# WCP-Bookers_App_1

```
アプリケーションを作成してみよう：基礎編
```

## バージョン
- Ruby version
    - 2.5.7
- Ruby on Rails version
    - 5.2.4.1

## 環境構築
- Vagrant(Mac) + VirtualBox(6.0.14)

- 「vagrant-vbguest」プラグインをインストール  
`$ vagrant plugin install vagrant-vbguest`

- Vagrantfileを設置

- Vagrantを起動  
`$ vagrant up`

- Vagrantを停止  
`$ vagrant halt`

※ マウントできないエラーが発生した場合  

```
「/sbin/mount.vboxsf: mounting failed with the error: No such device」
```

- 「kernel」のバージョンを確認  
`$ rpm -qa kernel\* | sort`

- バージョンが不一致であれば、下記コマンドを実行  

```
$ vagrant ssh
$ sudo yum -y update kernel
$ sudo yum -y install kernel-devel kernel-headers kernel-tools kernel-tools-libs
$ vagrant reload
```

- railsサーバー起動  
`$ rails s -b 0.0.0.0`

- 動作確認URL  
    - http://localhost:3000

## Scaffoldによる雛形作成手順

```
$ rails g scaffold Book title:string body:text
$ rake db:migrate
```

## Rspec

- テスト実行  
`$ bundle exec rspec spec/ --format documentation`
