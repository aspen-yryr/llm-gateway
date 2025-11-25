# LLMGateway

## 環境構築

- kubernetes クラスターのセットアップ
  - Docker Desktop の Kubernetes を kubeadm で有効化するのがおすすめ
  - 勝手に kubectl がインストールされるはず
- ingress-nginx のインストール

```
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.14.0/deploy/static/provider/cloud/deploy.yaml
```

### 名前解決設定

- Windows の場合、`C:\Windows\System32\drivers\etc\hosts`ファイルに以下のエントリを追加

```
127.0.0.1 litellm.local
```

- macOS/Linux の場合、`/etc/hosts`ファイルに以下のエントリを追加

```
127.0.0.1 litellm.local
```

### サービス起動して疎通確認

- `kubectl apply -k k8s/base`でサービスを起動
- http://litellm.localをブラウザで開く
