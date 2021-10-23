---
layout: post
comments: true
title: "C#에서 오라클 DB 연동"
date:   2019-03-08 00:17:00 -0000
categories: Language
tags: Csharp Oracle
---
간단하게 설정하겠다.

먼저 오라클(32bit)을 설치한다.
그리고 오라클과 같은 버전의 ODAC(32bit)를 설치한다.
ODAC는 비주얼 스튜디오에서 오라클 연동을 위한 별도의 드라이버이다. Oracle.DataAccess.dll을 이걸로 참조 받을 수 있다.

두 가지 방법이 있는데
하나는 개별 화면마다 작업하는 방법
그 다음은 통합 모듈로써 관리하는 방법이 있다.


그 전에 작업할 것이 있으니
솔루션 탐색기 - 참조 - 참조 추가를 누르면 참조 관리자가 뜨는데
이 때 오라클 설치 경로에서 Oracle.DataAccess.dll을 추가해줘야 한다.

경로는 드라이버:\app\사용자명\product\11.2.0(버전)\client\odp.net\bin\4에 있다.
***
첫 번째 방법은

폼에서
```c#
using Oracle.DataAccess;
```
를 추가한다.

(dll을 참조하지 않고 할 수도 있다. 이 때는 using System.Data.OracleClient; 로 추가해준다.)

그리고 오라클 접속 객체 생성
```c#
OracleConnection conn = new OracleConnection("Data source=포트주소/DB접속명; User ID=DB아이디; Password=DB패스워드");
```
***
두 번째 방법은
```c#
<connectionStrings>
      <add name="연결명" connectionString="Data source=포트주소/DB접속명; User ID=DB아이디; Password=DB패스워드; "/>
</connectionStrings>
```
App.config에 추가 한 뒤

연결하고자 하는 화면에서
```c#
using System.Configuration;
using Oracle.DataAccess;
```
를 추가한다.
```c#
OracleConnection conn = new OracleConnection(ConfigurationManager.ConnectionStrings["연결명"].ToString());
```
으로 최초 선언해준다.

