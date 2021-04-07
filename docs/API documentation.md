# BeSmart API v1 Reverse engineering

<!-- @import "[TOC]" {cmd="toc" depthFrom=1 depthTo=6 orderedList=false} -->

## Login
|Item|Value |
|----|------|
|Protocol| http or https|
|host|api.besmart-home.com|
|Verb|GET   |
|URI |/BeSMART_release/v1/api/iOS/users/login_new?username=`username`&password=`password`&Random=`random float number between 0 and 1` |
|Return type|JSON|
|Example|<code>{<br>&nbsp;"status": true,<br>&nbsp;"message": {<br>&nbsp;&nbsp;"wifi_box": {<br>&nbsp;&nbsp;&nbsp;"id": "_wifi_box_id_",<br>&nbsp;&nbsp;&nbsp;"online": "1"<br>&nbsp;&nbsp;},<br>&nbsp;&nbsp;"thermostat": [<br>&nbsp;&nbsp;&nbsp;{<br>&nbsp;&nbsp;&nbsp;&nbsp;"id": "_thermostat_1_id_",<br>&nbsp;&nbsp;&nbsp;&nbsp;"online": "1",<br>&nbsp;&nbsp;&nbsp;&nbsp;"name": "_thermostat_1_name_",<br>&nbsp;&nbsp;&nbsp;&nbsp;"model": "5",<br>&nbsp;&nbsp;&nbsp;&nbsp;"comfort_temp": "22.0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"economy_temp": "18.0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"frost_temp": "6.0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"current_temp": "21.4",<br>&nbsp;&nbsp;&nbsp;&nbsp;"target_temp": "18.0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"mode": "0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"season": "1",<br>&nbsp;&nbsp;&nbsp;&nbsp;"battery_power": "0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"unit": "0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"heating_status": "0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"heating_enable": "0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"advance": "0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"booster": "0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"max_heating_set_point": "80.0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"min_heating_set_point": "30.0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"sensor_influence": "10",<br>&nbsp;&nbsp;&nbsp;&nbsp;"climatic_curve": "1.2",<br>&nbsp;&nbsp;&nbsp;&nbsp;"central_heating_thermostat_OT_set_point": "5",<br>&nbsp;&nbsp;&nbsp;&nbsp;"dhw_active": "0"<br>&nbsp;&nbsp;&nbsp;},<br>&nbsp;&nbsp;&nbsp;{<br>&nbsp;&nbsp;&nbsp;&nbsp;"id": "_thermostat_2_id_",<br>&nbsp;&nbsp;&nbsp;&nbsp;"online": "1",<br>&nbsp;&nbsp;&nbsp;&nbsp;"name": "_thermostat_2_name_",<br>&nbsp;&nbsp;&nbsp;&nbsp;"model": "5",<br>&nbsp;&nbsp;&nbsp;&nbsp;"comfort_temp": "21.0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"economy_temp": "18.0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"frost_temp": "6.0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"current_temp": "21.4",<br>&nbsp;&nbsp;&nbsp;&nbsp;"target_temp": "18.0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"mode": "0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"season": "1",<br>&nbsp;&nbsp;&nbsp;&nbsp;"battery_power": "0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"unit": "0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"heating_status": "0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"heating_enable": "0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"advance": "0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"booster": "0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"max_heating_set_point": "80.0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"min_heating_set_point": "30.0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"sensor_influence": "10",<br>&nbsp;&nbsp;&nbsp;&nbsp;"climatic_curve": "1.2",<br>&nbsp;&nbsp;&nbsp;&nbsp;"central_heating_thermostat_OT_set_point": "5",<br>&nbsp;&nbsp;&nbsp;&nbsp;"dhw_active": "0"<br>&nbsp;&nbsp;&nbsp;}<br>&nbsp;&nbsp;],<br>&nbsp;&nbsp;"boiler": {<br>&nbsp;&nbsp;&nbsp;"online": "1",<br>&nbsp;&nbsp;&nbsp;"model": "2",<br>&nbsp;&nbsp;&nbsp;"mode": "0",<br>&nbsp;&nbsp;&nbsp;"dhw_current_temp": "26.0",<br>&nbsp;&nbsp;&nbsp;"heating_enable": "1"<br>&nbsp;&nbsp;}<br>&nbsp;},<br>&nbsp;"error_code": 0<br>}</code>|

----
## Boiler status

|Item|Value |
|----|------|
|Protocol| http or https|
|host|api.besmart-home.com|
|Verb|GET   |
|URI |/BeSMART_release/v1/api/Android/Boilers/data/user_id/`user_id`/wifi_box_id/`wifi_box_id`/token/`token` |
|Return type|JSON|
|Example|<code>{<br>&nbsp;"status": true,<br>&nbsp;"message": {<br>&nbsp;&nbsp;"heating_current_temp": "30.0",<br>&nbsp;&nbsp;"heating_target_temp": "5.0",<br>&nbsp;&nbsp;"outdoor_probe_temp": "3",<br>&nbsp;&nbsp;"dhw_current_temp": "26.0",<br>&nbsp;&nbsp;"dhw_target_temp": "45",<br>&nbsp;&nbsp;"system_pressure": "1.0",<br>&nbsp;&nbsp;"error": {<br>&nbsp;&nbsp;&nbsp;"status": "0",<br>&nbsp;&nbsp;&nbsp;"lock": "0",<br>&nbsp;&nbsp;&nbsp;"code": "0"<br>&nbsp;&nbsp;},<br>&nbsp;&nbsp;"flame_status": "0",<br>&nbsp;&nbsp;"heating_status": "0",<br>&nbsp;&nbsp;"heating_enable": "1",<br>&nbsp;&nbsp;"work_mode": "0",<br>&nbsp;&nbsp;"program_enable": "255",<br>&nbsp;&nbsp;"OT_cmd_stand_num": "0",<br>&nbsp;&nbsp;"dhw_active": "0",<br>&nbsp;&nbsp;"unit": "0",<br>&nbsp;&nbsp;"Relay_status": "1",<br>&nbsp;&nbsp;"country": "_country_",<br>&nbsp;&nbsp;"city": "_city_",<br>&nbsp;&nbsp;"temp_src": "2"<br>&nbsp;},<br>&nbsp;"error_code": 0<br>}</code>|
----
## Thermostat status

|Item|Value |
|----|------|
|Protocol| http or https|
|host|api.besmart-home.com|
|Verb|GET   |
|URI |/BeSMART_release/v1/api/Android/Thermostats/data/user_id/`user_id`/wifi_box_id/`wifi_box_id`/token/`token`/thermostat_id/`thermostat_id` |
|Return type|JSON|
|Example|<code>{<br>&nbsp;"status": true,<br>&nbsp;"message": {<br>&nbsp;&nbsp;"comfort_temp": "22.0",<br>&nbsp;&nbsp;"economy_temp": "18.0",<br>&nbsp;&nbsp;"frost_temp": "6.0",<br>&nbsp;&nbsp;"current_temp": "21.4",<br>&nbsp;&nbsp;"target_temp": "18.0",<br>&nbsp;&nbsp;"mode": "0",<br>&nbsp;&nbsp;"model": "5",<br>&nbsp;&nbsp;"season": "1",<br>&nbsp;&nbsp;"battery_power": "0",<br>&nbsp;&nbsp;"unit": "0",<br>&nbsp;&nbsp;"cmd_stand_status": "0",<br>&nbsp;&nbsp;"heating_status": "0",<br>&nbsp;&nbsp;"heating_enable": "0",<br>&nbsp;&nbsp;"dhw_active": "0",<br>&nbsp;&nbsp;"advance": "0",<br>&nbsp;&nbsp;"booster": "0",<br>&nbsp;&nbsp;"holiday_end_time": "0",<br>&nbsp;&nbsp;"RFSignal": "132.0",<br>&nbsp;&nbsp;"current_setpoint": "5",<br>&nbsp;&nbsp;"CoolComfortTemp": "-9999",<br>&nbsp;&nbsp;"CoolEcnomicTemp": "-9999",<br>&nbsp;&nbsp;"Online": "1",<br>&nbsp;&nbsp;"RelayCooling": "0",<br>&nbsp;&nbsp;"RelayFan": "0",<br>&nbsp;&nbsp;"RelayHeating": "1",<br>&nbsp;&nbsp;"country": "Italia",<br>&nbsp;&nbsp;"city": "Collegno",<br>&nbsp;&nbsp;"temp_src": "2",<br>&nbsp;&nbsp;"boiler": {<br>&nbsp;&nbsp;&nbsp;"online": "1",<br>&nbsp;&nbsp;&nbsp;"model": "2",<br>&nbsp;&nbsp;&nbsp;"heating_enable": "1",<br>&nbsp;&nbsp;&nbsp;"error": {<br>&nbsp;&nbsp;&nbsp;&nbsp;"status": "0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"lock": "0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"code": "0"<br>&nbsp;&nbsp;&nbsp;},<br>&nbsp;&nbsp;&nbsp;"work_mode": "0",<br>&nbsp;&nbsp;&nbsp;"dhw_current_temp": "25.0",<br>&nbsp;&nbsp;&nbsp;"outdoor_probe_temp": "3"<br>&nbsp;&nbsp;},<br>&nbsp;&nbsp;"program": [<br>&nbsp;&nbsp;&nbsp;[<br>&nbsp;&nbsp;&nbsp;&nbsp;_Day 0: list of program id (0 - frost,1 - economy,2 - comfort), one each 1/2 hour_<br>&nbsp;&nbsp;&nbsp;],<br>&nbsp;&nbsp;&nbsp;...<br>&nbsp;&nbsp;&nbsp;[<br>&nbsp;&nbsp;&nbsp;&nbsp;_Day 6: list of program id (0 - frost,1 - economy,2 - comfort), one each 1/2 hour_<br>&nbsp;&nbsp;&nbsp;],<br>&nbsp;&nbsp;],<br>&nbsp;&nbsp;"max_heating_set_point": "80.0",<br>&nbsp;&nbsp;"min_heating_set_point": "30.0",<br>&nbsp;&nbsp;"sensor_influence": "10",<br>&nbsp;&nbsp;"climatic_curve": "1.2",<br>&nbsp;&nbsp;"central_heating_thermostat_OT_set_point": "5"<br>&nbsp;},<br>&nbsp;"error_code": 0<br>}</code>|
----
## Wifi Box status (and list of all attached things)

|Item|Value |
|----|------|
|Protocol| http or https|
|host|api.besmart-home.com|
|Verb|GET   |
|URI |/BeSMART_release/v1/api/Android/Wifi_boxes/data/user_id/`user_id`/wifi_box_id/`wifi_box_id`/token/`token` |
|Return type|JSON|
|Example|<code>{<br>&nbsp;"status": true,<br>&nbsp;"message": {<br>&nbsp;&nbsp;"wifi_box": {<br>&nbsp;&nbsp;&nbsp;"id": "_wifi_box_id_",<br>&nbsp;&nbsp;&nbsp;"online": "1"<br>&nbsp;&nbsp;},<br>&nbsp;&nbsp;"thermostat": [<br>&nbsp;&nbsp;&nbsp;{<br>&nbsp;&nbsp;&nbsp;&nbsp;"id": "_thermostat_1_id_",<br>&nbsp;&nbsp;&nbsp;&nbsp;"online": "1",<br>&nbsp;&nbsp;&nbsp;&nbsp;"name": "_thermostat_1_name_",<br>&nbsp;&nbsp;&nbsp;&nbsp;"model": "5",<br>&nbsp;&nbsp;&nbsp;&nbsp;"comfort_temp": "22.0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"economy_temp": "18.0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"frost_temp": "6.0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"current_temp": "21.4",<br>&nbsp;&nbsp;&nbsp;&nbsp;"target_temp": "18.0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"mode": "0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"season": "1",<br>&nbsp;&nbsp;&nbsp;&nbsp;"battery_power": "0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"unit": "0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"heating_status": "0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"heating_enable": "0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"advance": "0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"booster": "0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"max_heating_set_point": "80.0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"min_heating_set_point": "30.0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"sensor_influence": "10",<br>&nbsp;&nbsp;&nbsp;&nbsp;"climatic_curve": "1.2",<br>&nbsp;&nbsp;&nbsp;&nbsp;"central_heating_thermostat_OT_set_point": "5",<br>&nbsp;&nbsp;&nbsp;&nbsp;"dhw_active": "0"<br>&nbsp;&nbsp;&nbsp;},<br>&nbsp;&nbsp;&nbsp;{<br>&nbsp;&nbsp;&nbsp;&nbsp;"id": "_thermostat_2_id_",<br>&nbsp;&nbsp;&nbsp;&nbsp;"online": "1",<br>&nbsp;&nbsp;&nbsp;&nbsp;"name": "_thermostat_2_name_",<br>&nbsp;&nbsp;&nbsp;&nbsp;"model": "5",<br>&nbsp;&nbsp;&nbsp;&nbsp;"comfort_temp": "21.0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"economy_temp": "18.0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"frost_temp": "6.0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"current_temp": "21.4",<br>&nbsp;&nbsp;&nbsp;&nbsp;"target_temp": "18.0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"mode": "0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"season": "1",<br>&nbsp;&nbsp;&nbsp;&nbsp;"battery_power": "0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"unit": "0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"heating_status": "0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"heating_enable": "0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"advance": "0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"booster": "0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"max_heating_set_point": "80.0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"min_heating_set_point": "30.0",<br>&nbsp;&nbsp;&nbsp;&nbsp;"sensor_influence": "10",<br>&nbsp;&nbsp;&nbsp;&nbsp;"climatic_curve": "1.2",<br>&nbsp;&nbsp;&nbsp;&nbsp;"central_heating_thermostat_OT_set_point": "5",<br>&nbsp;&nbsp;&nbsp;&nbsp;"dhw_active": "0"<br>&nbsp;&nbsp;&nbsp;}<br>&nbsp;&nbsp;],<br>&nbsp;&nbsp;"boiler": {<br>&nbsp;&nbsp;&nbsp;"online": "1",<br>&nbsp;&nbsp;&nbsp;"model": "2",<br>&nbsp;&nbsp;&nbsp;"mode": "0",<br>&nbsp;&nbsp;&nbsp;"dhw_current_temp": "26.0",<br>&nbsp;&nbsp;&nbsp;"heating_enable": "1"<br>&nbsp;&nbsp;}<br>&nbsp;},<br>&nbsp;"error_code": 0<br>}</code>|

----
## Boiler status

|Item|Value |
|----|------|
|Protocol| http or https|
|host|api.besmart-home.com|
|Verb|GET   |
|URI |/BeSMART_release/v1/api/Android/Wifi_boxes/data/user_id/`user_id`/wifi_box_id/`wifi_box_id`/token`/ |
|Return type|JSON|
|Example|<code>{<br>&nbsp;"status": true,<br>&nbsp;"message": {<br>&nbsp;&nbsp;"heating_current_temp": "30.0",<br>&nbsp;&nbsp;"heating_target_temp": "5.0",<br>&nbsp;&nbsp;"outdoor_probe_temp": "3",<br>&nbsp;&nbsp;"dhw_current_temp": "26.0",<br>&nbsp;&nbsp;"dhw_target_temp": "45",<br>&nbsp;&nbsp;"system_pressure": "1.0",<br>&nbsp;&nbsp;"error": {<br>&nbsp;&nbsp;&nbsp;"status": "0",<br>&nbsp;&nbsp;&nbsp;"lock": "0",<br>&nbsp;&nbsp;&nbsp;"code": "0"<br>&nbsp;&nbsp;},<br>&nbsp;&nbsp;"flame_status": "0",<br>&nbsp;&nbsp;"heating_status": "0",<br>&nbsp;&nbsp;"heating_enable": "1",<br>&nbsp;&nbsp;"work_mode": "0",<br>&nbsp;&nbsp;"program_enable": "255",<br>&nbsp;&nbsp;"OT_cmd_stand_num": "0",<br>&nbsp;&nbsp;"dhw_active": "0",<br>&nbsp;&nbsp;"unit": "0",<br>&nbsp;&nbsp;"Relay_status": "1",<br>&nbsp;&nbsp;"country": "_country_",<br>&nbsp;&nbsp;"city": "_city_",<br>&nbsp;&nbsp;"temp_src": "2"<br>&nbsp;},<br>&nbsp;"error_code": 0<br>}</code>|
----
## Get weather in wifibox location
|Item|Value |
|----|------|
|Protocol| http or https|
|host|api.besmart-home.com|
|Verb|GET   |
|URI |/BeSMART_release/v1/api/Android/wifi_boxes/weather/user_id/`user_id`/wifi_box_id/`wifi_box_id`/token/`token` |
|Return type|JSON|
|Example|<code>{&nbsp;&nbsp;"status": true,<br>&nbsp;&nbsp;"message": {<br>&nbsp;&nbsp;&nbsp;"temperature": "2",<br>&nbsp;&nbsp;&nbsp;"address": "Collegno"<br>&nbsp;&nbsp;},<br>&nbsp;&nbsp;"error_code": 0<br>&nbsp;}</code>|

----
## Set thermostat mode
|Item|Value |
|----|------|
|Protocol| http or https|
|host|api.besmart-home.com|
|Verb|PUT   |
|URI |/BeSMART_release/v1/api/Android/Thermostats/mode |
|Content-Type|application/x-www-form-urlencoded|
|Form Items|<table><thead><tr><th>Item Name</th><th>Item Value</th></tr></thead><tbody><tr><td>mode</td><td><code>mode</code> (<i>see thermo modes below</i>)</td></tr><tr><td>wifi_box_id</td><td><code>wifi_box_id</code></td></tr><tr><td>user_id</td><td><code>user_id</code></td></tr><tr><td>thermostat_id</td><td><code>thermostat_id</code></td></tr><tr><td>id</td><td><code>user_id</code></td></tr><tr><td>token</td><td><code>token</code></td></tr></tbody></table>|
|Return type|JSON|
|Example OK|<code>{<br>&nbsp;"status": true,<br>&nbsp;"message": "Set successfully",<br>&nbsp;"error_code": 0<br>}</code>|
|Example KO|<code>{<br>&nbsp;"status": false,<br>&nbsp;"message": "Error Message",<br>&nbsp;"error_code": _not 0_<br>}</code>|
----
## Set thermostat temperature
|Item|Value |
|----|------|
|Protocol| http or https|
|host|api.besmart-home.com|
|Verb|PUT   |
|URI |/BeSMART_release/v1/api/Android/Thermostats/temperature |
|Content-Type|application/x-www-form-urlencoded|
|Form Items|<table><thead><tr><th>Item Name</th><th>Item Value</th></tr></thead><tbody></tr><tr><td>wifi_box_id</td><td><code>wifi_box_id</code></td></tr><tr><td>user_id</td><td><code>user_id</code></td></tr><tr><td>thermostat_id</td><td><code>thermostat_id</code></td></tr><tr><td>id</td><td><code>user_id</code></td></tr><tr><td>token</td><td><code>token</code></td></tr><tr><td>temp_mode</td><td><code>temp_mode</code> (<i>see temp modes below</i>)</td><tr><td>integer_part</td><td><code>integer part of temp to be set</code></td><tr><td>fraction_part</td><td><code>fraction part of temp to be set</code></td></tbody></table>|
|Return type|JSON|
|Example OK|<code>{<br>&nbsp;"status": true,<br>&nbsp;"message": "Set successfully",<br>&nbsp;"error_code": 0<br>}</code>|
|Example KO|<code>{<br>&nbsp;"status": false,<br>&nbsp;"message": "Error Message",<br>&nbsp;"error_code": _not 0_<br>}</code>|
----
# Constants
## Thermostat modes
|Mode|Description|
|---|---|
|0|Automatic|
|1|Manual|
|2|Economy|
|3|Party|
|4|Idle|
|5|Domestic hot water only|
---
## Temperature mode
|Mode|Description|
|---|---|
|0|Frost|
|1|Economy|
|2|Comfort|