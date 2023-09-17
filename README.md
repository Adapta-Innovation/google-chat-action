# google-chat-action

Github action to send Cards V2 to the google chat via webhook.

## Quick start

```yaml
  - name: Notify Google Chat
    id: test-action
    uses: SimonScholz/google-chat-action@main
    with:
        webhookUrl: {your google chat webhook url}
        jobStatus: ${{ job.status }}
        subtitle: Brought to you by Simon ;-)
        imageUrl: https://raw.githubusercontent.com/SimonScholz/simonscholz.github.io/gatsby-homepage/src/assets/img/avatar.webp
        imageType: SQUARE
        imageAltText: Alternative image text
    if: failure() # only send notification in case of failure
```

## inputs

| Property      | Description                     | Required   |
| ------------- | ------------------------------- | :--------: |
| webhookUrl    | The webhook URL of the Google Chat. Should be stored in an action secret. |    ✅      |
| jobStatus     | The optional jobStatus. Values can be success, failure, cancelled. You should pass ${{ job.status }} here. |    🚫      |
| title         | Optional title. If not set, it defaults to the action name + job status. |    🚫      |
| subtitle      | Optional subtitle. If not set, the subtitle will not be shown. |    🚫      |
| imageUrl      | Optional icon. If not set, no icon will be shown. |    🚫      |
| imageType     | Optional imageType (imageUrl must be set for this). Possible values are SQUARE and CIRCLE. If not set, this will default to CIRCLE. |    🚫      |
| imageAltText  | Optional imageAltText. Alternative in case the image cannot be shown. |    🚫      |