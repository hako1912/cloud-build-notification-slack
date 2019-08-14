# cloud-build-notification-slack

Google Cloud Buildの結果をSlack通知する。

## 使い方

`git clone`してから次のコマンドを実行する。
`BUCKET`変数と`SLACK_WEBHOOK_URL`変数は自分の環境に置き換える。
```bash
# Cloud Function用のストレージバケット名
# ex) my-project-cloud-build-notification
BUCKET='<cloud storage bucket name>'
gsutil mb gs://$BUCKET

# デプロイ
SLACK_WEBHOOK_URL='<your webhook url>'
gcloud functions deploy cloud-build-notification-slack \
    --stage-bucket $BUCKET \
    --entry-point subscribe \
    --trigger-topic cloud-builds \
    --runtime nodejs8 \
    --set-env-vars SLACK_WEBHOOK_URL=$SLACK_WEBHOOK_URL
```
