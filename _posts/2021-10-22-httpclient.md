---
layout: post
comments: true
title: 'http통신'
categories: Language
tags: Java
---

**POST 방식**
```java
HttpClient httpClient = HttpClientBuilder.create().build();
HttpPost httpPost = new HttpPost(Url);

(파라미터로 담을 데이터 구성)

String jsonStr = mapper.writeValueAsString(params);

httpPost.setHeader("Content-Type", "application/json");
StringEntity params = new StringEntity(jsonStr);
httpPost.setEntity(params);

HttpResponse response = httpClient.execute(httpPost);

repsonse.close();
httpClient.close();
```