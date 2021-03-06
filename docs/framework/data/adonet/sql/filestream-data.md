---
title: "FILESTREAM 데이터"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bd8b845c-0f09-4295-b466-97ef106eefa8
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 2fde543187d1904da93be255878d6c7a99de6bbf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="filestream-data"></a>FILESTREAM 데이터
FILESTREAM 저장소 특성은 varbinary(max) 열에 저장된 이진(BLOB) 데이터에 사용됩니다. FILESTREAM 이전에는 이진 데이터를 저장하려면 특별한 처리가 필요했습니다. 텍스트 문서, 이미지 및 비디오 같이 구조화되지 않은 데이터는 대개 데이터베이스의 외부에 저장되어 관리가 어렵습니다.  
  
> [!NOTE]
>  SqlClient에서 FILESTREAM 데이터로 작업하려면 .NET Framework 3.5 SP1 이상을 설치해야 합니다.  
  
 varbinary(max) 열에 FILESTREAM 특성을 지정하면 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]에서는 데이터베이스 파일 대신 로컬 NTFS 파일 시스템에 데이터를 저장합니다. 데이터가 별도로 저장되기는 하지만 데이터베이스에 저장된 varbinary(max) 데이터로 작업할 때와 동일한 [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] 문을 사용할 수 있습니다.  
  
## <a name="sqlclient-support-for-filestream"></a>FILESTREAM에 대한 SqlClient 지원  
 [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] Data Provider for [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)](<xref:System.Data.SqlClient>)에서는 <xref:System.Data.SqlTypes.SqlFileStream> 네임스페이스에 정의된 <xref:System.Data.SqlTypes> 클래스를 사용하여 FILESTREAM 데이터에 대한 읽기와 쓰기를 지원합니다. `SqlFileStream`은 데이터 스트림에 대한 읽기 및 쓰기 메서드를 제공하는 <xref:System.IO.Stream> 클래스에서 상속됩니다. 스트림에서 읽으면 바이트 배열과 같은 데이터가 스트림에서 데이터 구조로 전송되고, 데이터를 쓰면 데이터가 데이터 구조에서 스트림으로 전송됩니다.  
  
### <a name="creating-the-includessnoversionincludesssnoversion-mdmd-table"></a>[!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 테이블 만들기  
 다음 [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] 문은 employees라는 테이블을 만들어 데이터 행을 삽입합니다. FILESTREAM 저장소를 설정한 후에는 다음에 나오는 코드 예제와 함께 이 테이블을 사용할 수 있습니다. 이 항목의 맨 마지막에는 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 온라인 설명서의 리소스에 대한 링크가 나옵니다.  
  
```  
CREATE TABLE employees  
(  
  EmployeeId INT  NOT NULL  PRIMARY KEY,  
  Photo VARBINARY(MAX) FILESTREAM  NULL,  
  RowGuid UNIQUEIDENTIFIER  NOT NULL  ROWGUIDCOL  
  UNIQUE DEFAULT NEWID()  
)  
GO  
Insert into employees  
Values(1, 0x00, default)  
GO  
```  
  
### <a name="example-reading-overwriting-and-inserting-filestream-data"></a>예제: FILESTREAM 데이터 읽기, 덮어쓰기 및 삽입  
 다음 샘플에서는 FILESTREAM에서 데이터를 읽는 방법을 보여 줍니다. 이 코드에서는 `FileAccess`를 `Read`로 설정하고 `FileOptions`를 `SequentialScan`으로 설정하여 파일의 논리 경로를 가져옵니다. 그런 다음 코드에서는 SqlFileStream의 바이트를 버퍼로 읽어오고 콘솔 창에 바이트를 씁니다.  
  
 이 샘플에서는 FILESTREAM에 데이터를 써서 기존의 모든 데이터를 덮어쓰는 방법도 보여 줍니다. 이 코드에서는 `SqlFileStream`를 `FileAccess`로 설정하고 `Write`를 `FileOptions`으로 설정하여 파일의 논리 경로를 가져오고 `SequentialScan`을 만듭니다. 그런 다음 `SqlFileStream`에 단일 바이트를 써서 파일의 모든 데이터를 대체합니다.  
  
 이 샘플에서는 Seek 메서드로 파일 끝에 데이터를 추가하여 FILESTREAM에 데이터를 쓰는 방법도 보여 줍니다. 이 코드에서는 `SqlFileStream`를 `FileAccess`로 설정하고 `ReadWrite`를 `FileOptions`으로 설정하여 파일의 논리 경로를 가져오고 `SequentialScan`을 만듭니다. 코드에서는 Seek 메서드를 사용하여 파일의 끝을 찾은 다음 기존 파일에 단일 바이트를 추가합니다.  
  
```csharp  
using System;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using System.Data;  
using System.IO;  
  
namespace FileStreamTest  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            SqlConnectionStringBuilder builder = new SqlConnectionStringBuilder("server=(local);integrated security=true;database=myDB");  
            ReadFilestream(builder);  
            OverwriteFilestream(builder);  
            InsertFilestream(builder);  
  
            Console.WriteLine("Done");  
        }  
  
        private static void ReadFilestream(SqlConnectionStringBuilder connStringBuilder)  
        {  
            using (SqlConnection connection = new SqlConnection(connStringBuilder.ToString()))  
            {  
                connection.Open();  
                SqlCommand command = new SqlCommand("SELECT TOP(1) Photo.PathName(), GET_FILESTREAM_TRANSACTION_CONTEXT() FROM employees", connection);  
  
                SqlTransaction tran = connection.BeginTransaction(IsolationLevel.ReadCommitted);  
                command.Transaction = tran;  
  
                using (SqlDataReader reader = command.ExecuteReader())  
                {  
                    while (reader.Read())  
                    {  
                        // Get the pointer for the file  
                        string path = reader.GetString(0);  
                        byte[] transactionContext = reader.GetSqlBytes(1).Buffer;  
  
                        // Create the SqlFileStream  
                        using (Stream fileStream = new SqlFileStream(path, transactionContext, FileAccess.Read, FileOptions.SequentialScan, allocationSize: 0))  
                        {  
                            // Read the contents as bytes and write them to the console  
                            for (long index = 0; index < fileStream.Length; index++)  
                            {  
                                Console.WriteLine(fileStream.ReadByte());  
                            }  
                        }  
                    }  
                }  
                tran.Commit();  
            }  
        }  
  
        private static void OverwriteFilestream(SqlConnectionStringBuilder connStringBuilder)  
        {  
            using (SqlConnection connection = new SqlConnection(connStringBuilder.ToString()))  
            {  
                connection.Open();  
  
                SqlCommand command = new SqlCommand("SELECT TOP(1) Photo.PathName(), GET_FILESTREAM_TRANSACTION_CONTEXT() FROM employees", connection);  
  
                SqlTransaction tran = connection.BeginTransaction(IsolationLevel.ReadCommitted);  
                command.Transaction = tran;  
  
                using (SqlDataReader reader = command.ExecuteReader())  
                {  
                    while (reader.Read())  
                    {  
                        // Get the pointer for file   
                        string path = reader.GetString(0);  
                        byte[] transactionContext = reader.GetSqlBytes(1).Buffer;  
  
                        // Create the SqlFileStream  
                        using (Stream fileStream = new SqlFileStream(path, transactionContext, FileAccess.Write, FileOptions.SequentialScan, allocationSize: 0))  
                        {  
                            // Write a single byte to the file. This will  
                            // replace any data in the file.  
                            fileStream.WriteByte(0x01);  
                        }  
                    }  
                }  
                tran.Commit();  
            }  
        }  
  
        private static void InsertFilestream(SqlConnectionStringBuilder connStringBuilder)  
        {  
            using (SqlConnection connection = new SqlConnection(connStringBuilder.ToString()))  
            {  
                connection.Open();  
  
                SqlCommand command = new SqlCommand("SELECT TOP(1) Photo.PathName(), GET_FILESTREAM_TRANSACTION_CONTEXT() FROM employees", connection);  
  
                SqlTransaction tran = connection.BeginTransaction(IsolationLevel.ReadCommitted);  
                command.Transaction = tran;  
  
                using (SqlDataReader reader = command.ExecuteReader())  
                {  
                    while (reader.Read())  
                    {  
                        // Get the pointer for file  
                        string path = reader.GetString(0);  
                        byte[] transactionContext = reader.GetSqlBytes(1).Buffer;  
  
                        using (Stream fileStream = new SqlFileStream(path, transactionContext, FileAccess.Write, FileOptions.SequentialScan, allocationSize: 0))  
                        {  
                            // Seek to the end of the file  
                            fileStream.Seek(0, SeekOrigin.End);  
  
                            // Append a single byte   
                            fileStream.WriteByte(0x01);  
                        }  
                    }  
                }  
                tran.Commit();  
            }  
  
        }  
    }  
} using (SqlConnection connection = new SqlConnection(  
    connStringBuilder.ToString()))  
{  
    connection.Open();  
  
    SqlCommand command = new SqlCommand("", connection);  
    command.CommandText = "select Top(1) Photo.PathName(), "  
    + "GET_FILESTREAM_TRANSACTION_CONTEXT () from employees";  
  
    SqlTransaction tran = connection.BeginTransaction(  
        System.Data.IsolationLevel.ReadCommitted);  
    command.Transaction = tran;  
  
    using (SqlDataReader reader = command.ExecuteReader())  
    {  
        while (reader.Read())  
        {  
            // Get the pointer for file  
            string path = reader.GetString(0);  
            byte[] transactionContext = reader.GetSqlBytes(1).Buffer;  
  
            FileStream fileStream = new SqlFileStream(path,  
                (byte[])reader.GetValue(1),  
                FileAccess.ReadWrite,  
                FileOptions.SequentialScan, 0);  
  
            // Seek to the end of the file  
            fs.Seek(0, SeekOrigin.End);  
  
            // Append a single byte   
            fileStream.WriteByte(0x01);  
            fileStream.Close();  
        }  
    }  
    tran.Commit();  
}  
```  
  
 또 다른 예제를 참조 하십시오. [저장 하 고 파일 스트림 열에 이진 데이터를 인출 하는 방법을](http://www.codeproject.com/Articles/32216/How-to-store-and-fetch-binary-data-into-a-file-str)합니다.  
  
## <a name="resources-in-includessnoversionincludesssnoversion-mdmd-books-online"></a>[!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 온라인 설명서 리소스  
 FILESTREAM에 대한 자세한 설명은 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 온라인 설명서의 다음 단원에 나와 있습니다.  
  
|항목|설명|  
|-----------|-----------------|  
|[FILESTREAM 저장소 디자인 및 구현](http://msdn2.microsoft.com/library/bb895234\(SQL.105\).aspx)|FILESTREAM 문서 및 관련 항목에 대한 링크를 제공합니다.|  
|[FILESTREAM 개요](http://msdn2.microsoft.com/library/bb933993\(SQL.105\).aspx)|FILESTREAM 저장소를 사용해야 하는 경우 및 FILESTREAM 저장소가 SQL Server 데이터베이스 엔진을 NTFS 파일 시스템과 통합하는 방법에 대해 설명합니다.|  
|[FILESTREAM 저장소 시작](http://msdn.microsoft.com/library/bb933995\(SQL.105\).aspx)|SQL Server 인스턴스에서 FILESTREAM을 사용하도록 설정하는 방법, 저장된 FILESTREAM 데이터에 데이터베이스와 테이블을 만드는 방법 및 FILESTREAM 데이터가 포함된 행을 조작하는 방법에 대해 설명합니다.|  
|[클라이언트 응용 프로그램에서 FILESTREAM 저장소 사용](http://msdn.microsoft.com/library/bb933877\(SQL.105\).aspx)|FILESTREAM 데이터로 작업하기 위한 Win32 API 함수에 대해 설명합니다.|  
|[FILESTREAM 및 기타 SQL Server 기능](http://msdn.microsoft.com/library/bb895334\(SQL.105\).aspx)|SQL Server의 다른 기능과 함께 FILESTREAM 데이터를 사용할 경우의 고려 사항, 지침 및 제한 사항을 제공합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [SQL Server 데이터 형식 및 ADO.NET](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 [ADO.NET에서 데이터 검색 및 수정](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [코드 액세스 보안 및 ADO.NET](../../../../../docs/framework/data/adonet/code-access-security.md)  
 [SQL Server 이진 및 큰 값 데이터](../../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
