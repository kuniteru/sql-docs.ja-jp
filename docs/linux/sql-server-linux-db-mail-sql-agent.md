---
title: Linux 上の SQL エージェントでの DB メールと電子メール アラート
description: この記事では、SQL Server on Linux で DB メールと電子メール アラートを使用する方法について説明します。
author: VanMSFT
ms.author: vanto
ms.date: 02/20/2018
ms.topic: conceptual
ms.prod: sql
ms.technology: linux
ms.assetid: tbd
ms.openlocfilehash: d2e759d5cfa0f7b1fa918bde8547d3cbee2439af
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "85896509"
---
# <a name="db-mail-and-email-alerts-with-sql-agent-on-linux"></a>Linux 上の SQL エージェントでの DB メールと電子メール アラート

[!INCLUDE [SQL Server - Linux](../includes/applies-to-version/sql-linux.md)]

次の手順では、Linux 上の SQL Server エージェント (**mssql-server-agent**) で DB メールを設定して使用する方法を示します。 

## <a name="1-enable-db-mail"></a>1.DB メールを有効にする

```sql
USE master 
GO 
sp_configure 'show advanced options',1 
GO 
RECONFIGURE WITH OVERRIDE 
GO 
sp_configure 'Database Mail XPs', 1 
GO 
RECONFIGURE  
GO  
```

## <a name="2-create-a-new-account"></a>2.新しいアカウントを作成する
```sql
EXECUTE msdb.dbo.sysmail_add_account_sp 
@account_name = 'SQLAlerts', 
@description = 'Account for Automated DBA Notifications', 
@email_address = 'sqlagenttest@gmail.com', 
@replyto_address = 'sqlagenttest@gmail.com', 
@display_name = 'SQL Agent', 
@mailserver_name = 'smtp.gmail.com', 
@port = 587, 
@enable_ssl = 1, 
@username = 'sqlagenttest@gmail.com', 
@password = '<password>' 
GO
```

## <a name="3-create-a-default-profile"></a>3.既定のプロファイルを作成する

```sql
EXECUTE msdb.dbo.sysmail_add_profile_sp 
@profile_name = 'default', 
@description = 'Profile for sending Automated DBA Notifications' 
GO
```

## <a name="4-add-the-database-mail-account-to-a-database-mail-profile"></a>4.データベース メール プロファイルにデータベース メール アカウントを追加する
```sql
EXECUTE msdb.dbo.sysmail_add_principalprofile_sp 
@profile_name = 'default', 
@principal_name = 'public', 
@is_default = 1 ; 
 ```
 
## <a name="5-add-account-to-profile"></a>5.アカウントをプロファイルに追加する 
```sql
EXECUTE msdb.dbo.sysmail_add_profileaccount_sp   
@profile_name = 'default',   
@account_name = 'SQLAlerts',   
@sequence_number = 1;  
 ```
 
## <a name="6-send-test-email"></a>6.テスト電子メールを送信する
> [!NOTE]
> 場合によっては、電子メール クライアントにアクセスして、低セキュリティのクライアントによるメール送信の許可を有効にする必要があります。 一部のクライアントでは、DB メールは電子メール デーモンとして認識されません。

```
EXECUTE msdb.dbo.sp_send_dbmail 
@profile_name = 'default', 
@recipients = 'recipient-email@gmail.com', 
@Subject = 'Testing DBMail', 
@Body = 'This message is a test for DBMail' 
GO
```

## <a name="7-set-db-mail-profile-using-mssql-conf-or-environment-variable"></a>7.mssql-conf または環境変数を使用して DB メールのプロファイルを設定する
mssql-conf ユーティリティまたは環境変数を使用して DB メールのプロファイルを設定できます。 このケースでは既定のプロファイルを使用します。

```bash
# via mssql-conf
sudo /opt/mssql/bin/mssql-conf set sqlagent.databasemailprofile default
# via environment variable
MSSQL_AGENT_EMAIL_PROFILE=default
```

## <a name="8-set-up-an-operator-for-sqlagent-job-notifications"></a>8.SQLAgent ジョブ通知のオペレーターを設定する 

```sql
EXEC msdb.dbo.sp_add_operator 
@name=N'JobAdmins',  
@enabled=1, 
@email_address=N'recipient-email@gmail.com',  
@category_name=N'[Uncategorized]' 
GO 
```

## <a name="9-send-email-when-agent-test-job-succeeds"></a>9.'Agent Test Job' が成功したら電子メールを送信する 

```
EXEC msdb.dbo.sp_update_job 
@job_name='Agent Test Job', 
@notify_level_email=1, 
@notify_email_operator_name=N'JobAdmins' 
GO
```

## <a name="next-steps"></a>次のステップ
SQL Server エージェントを使用してジョブを作成、スケジュール設定、および実行する方法について詳しくは、[Linux 上での SQL Server エージェント ジョブの実行](sql-server-linux-run-sql-server-agent-job.md)に関するページをご覧ください。
