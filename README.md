# vagrant-windows-box

vagrantでwindows環境をつくる検証

## 必要なもの

- 多めのメモリ（VagrantfileでゲストOS用に4GB設定してます
- vagrant
- virtualbox
  - 最新のv6.1だとvagrantが対応していなかったのでv6.0を利用
- windowsイメージ
  - https://developer.microsoft.com/en-us/microsoft-edge/tools/vms/
  - virtual machineでwindows10を選択
  - select platformでvagrantを選択
    - (6GBのダウンロードを気長に待ちます)

## セットアップ手順

- vagrant / virtualbox / windowsイメージをダウンロード
- windowsイメージをvagrant boxとして追加しておく
  - `unzip MSEdge.Win10.Vagrant.zip`
  - `mv MSEdge\ -\ Win10.box MSEdgeWin10.box`
  - `vagrant box add MSEdgeWin10.box --name win10_edge`
    - Vagrantfileにこのbox名で登録しているので、名前変えたらVagrantfile側も変更する
- このリポジトリをclone（それかVagrantfileをコピペ
- vagrant up --provider=virtualbox
- `Passw0rd!` でログイン

## マシンにログイン後にやったほうがよさそうなこと

### 画面サイズを可変にする

- ツールバーからDevices > Insert Guest Additions CD Image...をクリック
- ゲストOSでDVDドライブをクリックしてGuest Additionsをインストール
- マシン再起動


### スナップショットを取る

- vagrant snapshot save default
