
# Intrgrate SMS.Net.Bd SMS NuGet Package in Visual Studio

## Version 1.1.1
[![Static Badge](https://img.shields.io/badge/NuGet-1.1.1-blue?style=flat)
](https://www.nuget.org/packages/smsnetbd.Csharp.Client)
![Static Badge](https://img.shields.io/badge/.Net_Core-6.0-purple?style=flat)


### Summary:
The SMS.Net.Bd NuGet package provides a simple interface to send SMS messages using the SMS.Net.Bd API. This release introduces initial support for sending SMS messages, scheduling SMS messages, checking SMS delivery reports, and retrieving account balance.

### Initialization:
To start using the SMS.Net.Bd NuGet package, follow these steps:

1. **Install the Package**: Install the SMS.Net.Bd NuGet package in your project using the following command in the NuGet Package Manager Console:

   ```shell
   dotnet add package smsnetbd.Csharp.Client --version 1.1.1
   ```

2. **Initialize SMS Client**: Create an instance of the `SMS` class by providing your API key. This API key can be obtained from the [SMS.Net.Bd API website](https://www.sms.net.bd/api).

   ```csharp
   using SMS.Net.Bd;

   // Initialize SMS client with your API key
   SMS smsClient = new SMS("Your-API-Key");
   ```

### Usage:
After initializing the SMS client, you can use its methods to interact with the SMS.Net.Bd API. Below are the available methods and their usage:

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
   int messageId = 12345; // Specify the ID of the SMS message
   string report = await smsClient.GetReport(messageId);
   ```

4. **GetBalance**: Retrieve the current account balance.

   ```csharp
   // Get account balance
   string balance = await smsClient.GetBalance();
   ```

### Feedback and Support

We welcome your feedback and suggestions for improving the SMS.Net.Bd NuGet package. If you encounter any issues or have questions, please contact [Your Contact Information] or open an issue on the GitHub repository.

Thank you for using SMS.Net.Bd!


For more details on the SMS.Net.Bd API and its usage, refer to the [official API documentation](https://www.sms.net.bd/api).
