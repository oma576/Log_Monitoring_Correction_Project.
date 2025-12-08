# Log_Monitoring_Correction_Project.

![image atl](https://github.com/oma576/Log_Monitoring_Correction_Project./blob/a7318c7a21c8f8536c5aa4e3465f3a7ab69d3535/Screen%20Shot%202025-12-08%20at%2012.30.46%20PM.png)

## Failure Point

`sudo systemctl restart rsyslog`

## Root cause analysis

The integrity check failed because the Tripwire database had never been initialized. The rsyslog configuration failed because the service was not restarted, rendering the configuration inert.
