---
title: Always Encrypted を使用したデータベースのバックアップと復元 | Microsoft Docs
ms.custom: ''
ms.date: 10/30/2019
ms.prod: sql
ms.reviewer: vanto
ms.technology: security
ms.topic: conceptual
ms.assetid: 29816a41-f105-4414-8be1-070675d62e84
author: jaszymas
ms.author: jaszymas
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: bb529b9cc518cd7802dfdbbddba8b88e399dbcba
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85627390"
---
# <a name="backup-and-restore-databases-using-always-encrypted"></a>Always Encrypted を使用したデータベースのバックアップと復元 
[!INCLUDE [SQL Server Azure SQL Database](../../../includes/applies-to-version/sql-asdb.md)]

この記事では、[Always Encrypted](../../../relational-databases/security/encryption/always-encrypted-database-engine.md) で保護された列を含むデータベースをバックアップおよび復元する方法について説明します。

データベースをバックアップすると、生成されるバックアップ ファイルには、Always Encrypted キーの暗号化された列に格納されている暗号化データとすべてのメタデータが含まれます。

データベースを復元するとき、Always Encrypted のすべての暗号化データとすべてのメタデータが復元されます。 

データベースを別のサーバー上で、または別の名前で復元した場合は、両方のデータベースのキーが同じであるため、ターゲット データベースの暗号化されたデータをアプリケーションでクエリできるようにするための特別な操作は必要ありません。

データベースのバックアップと復元を行う方法の詳細については、以下を参照してください。
- [バックアップの概要 (SQL Server)](../../backup-restore/backup-overview-sql-server.md)
- [データベースをマネージド インスタンスに復元する](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance-get-started-restore)

## <a name="next-steps"></a>次の手順
- [SQL Server Management Studio で Always Encrypted を使用した列のクエリを実行する](always-encrypted-query-columns-ssms.md)
- [セキュリティで保護されたエンクレーブが設定された Always Encrypted を使用するアプリケーションを開発する](always-encrypted-enclaves-client-development.md) 

## <a name="see-also"></a>参照
- [常に暗号化](../../../relational-databases/security/encryption/always-encrypted-database-engine.md)
- [Always Encrypted を使用したデータベースのエクスポートとインポート](always-encrypted-migrate-using-bacpac.md)
- [SQL Server インポートおよびエクスポート ウィザードで Always Encrypted を使用して列間でデータを移行する](always-encrypted-migrate-using-import-export-wizard.md)
- [Always Encrypted を使用した暗号化データの列への一括読み込み](migrate-sensitive-data-protected-by-always-encrypted.md)
