# raspi_initialization
2023/12/24時点での初期セットアップ手順の覚書  
## ラズパイ動作確認まで
1. メインPCでssh環境を用意する.sshのkeyを用意しておく.
1. メインPCに[Raspberry Pi Imager](https://www.raspberrypi.com/software/)をインストール  
1. メインPCにSDカードを指して(micro SDカードは認識しづらい場合は、SDに変換してから読み込むと吉)、Rasberry Pi Imagerを使用しOSをインストール  
    1. 64bit(recommended), ssh有効化, wifi設定, ユーザー設定  を有効化
1. ラズパイにSDカードを指して起動を確認(問題なければ、モニター、キーボードは無くても可)
1. メインPCからsshで接続できることを確認(パスワード認証)
1. sshの鍵認証を設定する
   1. scpでメインPCの公開鍵をラズパイにコピー
   1. ラズパイに公開鍵を登録
   ```
   mkdir ~/.ssh
   cat pubkey.pub >> ~/.ssh/authorized_keys
   ```
1. メインPCからsshで接続できることを確認(パスワード認証)

## ラズパイ初期環境構築
1. Docker Engineをインストール. raspi64bitは[Debian用のマニュアル](https://docs.docker.com/engine/install/debian/)に従う。aptでインストール可能。  (参考) [raspi 32bit用マニュアル](https://docs.docker.com/engine/install/raspberry-pi-os/)
1. Dockerグループ、起動時実行を設定する。[マニュアル](https://docs.docker.com/engine/install/linux-postinstall/)
1. 
