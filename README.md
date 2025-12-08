# Log_Monitoring_Correction_Project.

## Failure Point

`sudo systemctl restart rsyslog`

## Root cause analysis

The integrity check failed because the Tripwire database had never been initialized. The rsyslog configuration failed because the service was not restarted, rendering the configuration inert.
