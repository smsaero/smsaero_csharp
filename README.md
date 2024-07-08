# SmsAero Client library for C#

[![NuGet version (smsaero)](https://img.shields.io/nuget/v/smsaero.svg?style=flat-square)](https://www.nuget.org/packages/smsaero/)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](https://opensource.org/licenses/MIT)

Library for sending SMS messages using the SmsAero API. Written in C#.

## Installation

### dotnet CLI:

```bash
dotnet add package smsaero --version 1.0.3
```

### Package Manager in Visual Studio:

```bash
Install-Package smsaero -Version 1.0.3
```

## Usage example:

Get credentials from account settings page: https://smsaero.ru/cabinet/settings/apikey/

```csharp
namespace SmsAero
{
    class Program
    {
        static async Task Main(string[] args)
        {
            const string smsAeroLogin = "your email";
            const string smsAeroApiKey = "your api key";

            try {
                SmsAeroClient smsAeroClient = new SmsAeroClient(smsAeroLogin, smsAeroApiKey);
                string response = await smsAeroClient.SmsSend("Hello, World!", "70000000000");
                Console.WriteLine(response);
            } catch (Exception e) {
                Console.WriteLine("Error: " + e.Message);
            }
        }
    }
}
```

### License

```
MIT License
```
