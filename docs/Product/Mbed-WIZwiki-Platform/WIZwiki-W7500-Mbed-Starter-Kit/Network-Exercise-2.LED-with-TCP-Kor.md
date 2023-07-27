---
id: network-exercise-2-led-with-tcp-kor
title: 네트워크 예제2. TCP 통신으로 LED 제어하기
date: 2020-04-08
---

## 개요

TCP 프로토콜을 사용해서 원격으로 **LED 켜기와 끄기**를 실행시켜 보는 예제이다. PC를 TCP Client로 동작시키고,
WIZwiki 보드는 TCP Server로 동작시킨다. W7500의 TOE (TCP/IP Offload Engine)을 이용해서
네트워크를 구동시키면서 위즈위키에 연결된 컴포넌트 (여기선 LED)를 구동시키는 방법을 학습할 수 있다.

## 준비물

  - WIZwiki-W7500 보드
  - USB 케이블
  - LAN 케이블
  - 공유기 (DHCP가 지원되는 유선 공유기 또는 유무선 공유기)

## 하드웨어

### 회로도

특별한 부가 회로가 필요없다.

### 연결도

DHCP가 지원되는 공유기와 PC를 LAN 케이블로 연결한다. 공유기와 WIZwiki 보드를 LAN 케이블로 연결한다. PC와
WIZwiki 보드를 USB 케이블로 연결한다.

![](https://d3cmhcsnvv7jc.cloudfront.net/docs/img/products/wizwiki_mbed_kit/kit_kr/tcp_loopback_system_config.png)

## 소프트웨어

### 테스트용 프로그램

  - Terminal program
      - EX) Teraterm, Hercules, Hyperterminal 등
      - 시리얼포트 메시지 확인용
      - 시리얼포트 사용 예제는 아래 링크를 참조
          - 🌎[튜토리얼 예제2. 시리얼 포트를 이용해 데이터
            출력하기](./Exercise-2.Serial-port-Kor.md)



  - TCP/IP Client Server terminal program
      - EX) Hercules 등
      - TCP/IP Client Server terminal 을 이용해 메시지 송수신에 사용

### Example Code

아래 페이지의 예제 코드를 사용한다.

🌎https://os.mbed.com/teams/WIZnet/code/TCP_LED_Control-WIZwiki-W7500/

### 실행 방법 및 결과

PC와 WIZwiki 보드를 USB 케이블로 연결한다. (보드에 전원이 공급되어야 하기 때문에 이미 연결 되어 있을 것이다.)
PC에서 시리얼터미널 프로그램을 실행시킨다. WIZwiki 보드의 Reset 스위치를 눌러준 후에 메시지를 확인한다. DHCP가
동작해서 Server의 IP 주소(ex: 192.168.0.8)가 할당되는 것을 볼 수 있다.

![](https://d3cmhcsnvv7jc.cloudfront.net/docs/img/products/wizwiki_mbed_kit/kit_en/tcp_led_dhcp_1.jpg)

PC에서 Hercules 프로그램을 구동한다. Hercules에서 TCP Client 메뉴를 설정한다. 접속하고자 하는
Server의 IP 주소 (ex: 192.168.0.8)를 입력하고, Ping을 클릭하고, Connect를 클릭한 후의 모습이다.

![](https://d3cmhcsnvv7jc.cloudfront.net/docs/img/products/wizwiki_mbed_kit/kit_kr/tcp_led_client_1.jpg)

TCP Server 에서 출력하는 메시지를 Teraterm 에서 본 화면이다. PC의 Client에서 Server로
Connection 되었음을 할 수 있다. (ex: Connection from: 192.168.0.6)

![](https://d3cmhcsnvv7jc.cloudfront.net/docs/img/products/wizwiki_mbed_kit/kit_kr/tcp_led_server_1.jpg)
이제부터 WIZwiki 보드에 LED를 제어해본다.

PC의 TCP Client에서 **"LED\_ON"**이라는 메시지를 WIZwiki 보드 (TCP Server)로 보내면 LED가
켜진다. 아래 그림에서 "LED\_ON" 부분의 Send 버튼을 클릭한다.

![](https://d3cmhcsnvv7jc.cloudfront.net/docs/img/products/wizwiki_mbed_kit/kit_kr/tcp_led_on_client.jpg)

이 LED\_ON 메시지는 TCP Server 측에서 Parsing이 되고, LED가 켜진다. 아래 그림에서 파란색 동그라미
부분의 LED가 켜짐을 확인한다.

![](https://d3cmhcsnvv7jc.cloudfront.net/docs/img/products/wizwiki_mbed_kit/kit_kr/tcp_led_on_off.png)

LED가 켜지는 동작 이외에 다른 메시지도 표시된다. TCP Client 프로그램이 WIZwiki 보드에 메시지를 보내고,
WIZwiki 보드가 메시지를 반대의 순서로 TCP Client로 보낸다.

아래 그림과 같이 시리얼 포트로 Loopback 된 메시지를 확인한다.

![](https://d3cmhcsnvv7jc.cloudfront.net/docs/img/products/wizwiki_mbed_kit/kit_kr/tcp_led_on_server.jpg)

PC의 TCP Client에서 "LED\_ON"이 아닌 **"아무 메시지"**(ex: TEST)를 WIZwiki 보드 (TCP
Server)로 보내면 LED가 꺼진다.

![](https://d3cmhcsnvv7jc.cloudfront.net/docs/img/products/wizwiki_mbed_kit/kit_kr/tcp_led_off_client.jpg)

LED가 꺼지는 동작 이외에 다른 메시지도 표시된다. TCP Client 프로그램이 WIZwiki 보드에 메시지를 보내고,
WIZwiki 보드가 메시지를 반대의 순서로 TCP Client로 보낸다.

![](https://d3cmhcsnvv7jc.cloudfront.net/docs/img/products/wizwiki_mbed_kit/kit_kr/tcp_led_off_server.jpg)

아래 그림에서 파란색 동그라미 부분의 LED가 꺼짐을 확인한다.

![](https://d3cmhcsnvv7jc.cloudfront.net/docs/img/products/wizwiki_mbed_kit/kit_kr/tcp_led_on_off.png)

## 학습 자료

아래에 위즈네트 제품에 사용할 mbed 라이브러리와 예제들이 있다.

  - 🌎[WIZnet 팀 페이지](https://os.mbed.com/teams/WIZnet/)

아래에 위즈네트의 Hardware TCP/IP chip (W5500) 과 WIZnet TCP/IP Offload Engine
(W7500)을 위한 mbed 라이브러리

가 있다.

  - 🌎[WIZnetInterface 페이지](https://os.mbed.com/teams/WIZnet/code/WIZnetInterface/)
    

## 관련 링크

   * [스타터 킷 튜토리얼](./Tutorial-Kor.md)
