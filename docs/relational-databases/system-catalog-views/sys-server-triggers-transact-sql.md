---
title: server_triggers (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- server_triggers
- sys.server_triggers_TSQL
- server_triggers_TSQL
- sys.server_triggers
dev_langs:
- TSQL
helpviewer_keywords:
- sys.server_triggers catalog view
ms.assetid: 25926ff4-9271-45bf-bc32-d5d3344bd47a
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 7ce21b1c997a1530212f9a0317632f665c9ef503
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "85884464"
---
# <a name="sysserver_triggers-transact-sql"></a>server_triggers (Transact-sql)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  TR または TA の object_type を持つ、すべてのサーバーレベルの DDL トリガーのセットを格納します。 CLR トリガーの場合は、アセンブリを**master**データベースに読み込む必要があります。 すべてのサーバーレベルの DDL トリガー名は、1つのグローバルスコープに存在します。  
  
|列名|データ型|説明|  
|-----------------|---------------|-----------------|  
|**name**|**sysname**|トリガーの名前。|  
|**object_id**|**int**|オブジェクトの ID。|  
|**parent_class**|**tinyint**|親のクラス。 常に次のようになります。<br /><br /> 100 = サーバー|  
|**parent_class_desc**|**nvarchar(60)**|親のクラスの説明です。 常に次のようになります。<br /><br /> SERVER.|  
|**parent_id**|**int**|SERVER 上のトリガーに対しては常に 0 です。|  
|**type**|**char(2)**|オブジェクトの種類:<br /><br /> TA = アセンブリ (CLR) トリガー<br /><br /> TR = SQL トリガー|  
|**type_desc**|**nvarchar(60)**|オブジェクトの種類のクラスの説明です。<br /><br /> CLR_TRIGGER<br /><br /> SQL_TRIGGER|  
|**create_date**|**datetime**|トリガーが作成された日付。|  
|**modify_date**|**datetime**|トリガーが ALTER ステートメントを使用して最後に変更された日付です。|  
|**is_ms_shipped**|**bit**|内部コンポーネントによってユーザーの代理として作成されたトリガー [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 。|  
|**is_disabled**|**bit**|1 = トリガーは無効です。|  
  
## <a name="permissions"></a>アクセス許可  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] 詳細については、「 [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [カタログ ビュー &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)  
  
  
