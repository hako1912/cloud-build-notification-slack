# cloud-build-notification

Google Cloud Buildの結果をSlack通知する。

## 使い方

```bash
git clone <>
```

環境変数にSlackのWebhook URLを設定する。
```
gcloud functions deploy subscribe --update-env-vars HOGE=123
```
