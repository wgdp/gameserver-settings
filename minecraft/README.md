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
server:
  ip: 127.0.0.1
  exec_ansible_username: hoge
  exec_minecraft_username: minecraft
  openjdk_version: 8
  download_modpack_url: https://mediafilez.forgecdn.net/files/3570/46/SevTech_Ages_Server_3.2.3.zip
  dirname: minecraft_hogehoge
  runserver_sh: ServerStart.sh
  forge_version: 1.12.2-14.23.5.2860
minecraft_properties:
  motd: This is Minecraft server!!
  max_players: 8
  difficulty: 2
  server_port: 25565
service:
  description: Minecraft server
```
