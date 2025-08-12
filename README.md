# takuteh_server_config
サーバーの設定等を保存しておくリポジトリ  
## 注意点    
ビルドの際、事前に`_template`が入っているファイルは`_template`を外して配置し、環境に合わせて設定を書き換える必要がある  

例）
```shell 
cp nginx_template.yml nginx.yml
```

## 各サーバーの説明  
### reverse_proxy
- `nginx_template.conf`は通常のリバースプロキシの設定ファイル、ドメイン名とプロキシ先の設定を変更する
- `nginx_ngrok_template.conf`はngrokコンテナ経由の通信をリバプロする設定ファイル

### foward_proxy
- 通常のプロキシサーバー
- ホワイトリストにアクセス許可するドメイン名を記載する

### ngrok
- ngrokでドメインを取得したら、`ngrok.yml`に設定すればリバプロコンテナに通信を投げてくれる
