---
title: 分散トランザクションコーディネーター (ODBC)
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- MS DTC, using
ms.assetid: 12a275e1-8c7e-436d-8a4e-b7bee853b35c
author: markingmyname
ms.author: maghan
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: c4c0c042ac0a7236f04261e6750ad7771797a4a9
ms.sourcegitcommit: f3321ed29d6d8725ba6378d207277a57cb5fe8c2
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2020
ms.locfileid: "86000563"
---
# <a name="use-microsoft-distributed-transaction-coordinator-odbc"></a>Microsoft 分散トランザクション コーディネーターの使用 (ODBC)
[!INCLUDE[SQL Server Azure SQL Database Synapse Analytics PDW ](../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

    
### <a name="to-update-two-or-more-sql-servers-by-using-ms-dtc"></a>MS DTC を使用して複数の SQL Server を更新するには  
  
1.  MS DTC の OLE DtcGetTransactionManager 関数を使用して、MS DTC に接続します。 MS DTC の詳細については、Microsoft 分散トランザクション コーディネーターを参照してください。  
  
2.  確立する SQL Server 接続ごとに1回、SQL DriverConnect を呼び出します。  
  
3.  MS DTC の OLE ITransactionDispenser::BeginTransaction 関数を呼び出して、MS DTC トランザクションを開始し、トランザクションを表すトランザクション オブジェクトを取得します。  
  
4.  MS DTC トランザクションに参加させる ODBC 接続ごとに、[SQLSetConnectAttr](../../relational-databases/native-client-odbc-api/sqlsetconnectattr.md) を 1 回以上呼び出します。 [SQLSetConnectAttr](../../relational-databases/native-client-odbc-api/sqlsetconnectattr.md) の 2 番目のパラメーターは SQL_ATTR_ENLIST_IN_DTC、3 番目のパラメーターは (手順 3. で取得した) トランザクション オブジェクトである必要があります。  
  
5.  更新する SQL Server ごとに 1 回ずつ [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) を呼び出します。  
  
6.  MS DTC の OLE ITransaction::Commit 関数を呼び出して、MS DTC トランザクションをコミットします。 トランザクション オブジェクトは無効になります。  

 一連の MS DTC トランザクションを実行するには、手順 3. から手順 6. を繰り返します。  
  
 トランザクション オブジェクトへの参照を解放するには、MS DTC の OLE ITransaction::Return 関数を呼び出します。  
  
 MS DTC トランザクションで ODBC 接続を使用し、この接続をローカルの SQL Server トランザクションでも使用するには、[SQLSetConnectAttr](../../relational-databases/native-client-odbc-api/sqlsetconnectattr.md) に SQL_DTC_DONE を指定して呼び出します。  
  
> [!NOTE]  
>  手順 4. と手順 5. で示した呼び出し方法の代わりに、SQL Server ごとに [SQLSetConnectAttr](../../relational-databases/native-client-odbc-api/sqlsetconnectattr.md) と [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) を続けて呼び出すこともできます。  
  
## <a name="see-also"></a>参照  
 [ODBC&#41;&#40;のトランザクションの実行](https://msdn.microsoft.com/library/f431191a-5762-4f0b-85bb-ac99aff29724)  
  
  
