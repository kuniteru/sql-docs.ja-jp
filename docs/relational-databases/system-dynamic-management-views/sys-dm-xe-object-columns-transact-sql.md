---
title: dm_xe_object_columns (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.dm_xe_object_columns
- sys.dm_xe_object_columns_TSQL
- dm_xe_object_columns_TSQL
- dm_xe_object_columns
dev_langs:
- TSQL
helpviewer_keywords:
- sys.dm_xe_object_columns dynamic management view
- extended events [SQL Server], views
ms.assetid: d96a14f3-4284-45ff-b1fe-4858e540a013
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 005455742f1fbb782e663672c0cc104bd1cb28f9
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "85898606"
---
# <a name="sysdm_xe_object_columns-transact-sql"></a>dm_xe_object_columns (Transact-sql)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  すべてのオブジェクトのスキーマ情報を返します。  
  
> [!NOTE]  
>  イベントオブジェクトは、読み取り専用データと読み取り/書き込みデータの両方に対して、固定スキーマを公開します。  
  
|列名|データ型|説明|  
|-----------------|---------------|-----------------|  
|name|**nvarchar(256)**|列の名前です。 名前は、オブジェクト内で一意です。 NULL 値は許可されません。|  
|column_id|**int**|列の識別子。 column_id は、column_type と共に使用する場合に、オブジェクト内で一意です。 NULL 値は許可されません。|  
|object_name|**nvarchar(256)**|この列が所属するオブジェクトの名前。 Dm_xe_objects との間には多対一のリレーションシップがあります。Null 値は許容されません。|  
|object_package_guid|**uniqueidentifier**|オブジェクトを含むパッケージの GUID。 NULL 値は許可されません。|  
|type_name|**nvarchar(256)**|この列の型の名前。 NULL 値は許可されません。|  
|type_package_guid|**uniqueidentifier**|列のデータ型を含むパッケージの GUID。 NULL 値は許可されません。|  
|column_type|**nvarchar(60)**|この列の使用方法を示します。 NULL 値は許可されません。 column_type には、次のいずれかを指定できます。<br /><br /> readonly. 列には、変更できない静的な値が含まれています。<br /><br /> data。 オブジェクトによって公開される実行時データが列に格納されます。<br /><br /> 独自. 列には、変更可能な値が含まれています。<br /><br /> 注: この値を変更すると、オブジェクトの動作が変更される可能性があります。|  
|column_value|**nvarchar(256)**|オブジェクト列に関連付けられた静的な値を表示します。 NULL 値が許可されます。|  
|capabilities|**int**|列の機能を説明するビットマップ。 NULL 値が許可されます。|  
|capabilities_desc|**nvarchar(256)**|このオブジェクト列の機能についての説明です。 この値は、次のいずれかです。<br /><br /> 必須。 親オブジェクトをイベント セッションにバインドするときに値を設定する必要があります。<br /><br /> NULL 値が許可されます。|  
|description|**nvarchar (3072)**|このオブジェクト列の説明です。 NULL 値が許可されます。|  
  
## <a name="permissions"></a>アクセス許可  
 サーバーに対する VIEW SERVER STATE 権限が必要です。  
  
### <a name="relationship-cardinalities"></a>リレーションシップ基数  
  
|From|終了|リレーションシップ|  
|----------|--------|------------------|  
|sys.dm_xe_object_columns.object_name、sys.dm_xe_object_columns.object_package_guid|sys.dm_xe_objects.name、<br /><br /> sys.dm_xe_objects.package_guid|多対一|  
|sys.dm_xe_object_columns.type_name<br /><br /> sys.dm_xe_object_columns.type_package_guid|sys.dm_xe_objects.name<br /><br /> sys.dm_xe_objects.package_guid|多対一|  
  
## <a name="see-also"></a>関連項目  
 [動的管理ビューおよび関数 &#40;Transact-SQL&#41;](~/relational-databases/system-dynamic-management-views/system-dynamic-management-views.md)  
  
  

