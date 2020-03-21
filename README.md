# Cockpitのインストール方法
Cockpitはかんたんに使えて，軽量で，マルチサーバーにも対応したウェブベースのLinuxシステム管理ツール
Raspberry piで使用するためのマニュアル

## インストール
> sudo apt install dirmngr

> sudo su -   
>> echo 'deb http://deb.debian.org/debian stretch-backports main' > /etc/apt/sources.list.d/backports.list   
>> gpg --keyserver pgp.mit.edu --recv-keys 8B48AD6246925553   
>> gpg --keyserver keyserver.ubuntu.com --recv-keys 7638D0442B90D010   
>> gpg --keyserver keyserver.ubuntu.com --recv-keys 04EE7237B7D453EC   
>> gpg -a --export 8B48AD6246925553 | sudo apt-key add -   
>> gpg -a --export 7638D0442B90D010 | sudo apt-key add -   
>> gpg -a --export 04EE7237B7D453EC | sudo apt-key add -   
>> exit

> sudo apt-get update   
> sudo apt-get install cockpit   

## Cockpitにアクセス
https://（Cockpitをインストールしたマシンのアドレス）:9090/   
ユーザー名:pi   
パスワード:設定したパスワード   

## TLS/SSLの設定
> sudo openssl x509 -in /etc/cockpit/ws-certs.d/0-self-signed.cert -noout -text -fingerprint -sha256
~~~
Certificate:
    Data:
        Version: 3 (0x2)
        Serial Number: 18178437666814379984 (0xfc46c8be960d47d0)
    Signature Algorithm: sha256WithRSAEncryption
        Issuer: O=cd7d49e86dca4b89b455011597378bc8, CN=cockpit
（中略）
SHA256 Fingerprint=88:5C:92:47:98:AE:8B:95:46:AA:30:EA:EE:3C:EF:5C:5E:1E:65:DE:AC:B7:19:9A:B8:F1:E4:9C:A1:79:6B:38

~~~

## 参考サイト
[第480回　ウェブブラウザーから操作できる軽量管理ツール「Cockpit」](https://gihyo.jp/admin/serial/01/ubuntu-recipe/0480?page=1)   
[【Raspberry Pi】Webブラウザーから Raspberry Pi を管理　Webベース管理ツール「Cockpit」](https://www.startpassion.life/entry/2019/08/30/221549)
