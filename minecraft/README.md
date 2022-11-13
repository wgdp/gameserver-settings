# 使い方

hostsとvars.yml（もしくはsecret.yml）をサーバーごとに用意し、以下のコマンドで読み込み実行する。

```bash
ansible-playbook -i ${hostsのパス} -e @${vars.ymlのパス} setup_minecraft_server.yml
```

