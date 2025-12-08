# Log_Monitoring_Correction_Project.

![image atl](https://github.com/oma576/Log_Monitoring_Correction_Project./blob/80b3059f9b51f6b0e9b6db1244c68f7c3e3c6c23/Screen%20Shot%202025-12-08%20at%2012.53.09%20PM.png)

![image atl](https://github.com/oma576/Log_Monitoring_Correction_Project./blob/cc3d963a2c9030f24bc0f4b0c8251e2c2843e69d/Screen%20Shot%202025-12-08%20at%2012.50.37%20PM.png)

## Failure Point

`sudo systemctl restart rsyslog`

## Root cause analysis

The integrity check failed because the Tripwire database had never been initialized. The rsyslog configuration failed because the service was not restarted, rendering the configuration inert.
