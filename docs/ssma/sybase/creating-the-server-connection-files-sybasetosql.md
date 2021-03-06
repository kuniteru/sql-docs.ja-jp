---
title: サーバー接続ファイルの作成 (SybaseToSQL) |Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
helpviewer_keywords:
- Sybase Console,Creating Server Connection Files
- Sybase Console,Server Connection File Validation
ms.assetid: 35ef396f-9f98-429d-9fc5-4f413d08fb37
author: nahk-ivanov
ms.author: alexiva
ms.openlocfilehash: d50dead28fa182c946ec1abf0ac9cc4bb3f052d9
ms.sourcegitcommit: e8f6c51d4702c0046aec1394109bc0503ca182f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2020
ms.locfileid: "87931885"
---
# <a name="creating-the-server-connection-files-sybasetosql"></a>サーバー接続ファイルの作成 (SybaseToSQL)
サーバー情報は、スクリプトファイルの [サーバー] セクションで、または別のサーバー接続ファイルで指定できます。 サーバー接続ファイルのコマンドラインパラメーターは、 `-c <serverconnectionfile>` です。 スクリプトファイルとサーバー接続ファイルの両方に同じサーバー id が存在する場合は、スクリプトファイル内のサーバー定義が考慮されます。  
  
**例:**  
  
```  
1.<!--Sample of server connection file commands -->  
  
<sybase name="<source-server-unique-name>">  
  
  <standard-mode>  
  
    <provider value="Ole DB Provider"/>  
  
    <server-name value="<server-name>"/>  
  
    <server-port value="<port>"/>  
  
    <user-id value="<password>"/>  
  
  </standard-mode>  
  
</sybase>  
```  
  
```xml  
<!--Connection to SQL Server-->  
  
<sql-server name="<target-server-unique-name>">  
  
  <sql-server-authentication>  
  
    <database value="<database-name>"/>  
  
    <server value="<server-name>"/>  
  
    <user-id value="<user-name>"/>  
  
    <password value="<password>"/>  
  
    <encrypt value="<true/false>"/>  
  
    <trust-server-certificate value="<true/false>"/>  
  
  </sql-server-authentication >  
  
</sql-server>  
```  
  
```  
2.<!-Sample of server connection file commands-->  
<sybase name="<source-server-unique-name>">  
  
  <advanced-mode>  
  
    <connection-string value="User ID=<user-name>;Password=<password>;Provider=ASEOLEDB.1;Server=<server-name>;Port=<port>;OLE DB Services = -2;"/>  
  
  </advanced-mode >  
  
</sybase>  
```  
  
```xml  
<!--Connection to SQL Server-->  
  
<sql-server name="<target-server-unique-name>">  
  
  <sql-server-authentication >  
  
    <database value="<database-name>"/>  
  
    <server value="<server-name>"/>  
  
    <user-id value="<user-name>"/>  
  
    <password value="<password>"/>  
  
  </sql-server-authentication >  
  
</sql-server>  
```  
  
## <a name="server-connection-file-validation"></a>サーバー接続ファイルの検証  
ユーザーは、' スキーマ ' フォルダーで使用可能なスキーマ定義ファイル**S2SSConsoleScriptServersSchema**に対して、サーバー接続ファイルを簡単に検証できます。  
  
## <a name="next-step"></a>次の手順  
コンソールを操作する次の手順では、 [SSMA コンソール &#40;SybaseToSQL&#41;を実行](../../ssma/sybase/executing-the-ssma-console-sybasetosql.md)しています。  
  
## <a name="see-also"></a>参照  
[SSMA コンソールの実行](executing-the-ssma-console-sybasetosql.md)  
  
