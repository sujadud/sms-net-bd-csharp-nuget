
# sms.net.bd NuGet Package Release Note

## Version 1.1.1
[![Static Badge](https://img.shields.io/badge/NuGet-1.1.1-blue?style=flat)
](https://www.nuget.org/packages/smsnetbd.Csharp.Client)
![Static Badge](https://img.shields.io/badge/.Net_Core-6.0-purple?style=flat)

### Summary:
The sms.net.bd NuGet package provides a simple interface to send SMS messages using the sms.net.bd API. This release introduces initial support for sending SMS messages, scheduling SMS messages, checking SMS delivery reports, and retrieving account balances.

### Initialization:
To start using the sms.net.bd NuGet package, follow these steps:

1. **Install the Package**: Install the sms.net.bd NuGet package in your project using the following command in the NuGet Package Manager Console:

   ```shell
   dotnet add package smsnetbd.Csharp.Client
   ```

2. **Initialize SMS Client**: Create an instance of the `SMS` class by providing your API key. This API key can be obtained from the [sms.net.bd API website](https://www.sms.net.bd/api).

   ```csharp
   using sms.net.bd;

   // Initialize SMS client with your API key
   SMS smsClient = new SMS("Your-API-Key");
   ```

### Usage:
After initializing the SMS client, you can use its methods to interact with the sms.net.bd API. Below are the available methods and their usage:

1. **SendSMS**: Send a text message to a specified phone number.

   ```csharp
   // Send SMS message
   string phoneNumber = "1234567890";
   string message = "Hello, world!";
   string response = await smsClient.SendSMS(phoneNumber, message);
   ```

2. **ScheduleSMS**: Schedule a text message to be sent at a specified time.

   ```csharp
   // Schedule SMS message
   string phoneNumber = "1234567890";
   string message = "Hello, world!";
   string scheduleTime = "2023-11-01T12:00:00"; // Specify the scheduled time in ISO 8601 format
   string response = await smsClient.ScheduleSMS(phoneNumber, message, scheduleTime);
   ```

3. **GetReport**: Retrieve the delivery report of an SMS message.

   ```csharp
   // Get SMS delivery report
   string messageId = 12345; // Specify the ID of the SMS message
   string report = await smsClient.GetReport(messageId);
   ```

4. **GetBalance**: Retrieve the current account balance.

   ```csharp
   // Get account balance
   string balance = await smsClient.GetBalance();
   ```

### Error Codes

| Common Errors |  |
|--|--|
| Error - 0 | Success. Everything worked as expected. |
| Error - 400 | The request was rejected, due to a missing or invalid parameter. |
| Error - 403 | You don't have permissions to perform the request. |
| Error - 404 | The requested resource not found. |
| Error - 405 | Authorization required. |
| Error - 409 | Unknown error occurred on Server end. |


| Send SMS Errors |  |
|--|--|
| Error - 410 | Account expired. |
| Error - 411 | Reseller Account expired or suspended. |
| Error - 412 | Invalid Schedule. |
| Error - 413 | Invalid Sender ID. |
| Error - 414 | Message is empty. |
| Error - 415 | Message is too long. |
| Error - 416 | No valid number found. |
| Error - 417 | Insufficient balance. |
| Error - 418 | Content Blocked. |

### Feedback and Support

We welcome your feedback and suggestions for improving the sms.net.bd NuGet package. If you encounter any issues or have questions, please contact [Your Contact Information] or open an issue on the GitHub repository.

Thank you for using sms.net.bd!


For more details on the sms.net.bd API and its usage, refer to the [official API documentation](https://www.sms.net.bd/api).
