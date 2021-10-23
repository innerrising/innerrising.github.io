---
layout: post
comments: true
title: "컬럼명을 자바 변수명으로 바꿔주는 쿼리"
date:   2019-03-08 00:26:00 -0000
categories: Java Oracle
---
컬럼명 : USER_NM

```sql
LOWER(SUBSTR('USER_NM',0,1)) || SUBSTR(REPLACE(INITCAP ('USER_NM'),'_',''), 2) 
```

결과 : userNm
이제 자바 변수명 만들 때 이걸로 돌리면 된다.