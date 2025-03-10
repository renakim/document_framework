---
id: trouble-shooting-EN
title: Trouble Shooting-[EN]
date: 2020-04-08
---

**Supported Languages**  
\* [English](./Trouble-Shooting-EN.md) (current page)  
\* [Korean](./Trouble-Shooting-KO.md)

-----

  - Latest Update: ***Jan. 2018***

-----

## Common Cases

| Problems with the Configuration Tool |
| ------------------------------------ |

<details>
<summary>Where can I find the Configuration tool for WIZ750SR?</summary>

- WIZ750SR is a product designed to be compatible with WIZ107/108SR.
  Thus there is not a separate Configuration tool exclusively for
  WIZ750SR and users should use the WIZ107/107SR Configuration tool.

- The latest version Configuration tool can be downloaded at this [download page](./Download.md).

</details>

<details>
 <summary>The product cannot be searched.</summary>

  - Check the power and Ethernet cable’s connection first.

  - Check if the ping request from PC to module is successful.
      - When using Windows
        1.  Run \> Enter 'cmd' (windows command line)
        2.  ping 192.168.xxx.xxx (enter the allocated IP address)
        3.  Check response

|                                                                                                      |
| ---------------------------------------------------------------------------------------------------- |
| ![](https://d3cmhcsnvv7jc.cloudfront.net/docs/img/products/wiz750sr/troubleshooting/windows_cmd.png) |
| Entering 'cmd' command on Windows Run                                                                |

|                                                                                                         |
| ------------------------------------------------------------------------------------------------------- |
| ![](https://d3cmhcsnvv7jc.cloudfront.net/docs/img/products/wiz750sr/troubleshooting/ping_success_0.png) |
| Ping request / reply success                                                                            |

|                                                                                                        |
| ------------------------------------------------------------------------------------------------------ |
| ![](https://d3cmhcsnvv7jc.cloudfront.net/docs/img/products/wiz750sr/troubleshooting/ping_failed_0.png) |
| Ping request / reply failed                                                                            |

  - Use **UDP broadcast, port 50001** in order to use the UDP
    Search from the configuration tool of WIZ750SR. Please test after
    closing the **OS firewall and virus programs**. 

  - If there is a problem with the UDP port, users can change the OS
    inbound / outbound port settings to open the Search & firmware
    update port (UDP/TCP 50001, TCP 50002).

  - If multiple network adaptors are used, an error can occur in sending
    the packet in the correct order of the network interface Metric.
    Deactivate all other adaptors except the one that is used for OS
    setting in order to test again.
      - This problem can occur because of the virtual Ethernet adaptor,
        which is used for the networking of Virtual Machines like VMware
        or Virtual Box is used.

</details>

<details>
<summary>The product setting changes are not applied.</summary>

  - Click the ‘Setting’ icon from the Configuration tool after changing
    the product setting; then the product will restart and the changes
    will be applied.

|                                                                                                    |
| -------------------------------------------------------------------------------------------------- |
| ![](https://d3cmhcsnvv7jc.cloudfront.net/docs/img/products/wiz750sr/gettingstarted/configtool.png) |
| WIZ107/108SR & **WIZ750SR** Configuration Tool                                                     |

</details>

<details>
<summary>How do I check the firmware version?</summary>

1.  Click 'Search' and click the \[+\] MAC address to check the product information
2.  Check the ‘Firmware version' 

  - User can check the latest firmware version at the [product update history page](./Series-Update-History-EN.md) and [download page](./Download.md).

</details>

<details>
<summary>The firmware update is unsuccessful.</summary>

  - WIZ750SR has an internal TCP server for firmware updates.
      - TCP port number: 50002

  - Check if the ping request from PC to module is successful.
      - When using Windows
        1.  Run \> Enter 'cmd' (windows command line)
        2.  ping 192.168.xxx.xxx (enter the allocated IP address)
        3.  Check response

|                                                                                                      |
| ---------------------------------------------------------------------------------------------------- |
| ![](https://d3cmhcsnvv7jc.cloudfront.net/docs/img/products/wiz750sr/troubleshooting/windows_cmd.png) |
| Entering 'cmd' command on Windows Run                                                                |

|                                                                                                         |
| ------------------------------------------------------------------------------------------------------- |
| ![](https://d3cmhcsnvv7jc.cloudfront.net/docs/img/products/wiz750sr/troubleshooting/ping_success_0.png) |
| Ping request / reply success                                                                            |

|                                                                                                        |
| ------------------------------------------------------------------------------------------------------ |
| ![](https://d3cmhcsnvv7jc.cloudfront.net/docs/img/products/wiz750sr/troubleshooting/ping_failed_0.png) |
| Ping request / reply failed                                                                            |

  - The IP WIZ750SR and IP of the PC running the configuration tool must
    be identical in order to update the firmware.
      - In **DHCP mode** (automatic IP allocation), the PC and WIZ750Sr
        must have the same router allocate IP.
      - In **Static mode** (manual IP allocation), set as shown below.
          - 예) Product IP address: 192.168.11.2
          - 예) PC IP address: 192.168.11.3 (Same Class C private IPv4
            address range, Different IP address)

</details>

| Problems with the WIZ750SR Evaluation Board (EVB) |
| ------------------------------------------------- |

<details>
<summary>How do I connect the serial interface of WIZ750SR to PC for testing?</summary>

- There are two versions of the WIZ750SR evaluation board, RS-232/TTL & RS-422/485, and each is composed of a different serial interface connector.

- The **DB9 connector** is provided with the **RS-232/TTL version**; users can connect it to the serial port of the PC or use it with a RS-232 to USB convertor (available at Amazon).

- The **terminal block interface** is provided with the **RS-422/485 version**; this is used to connect to the user’s serial device. If the user wishes to connect with the PC, an RS-422/485 to USB connector (available at Amazon) is needed.

</details>

-----

## Problems cannot be solved\!


<details>
<summary>What is the next step if my problem is still not solved?</summary>

  - Users can ask questions at the [WIZnet Forum](https://forum.wiznet.io/).
      - <https://forum.wiznet.io/>

  - All WIZnet products have a **warranty of 1 year from the purchase
    date**.
  - Contact the person you purchased the product from and request a
    **RMA**.

</details>

-----

## Navigation

-----

 **WIZ750SR** 

  - **User's Manual [(English)](./Users-Manual-EN.md)/[(Korean)](./Users-Manual-KO.md)** 
  
  - **Device Command Manual [(English)](./Command-Manual-EN.md)/[(Korean)](./Command-Manual-KO.md)**
  
  - **Troubleshooting Guide [(English)](./Trouble-Shooting-EN.md)/[(Korean)](./Trouble-Shooting-KO.md)**
  
  - **Update History [(English)](./Series-Update-History-EN.md)/[(Korean)](./Series-Update-History-KO.md)**
  
-----

**WIZ750SR series Downloads** 

  - **[Software Download](./Download.md)**

  - **[Technical References](./Technical-References.md)**

-----

