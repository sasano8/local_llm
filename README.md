# Ollama

Ollama のインストール。

```
curl -fsSL https://ollama.com/install.sh | sh
```


# 日本語に強いローカルLLMの導入

モデルをダウンロードする。

```
wget -O models/Llama-3-ELYZA-JP-8B-q4_k_m/Llama-3-ELYZA-JP-8B-q4_k_m.gguf https://huggingface.co/elyza/Llama-3-ELYZA-JP-8B-GGUF/resolve/main/Llama-3-ELYZA-JP-8B-q4_k_m.gguf?download=true
sha256sum Llama-3-ELYZA-JP-8B-q4_k_m.gguf # ハッシュを確認
```

モデルをデプロイする。

```
ollama create elyza:jp8b -f models/Llama-3-ELYZA-JP-8B-q4_k_m/Modelfile
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

