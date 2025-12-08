# Log_Monitoring_Correction_Project.

### Part 1: Configure and Investigate the Linux Log File

![image atl](https://github.com/oma576/Log_Monitoring_Correction_Project./blob/e35838d4d432eabef25ba2b2926a68bba3f56061/Screen%20Shot%202025-12-08%20at%2012.56.44%20PM.png)

![image atl](https://github.com/oma576/Log_Monitoring_Correction_Project./blob/cc3d963a2c9030f24bc0f4b0c8251e2c2843e69d/Screen%20Shot%202025-12-08%20at%2012.50.37%20PM.png)

![image atl](https://github.com/oma576/Log_Monitoring_Correction_Project./blob/6b01e326bb425c1891010d99a6d9bd52c7f48ccf/Screen%20Shot%202025-12-08%20at%2012.56.44%20PM.png)

### Part 2: Configure Tripwire

![image atl](https://github.com/oma576/Log_Monitoring_Correction_Project./blob/ddfd8ea014219bb64dc4cb2151af05ec50d771df/Screen%20Shot%202025-12-08%20at%201.06.57%20PM.png)

### Part 3: Configure Rootkit Hunter

![image atl](https://github.com/oma576/Log_Monitoring_Correction_Project./blob/7714510b8aec5fa5eee150501afd35bd45ee4930/Screen%20Shot%202025-12-08%20at%201.22.20%20PM.png)

![image atl](https://github.com/oma576/Log_Monitoring_Correction_Project./blob/65cbd8727b48224f2999ba97f9a3cd3da0df7b44/Screen%20Shot%202025-12-08%20at%201.23.22%20PM.png)

![image atl](https://github.com/oma576/Log_Monitoring_Correction_Project./blob/d6df77abcfac35650b4de97c9d8e2ef798e0a369/Screen%20Shot%202025-12-08%20at%201.23.32%20PM.png)

## Part 2: Configure Tripwire
```
sudo systemctl restart rsyslog
systemctl status rsyslog
```

![image atl](https://github.com/oma576/Log_Monitoring_Correction_Project./blob/bfe6817ae908b57596c5f855b7a2c160fc4753c9/Screen%20Shot%202025-12-08%20at%204.20.51%20PM.png)

```
sudo tripwire --init
```

![image atl](https://github.com/oma576/Log_Monitoring_Correction_Project./blob/44e7d8dba4070c10416fc65e6adc9b668a293637/Screen%20Shot%202025-12-08%20at%204.21.04%20PM.png)

```
sudo tripwire --check
```

![image atl](https://github.com/oma576/Log_Monitoring_Correction_Project./blob/5852596f26064aa4ca58714a6281149e874a9313/Screen%20Shot%202025-12-08%20at%204.22.18%20PM.png)

## Failure Point
```
sudo systemctl restart rsyslog
```
## Root cause analysis

The integrity check failed because the Tripwire database had never been initialized. The rsyslog configuration failed because the service was not restarted, rendering the configuration inert.
