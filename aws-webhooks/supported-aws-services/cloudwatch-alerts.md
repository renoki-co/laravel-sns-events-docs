# 🚨 CloudWatch Alerts

Cloudwatch Alerts sends notifications via SNS to your topics when an alarm state changed. For example, you can listen to all the OK and ALARM statuses and implement your own logic to send Slack notifications to your organization.

`$message` is the array message of the content, while `$originalMessage` is the entire SNS message as an array.

```php
use RenokiCo\AwsWebhooks\Http\Controllers\CloudwatchWebhook;

class MyCloudwatchController extends CloudwatchWebhook
{
    /**
     * Handle the event when an alarm transitioned to OK.
     *
     * @param  array  $message
     * @param  array  $originalMessage
     * @param  \Illuminate\Http\Request  $request
     * @return void
     */
    protected function onOkState(array $message, array $originalMessage, Request $request)
    {
        //
    }

    /**
     * Handle the event when an alarm transitioned to ALARM.
     *
     * @param  array  $message
     * @param  array  $originalMessage
     * @param  \Illuminate\Http\Request  $request
     * @return void
     */
    protected function onAlarmState(array $message, array $originalMessage, Request $request)
    {
        //
    }

    /**
     * Handle the event when an alarm transitioned to INSUFFICIENT_DATA.
     *
     * @param  array  $message
     * @param  array  $originalMessage
     * @param  \Illuminate\Http\Request  $request
     * @return void
     */
    protected function onInsufficientDataState(array $message, array $originalMessage, Request $request)
    {
        //
    }
}
```
