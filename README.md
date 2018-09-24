# seedconfig
Amazon Linux 2のVMware用のseed.isoの元ファイル
詳細については以下のURL参照
https://docs.aws.amazon.com/ja_jp/AWSEC2/latest/UserGuide/amazon-linux-2-virtual-machine.html#amazon-linux-2-virtual-machine-download

#使い方
Linux環境にseedconfigディレクトリを作成して以下の2ファイルを配置
meta-data
user-data

以下のコマンドでisoイメージを作成
genisoimage -output seed.iso -volid cidata -joliet -rock user-data meta-data

ダウンロードしたAmazon Linux 2の仮想マシンイメージを元に「OVAファイルから仮想マシンをデプロイ」する。

起動時にDVDブートするように設定した上で、作成したseed.isoをマウントする。

指定した通りに修正された仮想マシンが起動する。

#注意点
Network指定時にOnboot設定を行う方法が不明。判明次第追記する。
SSHで接続時の鍵認証となってしまう点を修正する。
Gitに上げるときはセンシティブな情報を修正するシェルを流してから上げること。

