---
title: サーバー接続ファイルの作成 (DB2ToSQL) |Microsoft Docs
ms.prod: sql
ms.custom: ''
ms.date: 07/14/2020
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
ms.assetid: 685419f6-8606-462c-be12-8bace45bede6
author: nahk-ivanov
ms.author: alexiva
ms.openlocfilehash: 4a1ee05cbf14f18a34b15161eec88df04be5539b
ms.sourcegitcommit: cb620c77fe6bdefb975968837706750c31048d46
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "86392780"
---
# <a name="creating-the-server-connection-files-db2tosql"></a>サーバー接続ファイルの作成 (DB2ToSQL)

サーバー情報は、スクリプトファイルの [サーバー] セクションで、または別のサーバー接続ファイルで指定できます。 サーバー接続ファイルのコマンドラインパラメーターは、 `-c <serverconnectionfile>` です。 スクリプトファイルとサーバー接続ファイルの両方に同じサーバー ID が存在する場合は、スクリプトファイル内のサーバー定義が考慮されます。

**例: 1**

```xml
<!-- Sample of server connection file commands -->
<db2 name="<source-server-unique-name>">
  <standard-mode>

    <connection-provider value="OleDB Provider" />

    <!-- Defines server manager to connect.
         Available manager attribute values
           • zOs - DB2 for z/OS
           • LUW - DB2 for Linux, Unix and Windows
           • DBi - DB2 for i -->
    <database-manager value="$Db2Manager$" />

    <server-name value="$Db2HostName$" />

    <port value="$Db2Port$" />

    <initial-catalog value="$Db2Instance$" />

    <user-id value="$Db2UserName$" />

    <password value="$Db2Password$"/>

  </standard-mode>
</db2>
```

```xml
<sql-server name="<target-server-unique-name>">
  <sql-server-authentication>

    <server value="<server-name>" />

    <database value="<database-name>" />
  
    <user-id value="<user-name>"/>
  
    <password value="<password>"/>

  </sql-server-authentication>
</sql-server>
```

## <a name="next-step"></a>次の手順

コンソールを操作する次の手順では、 [SSMA コンソール &#40;DB2ToSQL を実行](../../ssma/db2/executing-the-ssma-console-db2tosql.md)して&#41;

## <a name="see-also"></a>関連項目

- [SSMA コンソールの実行](https://msdn.microsoft.com/ce63f633-067d-4f04-b8e9-e1abd7ec740b)
