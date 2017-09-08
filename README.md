# Serilog.Sinks.GoogleCloudLogging

Serilog sink that writes events to [Google Cloud Platform Stackdriver Logging](https://cloud.google.com/logging/).

### Getting started

Install [package](https://www.nuget.org/packages/Serilog.Sinks.GoogleCloudLogging/) from Nuget:

```
   Install-Package Serilog.Sinks.GoogleCloudLogging
```

Configure logger:

```csharp
var log = new LoggerConfiguration()
    .WriteTo.GoogleCloudLogging(new GoogleCloudLoggingSinkOptions("YOUR_PROJECT_ID"))
    .CreateLogger();
```

### Sink options:

Name | Description
------------ | -------------
`ProjectId` | Required - Google Cloud project ID where logs will be sent to.
`ResourceType` | Resource type for logs, defaults to "global".
`LogName` | Name of log. Will automatically use SourceContext from Serilog events or fallback to this setting, defaults to "Default".
`Labels` | Dictionary of string keys and values added to all logs. Individual log entries will automatically add `Properties` from Serilog events.

When using default options, logs will appear under these filter settings in the GCP Console:

![](https://i.imgur.com/azT3uDE.png)
