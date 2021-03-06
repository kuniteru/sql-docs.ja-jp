---
title: 記述子の種類 |Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- descriptors [ODBC], types
ms.assetid: ec20e446-e540-41ad-8559-d9c0a5b8358f
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 9a6c7b55194eb61c1a909ced2296e4ad2050b674
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "81304893"
---
# <a name="types-of-descriptors"></a>記述子の種類
記述子は、次のいずれかを説明するために使用されます。  
  
-   0個以上のパラメーターのセット。 パラメーター記述子は、次の内容を記述するために使用できます。  
  
    -   アプリケーション*パラメーターのバッファー* 。アプリケーションによって設定された入力動的引数、または SQL の**CALL**ステートメントの実行後に出力される動的引数のいずれかが含まれています。  
  
    -   *実装パラメーターのバッファー*。 入力動的引数の場合、アプリケーションで指定されているデータ変換の後に、アプリケーションパラメーターバッファーと同じ引数が格納されます。 出力の動的引数の場合、これには、アプリケーションが指定するデータ変換の前に返された引数が格納されます。  
  
     入力動的引数の場合、アプリケーションは、動的パラメーターマーカーを含む SQL ステートメントを実行する前に、アプリケーションパラメーター記述子で動作する必要があります。 入力と出力の両方の動的引数に対して、アプリケーションは、実装パラメーター記述子に含まれるデータ型とは異なるデータ型を指定して、データ変換を実現できます。  
  
-   データベースデータの1行。 行記述子は、次の内容を記述するために使用できます。  
  
    -   データベースの行を含む*実装行バッファー* 。 (これらのバッファーには、データベースとの間で読み書きされるデータが概念的に含まれています。 ただし、格納されているデータベースデータの形式は指定されていません。 データベースは、実装バッファー内のフォームからデータに対して追加の変換を実行できます)。  
  
    -   アプリケーションが指定する任意のデータ変換に従って、アプリケーションに表示されるデータの行を含む*アプリケーションの行バッファー* 。  
  
     アプリケーションは、データベースの列データがアプリケーション変数に出現する必要がある場合に、アプリケーションの行記述子で動作します。 列データのデータ変換を実現するために、アプリケーションでは、実装行記述子とは異なるデータ型を指定できます。  
  
 記述子の種類を次の表にまとめます。  
  
|バッファーの種類|[行]|動的パラメーター|  
|-----------------|----------|------------------------|  
|**アプリケーションバッファー**|アプリケーションの行記述子 (標準)|アプリケーションパラメーター記述子 (APD)|  
|**実装バッファー**|実装行記述子 (IRD)|実装パラメーター記述子 (IPD)|  
  
 パラメーターまたは行バッファーのいずれかについて、アプリケーションが実装とアプリケーション記述子の対応するレコードで異なるデータ型を指定している場合、ドライバーは記述子を使用するときにデータ変換を実行します。 たとえば、数値と datetime 値を文字文字列形式に変換できます。 (有効な変換については、「[付録 D: データ型](../../../odbc/reference/appendixes/appendix-d-data-types.md)」を参照してください)。  
  
 記述子は、さまざまなロールを実行できます。 異なるステートメントは、アプリケーションが明示的に割り当てる任意の記述子を共有できます。 1つのステートメント内の行記述子は、別のステートメントのパラメーター記述子として使用できます。  
  
 記述子がデータベース操作でまだ使用されていない場合でも、特定の記述子がアプリケーション記述子であるか、実装記述子であるかは常にわかっています。 実装によって暗黙的に割り当てられる記述子については、実装により、ステートメントハンドルを基準とした定義済みの行が記録されます。 **SQLAllocHandle**を呼び出すことによってアプリケーションによって割り当てられる記述子は、アプリケーション記述子です。
