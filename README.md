# Slack Test Results Notification

> Send Slack message with test result from popular testing frameworks

⭐ **If you find this project useful, consider giving it a GitHub star** ⭐

It means a lot to us and helps us grow this open source library.

## Features

- **Send Test Results to Slack**: Automatically send test results to a Slack channel.
- **Send Flaky Test Details to Slack**: Automatically send flaky test details to a Slack channel.
- **Conditional Notifications**: Use the `--onFailOnly` option to send notifications only if tests fail.

## Setup

You'll need a CTRF report generated by your testing framework. [CTRF reporters](https://www.ctrf.io/docs/category/reporters) are available for most testing frameworks and easy to install.

### Create a Slack Incoming Webhook

1. Go to the [Slack API: Incoming Webhooks](https://api.slack.com/messaging/webhooks) page.
2. Click on "Create a Slack App" or use an existing app.
3. Add the "Incoming Webhooks" feature to your app.
4. Activate the Incoming Webhook and add a new webhook to your workspace.
5. Copy the webhook URL provided.

### Set the Environment Variable

Set the webhook URL as an environment variable in your shell or CI environment:

```sh
export SLACK_WEBHOOK_URL='https://hooks.slack.com/services/your/webhook/url'
```

Make sure to replace `'https://hooks.slack.com/services/your/webhook/url'` with your actual webhook URL.

You might want to store the webhook URL as a secret.

## Usage

To send the test results summary to Slack:

```sh
npx slack-ctrf results /path/to/ctrf-report.json
```

To send flaky test report to Slack:

```sh
npx slack-ctrf flaky /path/to/ctrf-report.json
```

### Send Only on Failures

To send the test results summary to Slack only if there are failed tests, use the `--onFailOnly` option:

```sh
npx slack-ctrf results /path/to/ctrf-file.json --onFailOnly
```

or using the alias:

```sh
npx slack-ctrf results /path/to/ctrf-file.json -f
```

## Options

- `--onFailOnly, -f`: Send notification only if there are failed tests.

## What is CTRF?

CTRF is a universal JSON test report schema that addresses the lack of a standardized format for JSON test reports.

**Consistency Across Tools:** Different testing tools and frameworks often produce reports in varied formats. CTRF ensures a uniform structure, making it easier to understand and compare reports, regardless of the testing tool used.

**Language and Framework Agnostic:** It provides a universal reporting schema that works seamlessly with any programming language and testing framework.

**Facilitates Better Analysis:** With a standardized format, programatically analyzing test outcomes across multiple platforms becomes more straightforward.

## Support Us

If you find this project useful, consider giving it a GitHub star ⭐ It means a lot to us.
