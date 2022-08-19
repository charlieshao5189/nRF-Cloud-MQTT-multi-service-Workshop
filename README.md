# nRF-Cloud-MQTT-multi-service-Workshop
Workshop based on NCS2.0.0 sample nRF9160: nRF Cloud MQTT multi-service

## Workshop Steps

### Step 1 - Send Welcome message to nRF Cloud
```shell
diff --git a/prj.conf b/prj.conf
index a07c7d5..8b437c2 100644
--- a/prj.conf
+++ b/prj.conf
@@ -50,12 +50,12 @@ CONFIG_STREAM_FLASH_ERASE=y
 CONFIG_LOCATION=y
 CONFIG_LOCATION_METHOD_GNSS=y
 CONFIG_LOCATION_METHOD_CELLULAR=y
-CONFIG_NRF_CLOUD_AGPS=y
+CONFIG_NRF_CLOUD_AGPS=n
 CONFIG_NRF_CLOUD_CELL_POS=y
 CONFIG_MULTICELL_LOCATION_SERVICE_NRF_CLOUD=y
 CONFIG_MODEM_INFO=y
 CONFIG_MODEM_INFO_ADD_NETWORK=y
-CONFIG_NRF_CLOUD_PGPS=y
+CONFIG_NRF_CLOUD_PGPS=n
 CONFIG_NRF_CLOUD_PGPS_REPLACEMENT_THRESHOLD=4
 CONFIG_NRF_CLOUD_PGPS_REQUEST_UPON_INIT=y

diff --git a/src/application.c b/src/application.c
index ff29246..58f13e6 100644
--- a/src/application.c
+++ b/src/application.c
@@ -220,6 +220,8 @@ void main_application(void)
                LOG_WRN("Failed to determine valid date time. Proceeding anyways");
        } else {
                LOG_INF("Current date and time determined");
+               LOG_INF("Welcome to this Workshop! See this message on nRF Cloud Terminal");
+               send_sensor_sample("Welcome to this Workshop!",0);
        }

        /* Begin tracking location at the configured interval. */
```

![image](pics/nrfcloudterminal_welcome.png)
