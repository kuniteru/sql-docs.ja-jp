---
title: SQLServerException クラス | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
ms.assetid: af5ef257-7cf6-4db3-b1ee-07d22d82bef1
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: b2ed370fdb002563203ffbc403bda54acef688af
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2020
ms.locfileid: "80925324"
---
# <a name="sqlserverexception-class"></a>SQLServerException クラス
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  SQL ステートメントの実行に失敗したこと、または実行が完了しなかったことを表します。  
  
 **パッケージ:** com.microsoft.sqlserver.jdbc  
  
 **継承:** java.sql.SQLException  
  
 **実装:** java.io.Serializable  
  
## <a name="syntax"></a>構文  
  
```  
  
public final class SQLServerException  
```  
  
## <a name="remarks"></a>解説  
 SQLServerException クラスでは、SQL 92 と XOPEN の両方の状態コードが処理されます。 これらは、ユーザー指定の接続プロパティを使用して切り替えることができます。 例外は、開いている指定のログ ファイルに書き込まれます。  
  
## <a name="see-also"></a>参照  
 [SQLServerException のメンバー](../../../connect/jdbc/reference/sqlserverexception-members.md)   
 [JDBC Driver API リファレンス](../../../connect/jdbc/reference/jdbc-driver-api-reference.md)  
  
  
