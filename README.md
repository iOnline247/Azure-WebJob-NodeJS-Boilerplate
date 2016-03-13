# Azure-WebJob-NodeJS-Boilerplate
Fork and go...
The basics that are needed to get up and running with a Azure WebJob that runs NodeJS.
https://azure.microsoft.com/en-us/documentation/articles/websites-webjobs-resources/

### Cron Job Settings
Following the guidance [Create a scheduled WebJob using a CRON expression](https://azure.microsoft.com/en-us/documentation/articles/web-sites-create-web-jobs/#CreateScheduled) doesn't seem to work.

Some sample output from the WebJob that uses a 15 minute schedule.
``` text
[03/13/2016 04:07:35 > 8c7c50: SYS INFO] Detected WebJob file/s were updated, refreshing WebJob
[03/13/2016 04:07:35 > 8c7c50: SYS INFO] Status changed to Starting
[03/13/2016 04:07:35 > 8c7c50: SYS INFO] Run script 'a.js' with script host - 'NodeScriptHost'
[03/13/2016 04:07:35 > 8c7c50: SYS INFO] Status changed to Running
[03/13/2016 04:07:35 > 8c7c50: INFO] Azure-WebJob runs on Node version: v4.2.3
[03/13/2016 04:07:35 > 8c7c50: SYS INFO] Status changed to Success
[03/13/2016 04:07:35 > 8c7c50: SYS INFO] Process went down, waiting for 60 seconds
[03/13/2016 04:07:35 > 8c7c50: SYS INFO] Status changed to PendingRestart
[03/13/2016 04:08:35 > 8c7c50: SYS INFO] Run script 'a.js' with script host - 'NodeScriptHost'
[03/13/2016 04:08:35 > 8c7c50: SYS INFO] Status changed to Running
[03/13/2016 04:08:36 > 8c7c50: INFO] Azure-WebJob runs on Node version: v4.2.3
```
**Note:** The job fires every 60 seconds by default even with the `settings.job` file set to 15 minutes. 

The settings.job is defaulted to run every 15 minutes. Some light reading on how to change that.
https://en.wikipedia.org/wiki/Cron

**Note:** when deploying a WebJob from Visual Studio, make sure to mark your settings.job file properties as 'Copy if newer'.

### Delete a WebJob
1. Open this URL: https://`{yoursitename}`.scm.azurewebsites.net/DebugConsole or use WebMatrix and open your web app.
2. Then go to the folder path: data\jobs\\`{jobType}`
  1. The job type can be `continuous` or `triggered`
