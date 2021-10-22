---
layout: post
title: "ORA-04063 : package body "PKG_CRYPTO"에 오류가 있습니다."
date:   2019-07-08 10:28:00 +0900
categories: Java Spring
---

CRYPTO 라는 녀석이 암호화 해주는 유틸인 것 같은데 권한이 없으면 오류난다.

1. sys 계정으로 접속

2. %ORACLE_HOME%\rdbms\admin 경로에 존재하는 dbmsobtk.sql, prvtobtk.plb 두 개의 스크립트를 돌린다.

3. 아래 명령어를 통해 권한을 부여한다.

\*\*public 권한 부여\*\*
```
grant execute on dbms_crypto to public;

grant execute on dbms_obfuscation_toolkit to public;
```

\*\*계정 권한 부여\*\*
```
grant execute on dbms_crypto to 계정명;

grant execute on dbms_obfuscation_toolki to 계정명;
```

그 다음 해당 계정으로 들어가서 PKG_CRYPTO BODY를 리컴파일한다. 
저게 안 돼서 며칠 째 고생했는데 이제야 권한이 제대로 들어간다.(흡족)

- 끗 -