# 🧪 Testing your implementation

Laravel AWS Webhooks uses Laravel AWS SNS Events under the hood, so it exposes its `GeneratesSnsMessages` trait to generate valid SNS messages to send via HTTP POST on your defined endpoints.

Generating SNS messages to test your implementation during unit/feature tests is explained in the [Testing your implementation ](../getting-started/testing-your-implementation.md)section for the SNS Events package.
