# 使い方

hostsとvars.yml（もしくはsecret.yml）をサーバーごとに用意し実行する。

```bash
ansible-playbook -i ${hostsのパス} -e @${vars.ymlのパス} setup_minecraft_server.yml
```
hostsとvas.ymlの例を以下に示す。

```plainText
# hosts
# 以下のようにサーバーIPを追記する
127.0.0.1
```

```yaml
# vars.yml
# 適宜設定を書き換える。以下例。
server:                               # サーバー全般の設定
  ip: 127.0.0.1                       # サーバーのIP
  exec_ansible_username: hoge         # ansible実行時のサーバー側ユーザー
  exec_minecraft_username: minecraft  # minecraftサーバーを実行するサーバー
  openjdk_version: 8                  # openjdkのバージョン。Mod環境で多い1.12.2は8でおｋ。1.18以降だと17
  download_modpack_url: https://mediafilez.forgecdn.net/files/3570/46/SevTech_Ages_Server_3.2.3.zip # ModpackのダウンロードURL。例のURLはSevTech Ages
  dirname: minecraft_hogehoge         # ダウンロードしたModpackを展開するディレクトリ名
  runserver_sh: ServerStart.sh        # サーバー実行用のシェルスクリプト。基本的には自分で作らなくても用意されていることが多い。
  forge_version: 1.12.2-14.23.5.2860  # フォージのバージョン
minecraft_properties:                 # minecraftのサーバープロパティ周り      
  motd: This is Minecraft server!!    # motdはMinecraftのサーバー説明。
  max_players: 8                      # サーバーのプレイヤー最大数
  difficulty: 2                       # 難易度 0: ピースフル, 1: イージー, 2: ノーマル, 3: ハード
  server_port: 25565                  # ポート
service:                              # サービス周り
  description: Minecraft server       # serviceファイルの説明
```
