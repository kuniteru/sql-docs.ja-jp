---
title: SQLFreeStmt (カーソルライブラリ) |Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- SQLFreeStmt function [ODBC], Cursor Library
ms.assetid: 47bfbd4d-9453-4609-958d-1e05794cb223
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: d78075593926c15dbaeb1904603b08e990f64983
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "81302023"
---
# <a name="sqlfreestmt-cursor-library"></a>SQLFreeStmt (カーソル ライブラリ)
> [!IMPORTANT]  
>  この機能は、今後のバージョンの Windows では削除される予定です。 新しい開発作業ではこの機能の使用を避け、現在この機能を使用しているアプリケーションの変更を検討してください。 Microsoft では、ドライバーのカーソル機能を使用することをお勧めします。  
  
 このトピックでは、カーソルライブラリでの**SQLFreeStmt**関数の使用について説明します。 **SQLFreeStmt**の一般的な情報については、「 [SQLFreeStmt 関数](../../../odbc/reference/syntax/sqlfreestmt-function.md)」を参照してください。  
  
 アプリケーションが、 **SQLExtendedFetch**、 **sqlfetch**、または**sqlfetchscroll**を呼び出した後に SQL_UNBIND オプションを使用して**SQLFreeStmt**を呼び出すと、カーソルライブラリはエラーを返します。 結果セットの列のバインドを解除する前に、アプリケーションは SQL_CLOSE オプションを指定して**Sqlcloの**または**SQLFreeStmt**を呼び出す必要があります。
