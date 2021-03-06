---
title: System.Data.dll | で許可されていない型とメンバーMicrosoft Docs
descriptions: SQL Server CLR programming disallows a type or member with some values for the HostProtectionResource enum. This article lists System.Data.dll disallowed values.
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- host protection attributes [CLR integration]
- common language runtime [SQL Server], host protection attributes
ms.assetid: ee5f55e9-fbef-401a-be18-a2e5873c8720
author: rothja
ms.author: jroth
ms.openlocfilehash: b44f72ba097b45de94c7623e4b2e7b21ebe05e04
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85727704"
---
# <a name="disallowed-types-and-members-in-systemdatadll"></a>System.Data.dll の許可されない型およびメンバー
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]共通言語統合 (CLR) プログラミングでは、 **Hostprotectionattribute**が指定されている型またはメンバーの使用を禁止しています。これは**externalprocessmgmt**、 **externalスレッディング**、 **MayLeakOnAbort**、 **securityinfrastructure**、 **SelfAffectingProcessMgmnt**、 **SelfAffectingThreading**、 **Sharedstate**、 **Synchronization**、または**UI**の値を持つ、 **hostprotectionattribute**列挙体を指定します。 次の表は、ホスト保護属性 (HPA) 値が許可されない System.Data.dll アセンブリのメンバーおよび型を示しています。  
  
> [!NOTE]  
>  この一覧は、サポートされているアセンブリから作成されたものです。 詳細については、「[サポートされている .NET Framework ライブラリ](../../relational-databases/clr-integration/database-objects/supported-net-framework-libraries.md)」を参照してください。  
  
|型またはメンバー|HPA 値|  
|--------------------|--------------------|  
|System.Data.SqlClient.SqlCommand.BeginExecuteNonQuery()|ExternalThreading|  
|System.Data.SqlClient.SqlCommand.BeginExecuteReader()|ExternalThreading|  
|System.Data.SqlClient.SqlCommand.BeginExecuteXmlReader()|ExternalThreading|  
|System.Data.SqlClient.SqlDependency..ctor()|ExternalThreading|  
|System.Data.SqlClient.SqlDependency.Start()|ExternalThreading|  
|System.Data.SqlClient.SqlDependency.Stop()|ExternalThreading|  
|System.Data.TypedDataSetGenerator|SharedState、Synchronization|  
|System.Xml.XmlDataDocument|同期|  
  
## <a name="see-also"></a>関連項目  
 [ホスト保護属性と CLR 統合プログラミング](../../relational-databases/clr-integration-security-host-protection-attributes/host-protection-attributes-and-clr-integration-programming.md)   
 [Microsoft.VisualBasic.dllで許可されていない型とメンバー](../../relational-databases/clr-integration-security-host-protection-attributes/disallowed-types-and-members-in-microsoft-visualbasic-dll.md)   
 [mscorlib.dllで許可されていない型とメンバー](../../relational-databases/clr-integration-security-host-protection-attributes/disallowed-types-and-members-in-mscorlib-dll.md)   
 [System.dllで許可されていない型とメンバー](../../relational-databases/clr-integration-security-host-protection-attributes/disallowed-types-and-members-in-system-dll.md)   
 [System.Core.dll の許可されない型およびメンバー](../../relational-databases/clr-integration-security-host-protection-attributes/disallowed-types-and-members-in-system-core-dll.md)  
  
  
