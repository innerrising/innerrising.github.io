---
layout: post
comments: true
title: "오라클 DB 덤프(dump)"
date:   2019-06-19 00:26:00 -0000
categories: SQL
tags: Oracle
---

**로컬의 경우** 
```
imp(exp)(import, export 구분) userid=[대상계정명]/[대상계정암호] file='[경로]' (full=y)(전체 백업 여부)
```

**원격의 경우**
```
imp(exp) [대상계정명]/[대상계정암호]@[대상아이피]/[서비스명] file='[파일명]' (full=y)(전체 백업 여부)
```