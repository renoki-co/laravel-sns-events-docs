# 📧 Simple Email Service (SES)

Simple Email Service integrates with SNS to send notifications regarding mails. For example, you can catch bouncers or click/opens for various addresses.

All methods accept the same parameters.

`$message` is the array message of the content, while `$originalMessage` is the entire SNS message as an array.

```php
use RenokiCo\AwsWebhooks\Http\Controllers\SesWebhook;

class MySesController extends SesWebhook
{
    /**
     * Handle the Bounce event.
     *
     * @param  array  $message
     * @param  array  $originalMessage
     * @param  \Illuminate\Http\Request  $request
     * @return void
     */
    protected function onBounce(array $message, array $originalMessage, Request $request)
    {
        //    
    }

    protected function onComplaint(array $message, array $originalMessage, Request $request)
    {
        //
    }

    protected function onDelivery(array $message, array $originalMessage, Request $request)
    {
        //
    }

    protected function onSend(array $message, array $originalMessage, Request $request)
    {
        //
    }

    protected function onReject(array $message, array $originalMessage, Request $request)
    {
        //
    }

    protected function onOpen(array $message, array $originalMessage, Request $request)
    {
        //
    }

    protected function onClick(array $message, array $originalMessage, Request $request)
    {
        //
    }

    protected function onRenderingFailure(array $message, array $originalMessage, Request $request)
    {
        //
    }

    protected function onDeliveryDelay(array $message, array $originalMessage, Request $request)
    {
        //
    }
}
```
