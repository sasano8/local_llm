# Ollama

Ollama のインストール。

```
curl -fsSL https://ollama.com/install.sh | sh
```

インストールすると、デフォルトで 11434 ポートで Ollama サービスが起動します。


Ollama サービスを停止する場合は以下のコマンドを実行します。

```
sudo systemctl stop ollama
```


# 日本語に強いローカルLLMの導入

モデルをダウンロードする。

```
cd models/Llama-3-ELYZA-JP-8B-q4_k_m
./download.sh
```

モデルをデプロイする。

```
ollama create elyza:jp8b -f Modelfile
```

モデルと対話する。

```
ollama run elyza:jp8b
```

API で対話する。

```
curl http://localhost:11434/api/chat -d '{
  "model": "elyza:jp8b",
  "messages": [
    { "role": "user", "content": "why is the sky blue?" }
  ]
}'
```


# Open WebUI

https://github.com/open-webui/open-webui

