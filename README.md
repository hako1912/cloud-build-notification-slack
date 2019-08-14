# cloud-build-notification-slack

Google Cloud Buildの結果をSlack通知する。

## 使い方

`git clone`してから次のコマンドを実行する。

```bash
# Cloud Function用のストレージバケットを作成する
BUCKET='my-project-cloud-build-notification'
gsutil mb gs://$BUCKET

# デプロイ
gcloud functions deploy cloud-build-notification-slack \
    --stage-bucket $BUCKET \
    --entry-point subscribe \
    --trigger-topic cloud-builds \
    --runtime nodejs8 \
    --set-env-vars SLACK_WEBHOOK_URL='https://hooks.slack.com/services/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'
```
