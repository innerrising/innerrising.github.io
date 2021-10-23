---
layout: post
comments: true
title: "ORA-01882: timezone region not found"
date:   2019-03-08 00:25:00 -0000
tags: Server AWS
---
로컬에서는 되는데 AWS 만 올리면 timezone 어쩌고 하면서 쿼리를 못 읽는 경우가 있다.
리눅스 문젠지 알았는데 아니었다.

톰캣 문제다. 

```
export CATALINA_OPTS="$CATALINA_OPTS -Dfile.encoding=UTF8 -Duser.timezone=GMT+9"
```
하니까 바로 된다.