# 第７回課題


## セキュリティリスク
* セキュアなシステムを作ることは重要な反面、ユーザビリティは犠牲になってしまう

* コスト面や運用面と相談してどこまでセキュリティ対策を施すか適切に提案できるのもエンジニアとして大切なスキルだと思った

## AWS WAF
* 専用装置がなくともWAFを導入できるので、あまり詳しくない人でもセキュリティ対策を行えて、セキュリティ意識の向上につながると思った

* 一方で、あくまでアプリケーション層のみを保護するので、AWS WAFだけで全ての脆弱性を解消できるわけではないことに留意が必要

* WAFコンソールを実際に触ってみたが、AWS managed ruleを使えば安価にかつ簡単にWAFを構成できると感じた

## SSL接続

### SSL通信の流れ
１．ブラウザはSSL通信をリクエストする<br>
２．サーバーがSSL証明書を送付する。<br>
３．ブラウザが電子証明書の検証により、「SSL証明書に記載されたドメイン」と「通信先のドメイン」が同じであることを確認する<br>
４．ブラウザとサーバーがSSL通信を行うために共通鍵を交換する<br>
５．ブラウザとサーバーが共通鍵を使って送受信するデータを暗号化・複合してSSL通信を成立させる

### SSL通信の限界
* 全ての通信を秘匿できるわけではなく、ネットワーク管理者なら通信先のIPアドレスやデータ量を見ることができてしまう

### ACM
* SSL証明書を発行するマネージドサービス

* ELBやCloudFrontにアタッチ可能

* パブリック証明書：無料

* プライベート証明書：有料

* ACMで発行した証明書をアタッチするだけでは不十分で、HTTPS通信を経由するように設定が必要

---

# 所感

## 現在の環境の脆弱性
* セキュリティグループのインバウンドルールで、HTTPプロトコルを0.0.0.0/0に設定している
* アプリケーション層に対する保護がなされておらず、SQLインジェクションなどを受ける可能性がある
* RDSやELBがSSL接続されていない

## 考えられる対策
* セキュリティグループのインバウンドルールで許可するIPアドレスの範囲を絞る
* AWS WAFによってアプリケーション層を保護する
* ACMを利用してELBやRDSにSSL接続する