---
title: Excel デバイス情報設定 | Microsoft Docs
ms.date: 01/23/2020
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.technology: reporting-services
ms.topic: conceptual
helpviewer_keywords:
- device information settings [Reporting Services], Excel rendering
- Excel [Reporting Services], rendering
ms.assetid: bb5f3566-f033-4470-be87-1f52fb7a4ab6
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 7a83bcd79a50400888d5a973ad9a743db19b87b5
ms.sourcegitcommit: ff82f3260ff79ed860a7a58f54ff7f0594851e6b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2020
ms.locfileid: "76761826"
---
# <a name="excel-device-information-settings"></a>Excel  デバイス情報設定
  次の表は、 [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] 形式で表示するためのデバイス情報設定を示しています。  
  
|設定|値|  
|-------------|-----------|  
|**OmitDocumentMap**|ドキュメント マップをサポートするレポートで、ドキュメント マップを省略するかどうかを示します。 既定値は **false** です。|  
|**OmitFormulas**|表示レポートで式を省略するかどうかを示します。 既定値は **false** です。|  
|**SimplePageHeaders**|レポートのページ ヘッダーを Excel ページのヘッダーに表示するかどうかを示します。 値 **false** は、ページ ヘッダーがワークシートの 1 行目に表示されることを示します。 既定値は **false** です。|  
|**DynamicImageDpi**|グラフ、ゲージ、マップなどの動的画像の解像度。 既定値は **96**です。 (Power BI Report Server (2020 年 1 月) 以降で使用可能)|  

  
## <a name="see-also"></a>参照  
 <xref:ReportExecution2005.ReportExecutionService.Render%2A>   
 [表示拡張機能にデバイス情報設定を渡す](../reporting-services/report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md)   
 [RSReportServer.Config で表示拡張機能パラメーターをカスタマイズする](../reporting-services/customize-rendering-extension-parameters-in-rsreportserver-config.md)   
 [テクニカル リファレンス (SSRS)](../reporting-services/technical-reference-ssrs.md)  
  
  
