---
id: configuration-tool-manual
title: Configuration Tool Manual
date: 2022-06-08
---



-----



## Configuration Tool Overview

WIZnet’s configuration tool enables product search, product settings, and firmware upload via the network. WIZ5xxSR-RP is compatible with WIZ107SR / WIZ108SR, WIZ750SR / WIZ750SR-1xx / WIZ750SR-12x and WIZ510SSL and uses the same configuration tool.

The WIZ5xxSR-RP configuration tool is published on the Github under the name of WIZnet-S2E-Tool-GUI. The latest version of the executable can be downloaded from the release page.

  - **Github repository: [WIZnet-S2E-Tool-GUI Github repository](https://github.com/Wiznet/WIZnet-S2E-Tool-GUI)**
  - **Download the latest version: [WIZnet-S2E-Tool-GUI Github repository: Release](https://github.com/Wiznet/WIZnet-S2E-Tool-GUI/releases)**

The following screen will appear once the program is installed and opened.

|                                                                                                                                                     |
| :-------------------------------------------------------------------------------------------------------------------------------------------------: |
| ![](https://d3cmhcsnvv7jc.cloudfront.net/docs/img/products/s2e_module/wiz5xxsr-rp/configuration_tool_manual/configuration_tool_for_wiz5xxsr-rp.png) |
|                                                   Figure: **Configuration Tool for WIZ5xxSR-RP**                                                    |

  - WIZnet-S2E-Tool-GUI is Python interpreter based and it is platform-independent.
  - If user has used one of WIZ107SR / WIZ108SR, WIZ750SR / WIZ750SR-1xx / WIZ750SR-12x or WIZ510SSL, the same program can be used for WIZ5xxSR-RP.



-----


### Support Devices

Refer to the link below for a list of supported devices.

* [**WIZnet-S2E-Tool-GUI Support Devices**](https://github.com/Wiznet/WIZnet-S2E-Tool-GUI#support-devices)


-----



## Configuration Tool Layout

|                                                                                                                                            |
| :----------------------------------------------------------------------------------------------------------------------------------------: |
| ![](https://d3cmhcsnvv7jc.cloudfront.net/docs/img/products/s2e_module/wiz5xxsr-rp/configuration_tool_manual/configuration_tool_layout.png) |
|                                                   Figure: **Configuration Tool layout**                                                    |

The configuration tool is composed of four sections. Details of each section are available below.



#### ① Icon Menu

  - Device search, save settings, firmware upload, device reset and Etc.



#### ② Network Interface configuration

  - If using multiple network adapters, select the band to use



#### ③ Device List

  - Lists the information of searched devices on the network



#### ④ Search method

  - Device search method
  - Default: UDP broadcast



#### ⑤ Status bar

  - Configuration Tool's working status



#### ⑥ General options

  - Device's general options
  - Basic settings / Options / User I/O tab (WIZ750SR)



#### ⑦ Each channel options

  - Options for each channel. If the device has more than 1 channel, it will display a multi-channel tab.



-----



## Configuration Tool Details



### 1. Icon Menu

|                                                                                                                             |
| :-------------------------------------------------------------------------------------------------------------------------: |
| ![](https://d3cmhcsnvv7jc.cloudfront.net/docs/img/products/s2e_module/wiz5xxsr-rp/configuration_tool_manual/menu_icons.png) |
|                                                   Figure: **Menu icons**                                                    |



#### 1\) Device Search

  - Searches for WIZ5xxSR-RP on the same network.
  - Search can be done via [UDP Broadcast](https://en.wikipedia.org/wiki/Broadcasting_\(networking\)) or [TCP Unicast](https://en.wikipedia.org/wiki/Unicast)
  - Use **TCP/UDP port 50001** to search WIZ5xxSR-RP. Search can be unsuccessful due to firewall or virus protection software.
    - In this case, try to search after turning off the firewall or virus protection software.



#### 2\) Apply Settings

  - Save the settings for WIZ5xxSR-RP.
  - The settings will be applied through the configuration tool.
  - Then the module will automatically reboot.

1.  UDP Broadcast Search: can search multiple devices

2.  TCP Unicast Search: can search only one device



#### 3\) Firmware Upload

  - Use the firmware binary file provided from WIZnet to update WIZ5xxSR-RP’s firmware
  - Then the module will automatically reboot.
  - The following pop-up will appear once the firmware upload is complete.
  - Use **TCP/UDP port 50002 to upload firmware** on to WIZ5xxSR-RP.
    Firmware upload can be unsuccessful due to firewall or virus protection software.
    - In this case, try to upload after turning off the firewall or virus protection software.
  - The module will not work properly if the firmware is not correctly uploaded.

**DO NOT TURN OFF POWER DURING FIRMWARE UPLOADING**  
**IT CAN CAUSE MALFUNCTIONING**



#### 4\) Reset Device

  - Reboots WIZ5xxSR-RP.



#### 5\) Factory Reset

  - Returns the settings of WIZ5xxSR-RP to factory default.
  - Factory default setting of can be checked at WIZ5xxSR-RP Factory Settings.
  - Then the module will automatically reboot.



#### 6\) Save Config

  - Saves current device's settings to a file.
  - When the environment changes or you want to apply the current device settings to another device.



#### 7\) Load Config

  - Load the settings of the file saved with Save Config.
  - After loading the settings, press the **Apply Settings** button to apply the device.



#### 8\) Exit

  - Ends the configuration tool.



### 2\. Network Interface configuration

|                                                                                                                                   |
| :-------------------------------------------------------------------------------------------------------------------------------: |
| ![](https://d3cmhcsnvv7jc.cloudfront.net/docs/img/products/s2e_module/wiz5xxsr-rp/configuration_tool_manual/network_adapters.png) |
|                                                   Figure: **Network adapters**                                                    |

  - If using multiple types of network adapters, a list of adapters and the bands in use are displayed and can be selected according to your environment.
    - Example 1) If your laptop is using both Ethernet and Wi-Fi
    - Example 2) Using Virtual Machine



### 3\. Device List

|                                                                                                                              |
| :--------------------------------------------------------------------------------------------------------------------------: |
| ![](https://d3cmhcsnvv7jc.cloudfront.net/docs/img/products/s2e_module/wiz5xxsr-rp/configuration_tool_manual/device_list.png) |
|                                                   Figure: ***Device list**                                                   |

  - List of devices searched will appears.
    - **Searched results** shows the number of devices searched.
    - Each device is identified by its MAC address and device name.



### 4\. Search Method



#### Search ID code

  - This section is for inputting code when the search identification code is set.
  - If this option is selected, the assigned code must be entered when searching devices.



#### Search method

  - Search can be done via [UDP Broadcast](https://en.wikipedia.org/wiki/Broadcasting_\(networking\)) or [TCP Unicast](https://en.wikipedia.org/wiki/Unicast)
    - UDP Broadcast Search: can search multiple devices
    - TCP Unicast Search: can search only one device



### 5\. Status bar

  - Shows the result of the search.
    - MAC addresses will be shown together if multiple devices are searched.
  - The progress bar is shown during firmware updates.



### 6-1. Basic settings Tab

|                                                                                                                                     |
| :---------------------------------------------------------------------------------------------------------------------------------: |
| ![](https://d3cmhcsnvv7jc.cloudfront.net/docs/img/products/s2e_module/wiz5xxsr-rp/configuration_tool_manual/basic_settings_tab.png) |
|                                                   Figure: **Basic settings tab**                                                    |



#### 1\) Device information

  - Shows the current **firmware version**
  - Composed of three sections: **Major version number**, **Minor version number**, and **Maintenance version number** ex) v1.0.0



#### 2\) Search identification code

  - **Range: Up to 8-bytes string**
    - Default: Null (Not used)
  - The search identification code is for identifying the device search.
  - If this option is selected, the assigned code must be entered when searching devices.



#### 3\) Network configuration

  - **Static** (default)
    - By selecting this option, users can enter the IP address, subnet mask, gateway address, DNS server.
  - **DHCP**
    - By selecting this option, all information is automatically allocated from the router (DHCP server).
  - PPPoE mode is not supported.



### 6-2. Options Tab

|                                                                                                                              |
| :--------------------------------------------------------------------------------------------------------------------------: |
| ![](https://d3cmhcsnvv7jc.cloudfront.net/docs/img/products/s2e_module/wiz5xxsr-rp/configuration_tool_manual/options_tab.png) |
|                                                   Figure: **Options tab**                                                    |



#### 1\) TCP Timeout

  - TCP retransmission retry count setting
  - Value: 1\~255



#### 2\) Status pin

  - Set status I/O pin S0(PA\_10) and S1(PA\_01) operation mode



#### 3\) Serial debug

  - **Enable debug message output**
    - By enabling this option, the product information or error status can be printed via the Debug UART.
    - The serial settings of the Debug UART is fixed as **115200-8-N-1:None**.
    - User can monitor S2E(Serial to Ethernet) or E2S(Ethernet to Serial) data when the **Enable with Data** option is set. (Available since WIZ5xxSR-RP v1.2.2 or later)

1.  Stable version is recommended for usage. Ex) Development version: v1.0.0dev, Stable version: v1.0.0

2.  In cases when there are multiple devices in the same network.



#### 4\) Serial command mode

  - By enabling this option, the data communication mode (GW mode) will change to serial command mode (AT mode) when sending the **command mode switch code** via the serial data port.
    - Default: Enabled
  - Use the serial command mode composed of 2-byte to change settings.
  - The existing TCP connection will be lost if the mode changes to serial command mode.
  - **Serial command mode switch code: Trigger code**
    - This is a 3-byte code for switching the mode from data mode to serial command mode.
        - Default: \[2B\]\[2B\]\[2B\] (+++)
    - Each byte value reads hex code only.

:::info
**Please take caution of the following when using Trigger code.**

1. It can only be recognized as switch code if there is a time gap of at least 500ms of no data communication time before and after the 3-byte command mode switch.

2. The time interval for each byte of the 3-byte command mode switch code has to be at most 500ms.

3. Do not end the command mode switch code with CR((CR: Carriage return, ('\\r', 0x0D) )) or LF((LF: Line feed, ('\\n', 0x0A) )).

4. The default interval of the time gap before and after the command mode switch code is 500ms. The operation is based on the timer value of the serial data packaging option.
:::


#### 5\) Connection password (TCP server mode only)

  - **Range: Up to 8-bytes string**
    - Default: Null (Not used)
  - Connection password is available for **TCP server mode** (including TCP server mode of the mixed mode).
  - TCP client must send the connection password character upon connecting to WIZ5xxSR-RP in order for data communication.
  - TCP connection will be disconnected if the password does not match



### 6-3. MQTT Options Tab

|                                                                                                                                   |
| :-------------------------------------------------------------------------------------------------------------------------------: |
| ![](https://d3cmhcsnvv7jc.cloudfront.net/docs/img/products/s2e_module/wiz5xxsr-rp/configuration_tool_manual/mqtt_options_tab.png) |
|                                                   Figure: **MQTT options tab**                                                    |



#### 1) MQTT Credentials

  - Username, password:
    - Max size is 128
    - Can be blank



#### 2) MQTT Options

  - Client ID:
    - Max size is 128
    - Can be blank (but not recommended)
  - Keep Alive:
    - Set 0 to disable
    - Range 0 ~ 65535
  - QoS:
    - Select from drop-down menu (0,1 or 2)



#### 3) MQTT Topics

  - Publish Topic
    - Max 128
  - Subscribe Topic
    - Max 128
    - Up to 3 subscribe topics



### 6-4. Certificate Manager Tab

|                                                                                                                                          |
| :--------------------------------------------------------------------------------------------------------------------------------------: |
| ![](https://d3cmhcsnvv7jc.cloudfront.net/docs/img/products/s2e_module/wiz5xxsr-rp/configuration_tool_manual/certificate_manager_tab.png) |
|                                                   Figure: **Certificate manager tab**                                                    |



#### 1) Root CA

  - Root CA Option: None, Optional, Verify
  - Load File: click to open file explorer window and select Root CA file
  - Save to device: click to save to device



#### 2) Client Certificate

  - Enable check box: Check to enable
  - Load File: click to open file explorer window and select Root CA file
  - Save to device: click to save to device



#### 3) Private Key

  - Load File: click to open file explorer window and select Root CA file
  - Save to device: click to save to device



### 7\. Channel Tab

|                                                                                                                              |
| :--------------------------------------------------------------------------------------------------------------------------: |
| ![](https://d3cmhcsnvv7jc.cloudfront.net/docs/img/products/s2e_module/wiz5xxsr-rp/configuration_tool_manual/channel_tab.png) |
|                                                   Figure: **Channel tab**                                                    |

  - The serial command after switching modes must end with CR and LF.



#### 1\) Status & Serial Interface

|        Item         | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| :-----------------: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|      Status[1]      | Shows the operational status of the device<br />- <strong>BOOT</strong>: Settings and firmware upload is possible during this status<br />- <strong>OPEN</strong>: Status before TCP connection<br />- <strong>CONNECT</strong>: Status after TCP connection<br />- <strong>UPGRADE</strong>: Firmware update or DHCP IP allocation during this status<br />- <strong>ATMODE</strong>: Serial AT command mode.<br />- <strong>UDP</strong>: UDP mode<br /> |
| Serial interface[2] | Shows the types of UART interfaces.<br />- <strong>RS-232/TTL</strong>: WIZ5xxSR-RP hardware TTL or RS-232 version.<br />- <strong>RS-422/485</strong>: WIZ5xxSR-RP hardware RS-422/485 version.                                                                                                                                                                                                                                                           |

  - Difference between WIZ107/108SR is the addition of BOOT and UDP mode.
  - Difference between WIZ107/108SR is the number of UART interfaces.
  - TCP client mode includes the TCP client mode of the TCP mixed mode.



#### 2\) Operation mode

  - Setting for the network operation mode.
  - Users can choose among the seven options that suits their application: TCP client mode, TCP server mode (default), TCP client/server mixed mode, UDP mode, SSL TCP Client mode, MQTT Client mode, MQTTS Client mode.
  - WIZ5xxSR-RP does not support PPPoE / DDNS



#### 3\) Local port & Remote host / Port

  - Local port
  - Remote host / Port
    - Users can enter the IP address or domain name of the destination or remote host when the module attempts connection in TCP client mode or UDP mode.
    - The port number of the destination is required.



#### 4\) Serial Options

  - **Baud Rate**
    - The supported baud rates are as below.
    - 300, 600, 1200, 1800, 2400, 4800, 9600, 14400, 19200, 28800, 38400, 57600, 115200(default), 230400, 460800
  - **Data Bit**
    - The supported data bits are as below.
    - 7, 8(default)
  - **Parity Bit**
    - The supported parity bits are as below.
    - NONE(default), ODD, EVEN
  - **Stop Bit**
    - The supported stop bits are as below.
    - 1(default), 2
  - **Flow Control**
    - RS-232/TTL versions support the below serial data flow control.
        - NONE(default): Do not use flow control.
        - XON/XOFF: Software flow control
        - CTS/RTS: Hardware flow control
        - RTS on TX:
        - RTS on TX (Invert):
    - RS-422/485 versions will operate as ‘NONE’ shown above no matter which option is selected.



#### 5\) Serial data packing condition

  - WIZ5xxSR-RP provides **multiple serial data packing options**. By using this option, user command frame or all other data can be collected and sent together.
  - Data packing options can be multi-selected but has priority as shown below.  
    **Character =\> Size =\> Timer**
  - **Timer**
    - Range: 0 \~ 65535 / Unit: milliseconds (ms)
        - Default: 0 (Not used)
    - Collects the data until the designated time is lapsed and sent together. Will not operate if set to '0'.
  - **Size**
    - Range: 0 \~ 2048 / Unit: data length (number of bytes)
        - Default: 0 (Not used)
    - Collects the data until the designated data length is reached and sent together.
    - Will does not operate if set to '0'.

  - **Character**
    - Range & Unit: 1-byte character (Hex code)
        - Default: 00 (Not used)
    - Collects the data until the designated character is entered and sent together.
    - The designated character will be included if the data size does not exceed the buffer size. The designated character will be excluded if the data size exceeds the buffer size.
    - Will does not operate if set to '0x00'.



#### 6\) Timer interval

  - **Inactivity Timer**
    - **Range: 0 \~ 65535 / Unit: seconds**
        - Default: 0 (Not used)
    - If inactivity timer is set, connection is lost after the designated time without data communication is lapsed after the last data is sent.
    - This setting is for **TCP Server or TCP Client mode and mixed mode**.
  - **Reconnection Interval**
    - **Range: 1 \~ 65535 / Unit: milliseconds (ms)**
        - Default: 3000 (Use, 3 seconds)
    - The re-connection interval is for **TCP Client Operation, including TCP Client of the mixed mode**.
    - This option is requires in order to re-connect TCP communication in case it is lost.
    - The setting must be at least 1ms.



#### 7\) TCP Keep-alive interval

  - This option allows the connection status to be kept alive by sending the ‘keep-alive packet’ in **all three TCP modes**. (TCP server, TCP client, and TCP mixed mode)
    - Default: Enabled (recommended)
    - TCP connection is disconnected if there is no response to the ‘keep-alive’ packet. (Socket close / disconnect)
    - The ‘keep-alive’ packet is sent after the Ethernet packet is sent at least once from WIZ5xxSR-RP.
  - **Send Keep-Alive Interval**
    - **Range: 0 \~ 65535, Unit: milliseconds(ms)**
        - Default: 7000, 5000 (recommended, 7 seconds / 5 seconds)
    - The required interval for sending the ‘keep-alive’ packet is as below.
        - Initial interval: The time until the first ‘keep-alive’ packet is sent
        - Retry interval: The time interval between each ‘keep-alive’ packets
  - This option is recommended in case of a physical disconnection with the remote device.
    - This option is recommended especially in TCP server mode.



#### 8\) Timeout
  - **SSL receive**
    - **Range: 0 \~ 60000 / Unit: milliseconds (ms)**
        - Default: 2000 (Use, 2 seconds)
    - This option allows only in **SSL TCP client** mode
    - If there is no response until the set time, a timeout occurs.



-----
