# Azure-WebJob-NodeJS-Boilerplate
Fork and go...

The basics that are needed to get up and running with a Azure WebJob that runs NodeJS.

# Cron Job Settings
The settings.job is defaulted to run every 15 minutes. Some light reading on how to change that.
https://en.wikipedia.org/wiki/Cron

Note: when deploying a WebJob from Visual Studio, make sure to mark your settings.job file properties as 'Copy if newer'.

# Delete a WebJob
Open this URL: https://`{yoursitename}`.scm.azurewebsites.net/DebugConsole
Or use WebMatrix and open your web app.

Then go to the folder path: data\jobs\\`{jobType}`
The job type can be `continuous` or `triggered`
