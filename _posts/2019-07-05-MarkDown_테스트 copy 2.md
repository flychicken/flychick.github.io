---
title:      "마크다운 테스트"
date:       2019-07-08 17:43:00
categories:
  - markdown
tags:
    - markdown
---

A First Level Header
====================

A Second Level Header
---------------------

Now is the time for all good men to come to
the aid of their country. This is just a
regular paragraph.

The quick brown fox jumped over the lazy
dog's back.

### Header 3

> This is a blockquote.
> 
> This is the second paragraph in the blockquote.
>
> ## This is an H2 in a blockquote

### 한글은 잘 나오는지 확인 해보자
> 잘나오나?
>
> 진짜 잘 나오나?
>
>## 잘 나오겠지?
1. 한글
2. 한글
3. 한글

---
>[링크 사용법](http://naver.com, 'naver')
---
*이건

*뭐지?

*기울임*

_볼드_


"> 이건 코드 블록인가"
> 이건 코드 블록인가\\
>import Firebase\\
>import UI Kit\\
> class UIControllerview\\

|Left |Center|Right|
|:---:|:---:|:----:|
|1|2|3|
|45|67|89|

- one
- two
- three

1. one
2. two
3. three

다시 올라가라

```javascript
function test(){
  console.log("look ma', no spaces");
 }
```

:+1
:rocket

```python
s = "python syntax highlighting"
print s
```

~~~ SQL
SELECT * 
FROM DUAL
WHERE 1=1
;
~~~

~~~ Docker
# base image로 centos 7 사용 
FROM centos:7 as base
MAINTAINER "Taeseong Kim"

# centos update (옵션)
RUN yum -y update
# aio 라이브러리 설치 (tibero 사용)
RUN yum -y install libaio

# group & user 생성
RUN groupadd dba
RUN useradd -d /home/tibero -g dba tibero

# Tibero engine & license & tbinary 복사
ADD ./pkg/tibero6-bin-*.tar.gz /home/tibero/.
ADD ./pkg/tbinary_*.tar /home/tibero/.
COPY ./pkg/license.xml /home/tibero/tibero6/license/.

# Script 복사 & 권한 설정
COPY ./pkg/add_bash_profile /home/tibero/.
COPY ./pkg/runTibero.sh /home/tibero/.
RUN chmod 755 /home/tibero/*.sh

# 소유권 설정 
RUN chown -R tibero:dba /home/tibero

# 환경 변수 설정 
ENV     TB_SID=tibero \
            TB_HOME=/home/tibero/tibero6
ENV     LD_LIBRARY_PATH=$TB_HOME/lib:$TB_HOME/client/lib:$TB_HOME/tools/lib:$LD_LIBRARY_PATH \
            PATH=$PATH:$TB_HOME/bin:$TB_HOME/client/bin:$HOME/bin:$TB_HOME/script

# bash_profile 설정
USER tibero
WORKDIR /home/tibero/
RUN cat add_bash_profile >> .bash_profile

# TIP 파일 생성
USER tibero
WORKDIR $TB_HOME/config
RUN ./gen_tip.sh
RUN tbctl create_db

# Container 기동시 수행될 스크립트 지정
USER tibero
CMD /home/tibero/runTibero.sh

~~~
 
> first block
> > second blocks
>>> third blocks

추가 테스트

~~*testtesttest*~~


![테스트 이미지](/img/2019-07-09-14-03-48.png)


테스트 이미지