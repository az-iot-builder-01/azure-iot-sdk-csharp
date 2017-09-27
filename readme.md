# Microsoft Azure IoT SDK for .NET

This repository contains the following:
* **Microsoft Azure IoT Hub device SDK for C#** to connect client devices to Azure IoT Hub with .NET
* **Microsoft Azure IoT Hub service SDK for C#** to manage your IoT Hub service instance from a back-end .NET application

The API reference documentation for .NET SDK is [here](dotnet-api-reference).

To find SDKs in other languages for Azure IoT, please refer to the [azure-iot-sdks][azure-iot-sdks] repository.

## Developing applications for Azure IoT
Visit [Azure IoT Dev Center][iot-dev-center] to learn more about developing applications for Azure IoT.

## Key features and roadmap

:white_check_mark: feature available  :large_blue_diamond: feature in-progress  :large_orange_diamond: feature planned  :x: no support planned

| Feature                                               | https                  | mqtt                   | mqtt-ws                | amqp                   | amqp-ws                | Description                                                                                                                                                                                                                                                                                                                                                                                        |
|-------------------------------------------------------|------------------------|------------------------|------------------------|------------------------|------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Authentication                                        | :white_check_mark:     | :large_orange_diamond: | :white_check_mark:     | :large_orange_diamond: | :white_check_mark:     | Connect your device to IoT Hub securely with [supported authentication](https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-security-deployment), including private key, SASToken, X-509 Self Signed and Certificate Authority (CA) Signed.  X-509 (CA) Signed is not supported on .NET SDK yet.                                                                                                |
| Retry policies                                        | :x:                    | :white_check_mark:     | :white_check_mark:     | :white_check_mark:     | :white_check_mark:     | Retry policy for unsuccessful device-to-cloud messages have three options: no try, exponential backoff with jitter (default) and custom.                                                                                                                                                                                                                                                           |
| Connection status reporting                           | :large_orange_diamond: | :large_orange_diamond: | :large_orange_diamond: | :large_orange_diamond: | :large_orange_diamond: |                                                                                                                                                                                                                                                                                                                                                                                                    |
| Devices multiplexing over single connection           | :white_check_mark:     | :x:                    | :x:                    | :white_check_mark:     | :white_check_mark:     |                                                                                                                                                                                                                                                                                                                                                                                                    |
| Connection Pooling - Specifying number of connections | :white_check_mark:     | :x:                    | :x:                    | :white_check_mark:     | :white_check_mark:     | Send device-to-cloud messages to IoT Hub with custom properties.  You can also choose to batch send at most 256 KBs (not available over MQTT).  Send device-to-cloud messages with system properties is in backlog.  Click [here](https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-devguide-messages-d2c) for detailed information on the IoT Hub features.                                  |
| Send D2C message                                      | :large_orange_diamond: | :large_orange_diamond: | :large_orange_diamond: | :large_orange_diamond: | :large_orange_diamond: |                                                                                                                                                                                                                                                                                                                                                                                                    |
| Receive C2D messages                                  | :white_check_mark:     | :white_check_mark:     | :white_check_mark:     | :white_check_mark:     | :white_check_mark:     | Receive cloud-to-device messages and read associated custom and system properties from IoT Hub, with the option to complete/reject/abandon C2D messages (not available over MQTT and MQTT-websocket).  Click [here](https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-devguide-messages-c2d) for detailed information on the IoT Hub features.                                                |
| Upload file to Blob                                   | :white_check_mark:     | :x:                    | :x:                    | :x:                    | :x:                    | A device can initiate a file upload and notifies IoT Hub when the upload is complete.  Click [here](https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-devguide-file-upload) for detailed information on the IoT Hub features.                                                                                                                                                                 |
| Device Twins                                          | :x:                    | :large_orange_diamond: | :large_orange_diamond: | :large_orange_diamond: | :large_orange_diamond: | IoT Hub persists a device twin for each device that you connect to IoT Hub.  The device can perform operations like get twin tags, subscribe to desired properties.  Send reported properties version and desired properties version are in backlog.  Click [here](https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-devguide-device-twins) for detailed information on the IoT Hub features. |
| Direct Methods                                        | :x:                    | :large_orange_diamond: | :large_orange_diamond: | :large_orange_diamond: | :large_orange_diamond: | IoT Hub gives you the ability to invoke direct methods on devices from the cloud.  The SDK supports handler for method specific and generic operation.  Click [here](https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-devguide-direct-methods) for detailed information on the IoT Hub features.                                                                                             |
| Error reporting (TBD)                                 | :large_orange_diamond: | :large_orange_diamond: | :large_orange_diamond: | :large_orange_diamond: | :large_orange_diamond: | Error reporting for exceeding quota, authentication error, throttling error, and device not found error.                                                                                                                                                                                                                                                                                           |
| SDK Options                                           | :large_orange_diamond: | :large_orange_diamond: | :large_orange_diamond: | :large_orange_diamond: | :large_orange_diamond: | Set SDK options for proxy settings, client version string, polling time, specify TrustedCert for IoT hub, Network interface selection, C2D keep alive.                                                                                                                                                                                                                                             |
| Device Provisioning Service                           | :large_orange_diamond: | :large_orange_diamond: | :large_orange_diamond: | :large_orange_diamond: | :large_orange_diamond: |                                                                                                                                                                                                                                                                                                                                                                                                    |

## How to use the Azure IoT SDKs for .NET

* **Using packages and libraries**: The simplest way to use the Azure IoT SDKs is to use packages and libraries when available. Refer to [this document](./device/doc/devbox_setup.md) on how to get Azure IoT SDKs for .NET using Nuget and build applications.
* **Clone the repository**: The repository is using [GitHub Submodules](https://git-scm.com/book/en/v2/Git-Tools-Submodules) for its dependencies. In order to automatically clone these submodules, you need to use the --recursive option as described here:
```
git clone --recursive https://github.com/Azure/azure-iot-sdk-csharp.git
```

## Samples
In the repository, you will find a set of simple samples that will help you get started:
* [Device SDK samples](./device/samples)
* [Service SDK samples](./service/Samples)

## OS platforms and hardware compatibility

The IoT Hub device SDK for .NET can be used with a broad range of OS platforms and devices.
[ATTN: CONTENT REQUIRED -- INCLUDE A LIST OF PLATFORMS SUPPORTED BY C# OUT OF BOX]

The minimum requirements are for the device platform to support the following:

- **Being capable of establishing an IP connection**: only IP-capable devices can communicate directly with Azure IoT Hub.
- **Support TLS**: required to establish a secure communication channel with Azure IoT Hub.
- **Support SHA-256** (optional): necessary to generate the secure token for authenticating the device with the service. Different authentication methods are available and not all require SHA-256.
- **Have a Real Time Clock or implement code to connect to an NTP server**: necessary for both establishing the TLS connection and generating the secure token for authentication.
- **Having at least 64KB of RAM**: the memory footprint of the SDK depends on the SDK and protocol used as well as the platform targeted. The smallest footprint is achieved targeting microcontrollers.

You can find an exhaustive list of the OS platforms the various SDKs have been tested against in the [Azure Certified for IoT device catalog](https://catalog.azureiotsuite.com/). Note that you might still be able to use the SDKs on OS and hardware platforms that are not listed on this page: all the SDKs are open sourced and designed to be portable. If you have suggestions, feedback or issues to report, refer to the Contribution and Support sections below.

<!-- ## Samples

Whithin the repository, you can find various types of simple samples that can help you get started.
Below is a complete list of all these simple samples.
In addition to these simple samples, you can find a long list of [getting started guides](https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-get-started) that describe all the steps necessary to run the simple samples on a wide variety of devices and platforms.
And if you are looking for end to end samples that show how to do simple analytics and processing of the data generated by your device using Azure services such as Stream Analytics, Big Data, Machine Learning and others, check out our [E2E samples gallery](http://aka.ms/azureiotsamples).

- C# device SDK:
   - [Simple .NET sample using AMQP](device/samples/DeviceClientAmqpSample): Shows how to connect to IoT Hub and send and receive raw messages using the AMQP protocol.
   - [Simple .NET sample using HTTP](device/samples/DeviceClientHttpSample): Shows how to connect to IoT Hub and send and receive raw messages using the HTTP protocol.
   - [Simple .NET sample using MQTT](device/samples/DeviceClientMqttSample): Shows how to connect to IoT Hub and send and receive raw messages using the MQTT protocol.
   - [Simple UWP C++ sample](device/samples/CppUWPSample): Shows how to connect to IoT Hub and send and receive raw messages in a C++ [UWP](https://msdn.microsoft.com/windows/uwp/get-started/whats-a-uwp) (Universal Windows Platform) application.
   - [Simple UWP JS sample](device/samples/JSSample): Shows how to connect to IoT Hub and send and receive raw messages in a JavaScript [UWP](https://msdn.microsoft.com/windows/uwp/get-started/whats-a-uwp) application.
   - [Simple UWP C# sample](device/samples/UWPSample): Shows how to connect to IoT Hub and send and receive raw messages in a C# [UWP](https://msdn.microsoft.com/windows/uwp/get-started/whats-a-uwp) application.
   - [Simple .NET Micro Framework 4.3 sample](device/samples/NetMFDeviceClientHttpSample_43): Shows how to connect to IoT Hub and send and receive raw messages from a device running .NET Micro Framework 4.3.
   - [Simple .NET Micro Framework 4.4 sample](device/samples/NetMFDeviceClientHttpSample_44): Shows how to connect to IoT Hub and send and receive raw messages from a device running .NET Micro Framework 4.4. -->

## Contribution, feedback and issues

If you encounter any bugs, have suggestions for new features or if you would like to become an active contributor to this project please follow the instructions provided in the [contribution guidelines](.github/CONTRIBUTING.md).

## Support

If you are having issues using one of the packages or using the Azure IoT Hub service that go beyond simple bug fixes or help requests that would be dealt within the issues section of this project, the Microsoft Customer Support team will try and help out on a best effort basis.
To engage Microsoft support, you can create a support ticket directly from the [Azure portal](https://ms.portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade).
Escalated support requests for Azure IoT Hub SDKs development questions will only be available Monday thru Friday during normal coverage hours of 6 a.m. to 6 p.m. PST.
Here is what you can expect Microsoft Support to be able to help with:
- **SDKs issues**: If you are trying to compile and run the libraries on a supported platform, the Support team will be able to assist with troubleshooting or questions related to compiler issues and communications to and from the IoT Hub.  They will also try to assist with questions related to porting to an unsupported platform, but will be limited in how much assistance can be provided.  The team will be limited with trouble-shooting the hardware device itself or drivers and or specific properties on that device. 
- **IoT Hub / Connectivity Issues**: Communication from the device client to the Azure IoT Hub service and communication from the Azure IoT Hub service to the client.  Or any other issues specifically related to the Azure IoT Hub.
- **Portal Issues**: Issues related to the portal, that includes access, security, dashboard, devices, Alarms, Usage, Settings and Actions.
- **REST/API Issues**: Using the IoT Hub REST/APIs that are documented in the [documentation](https://docs.microsoft.com/en-us/rest/api/iothub/).

## Read more
* [Azure IoT Hub documentation][iot-hub-documentation]
* [Set up IoT Hub](doc/setup_iothub.md) describes how to configure your Azure IoT Hub service.
* [Manage IoT Hub](doc/manage_iot_hub.md) describes how to provision devices in your Azure IoT Hub service.
* [FAQ](doc/faq.md) contains frequently asked questions about the SDKs and libraries.
* [Azure Certified for IoT device catalog](https://catalog.azureiotsuite.com/)
* [Set up your development environment](./device/doc/devbox_setup.md) to prepare your development environment as well as how to run the samples on Linux, Windows or other platforms.
* [API reference documentation for .NET](https://docs.microsoft.com/en-us/dotnet/api/overview/azure/devices?view=azure-dotnet)
* [Get Started with IoT Hub using .NET](https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-csharp-csharp-getstarted)

## SDK folder structure
[ATTN:CONTENT REQUIRED - need a short description of what is in each folder. Bullets under device are not complete or necessarily accurate.] 

### /device

Contains Azure IoT Hub client components that provide the raw messaging capabilities of the library. Refer to the API documentation and samples for information on how to use it.

   * build: build scripts.
   * doc: contains requirements, designs notes, manuals.
   * Microsoft.Azure.Client.Devices.* : client libraries solutions and source files.
   * samples: contains simple samples.
   * tests: unit and end-to-end tests for source code.

### /doc

Contains application development guides and device setup instructions.

### /e2e

Contains end-to-end tests for source code.

### /jenkins

### /provisioning

### /security

### /service

Contains libraries that enable interactions with the IoT Hub service to perform operations such as sending messages to devices and managing the device identity registry.

### /shared

### /tools/DeviceExplorer

### /transport

# Long Term Support

The project offers a Long Term Support (LTS) version to allow users that do not need the latest features to be shielded from unwanted changes.

A new LTS version will be created every 6 months. The lifetime of an LTS branch is currently planned for one year. LTS branches receive all bug fixes that fall in one of these categories:

- security bugfixes
- critical bugfixes (crashes, memory leaks, etc.)

No new features or improvements will be picked up in an LTS branch.

LTS branches are named lts_*mm*_*yyyy*, where *mm* and *yyyy* are the month and year when the branch was created. An example of such a branch is *lts_07_2017*.

## Schedule<sup>1</sup>

Below is a table showing the mapping of the LTS branches to the packages released

| Nuget Package | Github Branch | LTS Status | LTS Start Date | Maintenance End Date | Removed Date |
| :-----------: | :-----------: | :--------: | :------------: | :------------------: | :----------: |
| 1.x.x         | lts_07_2017   | Active     | 2017-07-01     | 2017-12-31           | 2018-06-30   |

* <sup>1</sup> All scheduled dates are subject to change by the Azure IoT SDK team.

### Planned Release Schedule
![](./lts_branches.png)

---
This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/). For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

[iot-hub-documentation]: https://docs.microsoft.com/en-us/azure/iot-hub/
[iot-dev-center]: http://azure.com/iotdev
[azure-iot-sdks]: https://github.com/azure/azure-iot-sdks
[dotnet-api-reference]: https://docs.microsoft.com/en-us/dotnet/api/overview/azure/devices?view=azure-dotnet
[devbox-setup]: ./device/doc/devbox_setup.md
[get-started-dotnet]: https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-csharp-csharp-getstarted
