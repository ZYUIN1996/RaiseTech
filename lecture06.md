# 第6回課題

## CloudTrail
<br>

### CloudTrailイベント履歴
* AWSを最後に利用した日：6/11<br>
* イベント履歴にあるイベント名<br>
①ConsoleLogin
②CheckMfa
③StartInstances

![CloudTrail_event](images/CloudTrail_event.png)

### ConsoleLogin
![ConsoleLogin](images/ConsoleLogin.png)

![ConsoleLogin_eventrecord](images/ConsoleLogin_eventrecord.png)

### CheckMfa
![CheckMfa](images/CheckMfa.png)

![CheckMfa](images/CheckMfa_eventrecord.png)

### StarnInstances
![StartInstances](images/StartInstances.png)

### イベント履歴に書かれていること
①eventtime<br>
リクエストが完了した日付と時刻を示し、API コールが行われた<br>
サービスAPI エンドポイントを提供するローカルホストから取得する。
<br>

②userAgent<br>
AWS Management Console、AWS CLI など、リクエストが行われたエージェント。<br>
今回の場合はMozilla/5.0なので、Firefoxからリクエストが行われたと記載されている。

③eventtype<br>
イベントレコードを生成したイベントのタイプを識別するためのもの。<br>
今回の場合はAwsConsoleSignInなので、AWSアカウントユーザーが<br>
AWS Management Consoleにサインインしたというeventtype。

## CloudWatchアラーム

### Railsアプリケーションが使える状態
①ターゲットのヘルスチェック

![TG-healthy](images/TG-healthy.png)

②CloudWatchアラーム

![unhealthyhostcount-OK](images/unhealthyhostcount-OK.png)

③AmazonSNSアクション

![AmazonSNS-OKaction](images/AmazonSNS-OKaction.png)

### Railsアプリケーションが使えない状態
①ターゲットのヘルスチェック

![TG-unhealthy](images/TG-unhealthy.png)

②CloudWatchアラーム

![unhealthyhostcount-ALARM](images/unhealthyhostcount-ALARM.png)

③AmazonSNSアクション

![AmazonSNS-ALARMaction](images/AmazonSNS-ALARMaction.png)


## AWS使用料の見積
①EC2<br>
https://calculator.aws/#/estimate?id=76c8674c2dbdca07c0190ba1ca9aefb8de74658e

②RDS<br>
https://calculator.aws/#/estimate?id=296f294c06853362d9213322babdc47f21dc94e5

③S3<br>
https://calculator.aws/#/estimate?id=3c894de9ae786b40a52752af22ab715ed7b8ae63

④ALB<br>
https://calculator.aws/#/estimate?id=98758b11cf231cb13b087da4cdc34a9ddcad2e43

## AWS使用料
①現在の利用料<br>

![June-billing](images/June-billing.png)

②先月のEC2の使用料<br>


![May-EC2-billing](images/May-EC2-billing.png)

③無料利用枠の確認

![FreeTier](images/FreeTier.png)

