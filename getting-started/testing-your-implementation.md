# 🧪 Testing your implementation

Laravel SNS Events comes with a `GeneratesSnsMessages` trait that helps you create valid SES payloads in order to test your SNS implementation.

```php

use Rennokki\LaravelSnsEvents\Concerns\GeneratesSnsMessages;

class MySesControllerTest extends TestCase
{
    use GeneratesSnsMessages;

    public static function setUpBeforeClass(): void
    {
        static::initializeSsl();
    }

    public static function tearDownAfterClass(): void
    {
        static::tearDownSsl();
    }

    public function test_my_ses_controller()
    {
        $payload = $this->getNotificationPayload([
            'eventType' => $type,
        ]);

        $response = $this->withHeaders($this->getHeadersForMessage($payload))
            ->json('GET', route('ses', ['certificate' => static::$certificate]), $payload)
            ->assertOk();
    }
}
```

**Note: Please make sure to specify the certificate query parameter to the route when calling HTTP requests.**
