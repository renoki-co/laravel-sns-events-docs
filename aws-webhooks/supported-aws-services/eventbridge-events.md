# 🌉 EventBridge Events

EventBridge is supported for all `aws.*` sources coming within the message payload. You can implement your own methods just by creating a method similar to `on[source_name]Event`.

For example, you might have this EC2 Spot Termination notice:

```javascript
{
   "id":"7bf73129-1428-4cd3-a780-95db273d1602",
   "detail-type":"EC2 Instance State-change Notification",
   "source":"aws.ec2",
   "account":"123456789012",
   "time":"2015-11-11T21:29:54Z",
   "region":"us-east-1",
   "resources":[
      "arn:aws:ec2:us-east-1:123456789012:instance/i-abcd1111"
   ],
   "detail":{
      "instance-id":"i-abcd1111",
      "state":"pending"
   }
}
```

Because the source is called `aws.ec2`, you should create an `onEc2Event` method within your extended class:

```php
use RenokiCo\AwsWebhooks\Http\Controllers\EventbridgeWebhook;

class MyEventbridgeController extends EventbridgeWebhook
{
    /**
     * Handle the EC2 events.
     *
     * @param  array  $message
     * @param  array  $originalMessage
     * @param  \Illuminate\Http\Request  $request
     * @return void
     */
    protected function onEc2Event(array $message, array $originalMessage, Request $request)
    {
        foreach ($message['resources'] as $instanceArn) {
            //
        }
    }
}
```
