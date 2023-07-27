---
id: network-exercise-1-tcp-loopback-kor
title: 네트워크 예제1. TCP 루프백 통신 테스트하기
date: 2020-04-08
---

## 개요

TCP 프로토콜을 사용해서 Loopback 을 실행시켜 보는 예제이다. PC를 TCP Client로 동작시키고, WIZwiki
보드는 TCP Server로 동작시킨다. TCP Client에서 보낸 메시지를 그대로 되돌려 받는 동작을 한다.

W7500의 TOE (TCP/IP Offload Engine)을 이용해서 네트워크를 구동시키는 방법을 학습할 수 있다.


## 준비물

  - WIZwiki-W7500 보드
  - USB 케이블
  - LAN 케이블
  - 공유기 (DHCP가 지원되는 유선 또는 유무선 공유기)

## 하드웨어

### 회로도

특별한 부가 회로가 없다.

### 연결도

DHCP가 지원되는 공유기와 PC를 LAN 케이블로 연결한다. 공유기와 WIZwiki 보드를 LAN 케이블로 연결한다. PC와
WIZwiki 보드를 USB 케이블로 연결한다.

![](https://d3cmhcsnvv7jc.cloudfront.net/docs/img/products/wizwiki_mbed_kit/kit_en/tcp_loopback_system_config_en.png)


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

🌎https://os.mbed.com/teams/WIZnet/code/TCPEchoServer-WIZwiki-W7500/?platform=WIZwiki-W7500

아래 그림에서 빨간색 부분인 "Import this program" 부분을 클릭한다.

![](https://d3cmhcsnvv7jc.cloudfront.net/docs/img/products/wizwiki_mbed_kit/kit_en/ex_tcp_loop_1.jpg)

아래와 같은 팝업 창이 뜬다.

![](https://d3cmhcsnvv7jc.cloudfront.net/docs/img/products/wizwiki_mbed_kit/kit_en/ex_tcp_loop_2.jpg)

"Source URL" 과 "Import As" 가 디폴트 값으로 설정되어 있다. "Import Name"도 디폴트로 설정되어
있는데, 사용자가 원하면 바꿀 수 있다. 빨간색 부분인 "Import"를 클릭하면 mbed 컴파일러 환경으로 프로그램이
복사된다.


### 실행 방법 및 결과

PC와 WIZwiki 보드를 USB 케이블로 연결한다. (보드에 전원이 공급되어야 하기 때문에 이미 연결 되어 있을 것이다.)
PC에서 시리얼터미널 프로그램을 실행시킨다. WIZwiki 보드의 Reset 스위치를 눌러준 후에 메시지를 확인한다.
![](https://d3cmhcsnvv7jc.cloudfront.net/docs/img/products/wizwiki_mbed_kit/kit_en/ex_tcp_loop_server1.jpg)

PC에서 Hercules 프로그램을 구동한다. Hercules에서 TCP Client 메뉴를 선택하고, IP와 Port를
설정한다. 아래 그림의 "Ping" 버튼을 누른 후 메시지를 확인한다.
![](https://d3cmhcsnvv7jc.cloudfront.net/docs/img/products/wizwiki_mbed_kit/kit_en/ex_tcp_loop_client1.jpg)

"Connect" 버튼을 누른 후 연결을 확인한다.
![](https://d3cmhcsnvv7jc.cloudfront.net/docs/img/products/wizwiki_mbed_kit/kit_en/ex_tcp_loop_client2.jpg)

TCP Client 프로그램이 WIZwiki 보드에 메시지를 보내고, WIZwiki 보드가 역순으로 된 메시지를 TCP
Client로 보낸다. 아래 그림에서 Loopback 된 메시지를 확인한다.

![](https://d3cmhcsnvv7jc.cloudfront.net/docs/img/products/wizwiki_mbed_kit/kit_en/ex_tcp_loop_client3.jpg)

![](https://d3cmhcsnvv7jc.cloudfront.net/docs/img/products/wizwiki_mbed_kit/kit_en/ex_tcp_loop_server2.jpg)


## 학습 자료

아래에 위즈네트 제품에 사용할 mbed 라이브러리와 예제들이 있다.

  - 🌎[WIZnet 팀 페이지](https://os.mbed.com/teams/WIZnet/)

아래에 위즈네트의 Hardware TCP/IP chip (W5500) 과 WIZnet TCP/IP Offload Engine
(W7500)을 위한 mbed 라이브러리가 있다.

  - 🌎[WIZnetInterface 페이지](https://os.mbed.com/teams/WIZnet/code/WIZnetInterface/)
    

## 관련 링크

   * [스타터 킷 튜토리얼](./Tutorial-Kor.md)
