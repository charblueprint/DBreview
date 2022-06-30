# MySQL 설치하고 실행하기

![캡처1](C:\Users\tjoeun\Desktop\캡처1.JPG)![MySQLsetting](C:\Users\tjoeun\Desktop\MySQLsetting.JPG)
![MySQLsetting2](C:\Users\tjoeun\Desktop\MySQLsetting2.JPG)![MySQLsetting3](C:\Users\tjoeun\Desktop\MySQLsetting3.JPG)

# MySQL 시작하기

![MySQLenter](C:\Users\tjoeun\Desktop\MySQLenter.JPG)

MYSQL 설치가 끝나면 Mysql shell창이 나올텐데, 이 곳에다가 상기 코드처럼 써봅니다.

이 사진에서 `\sql` 은 sql 모드로 바꾸는 명령어입니다.

`\connect `는 해당 서버에 접속하기 위해서 비밀번호를 입력해야 하는데, 그 때 사용하는 명령어입니다.

그 비밀번호가 일치하면 사용자는 해당 서버에 접속하게 됩니다. 이때 생성한 이 비밀번호는 잊어버리면 다시 찾을 수 없으므로 조심해야 합니다.

# 데이터에 테이블 생성하기

![image-20220630114205975](C:\Users\tjoeun\AppData\Roaming\Typora\typora-user-images\image-20220630114205975.png)

상기 코드처럼 테이블 생성 시, 사용할 DB를 선정하지 않고 진행 할 수는 없습니다.  

```mysql
create table member(
mid varchar(10),
mpass varchar(10)
);
```
이 상기 코드를 풀어서 써보면,
create table '생성할 table 이름'( 
필드 명 자료형(범위) 부가 옵션,
필드 명 자료형(범위) 부가 옵션,
필드 명 자료형(범위) 부가 옵션,
필드 명 자료형(범위) 부가 옵션,
필드 명 자료형(범위) 부가 옵션,
...
); 입니다. 참고로 테이블 생성 시 필드(컬럼)과 함께 무조건 생성을 하게 됩니다.

이 사진에 나온 명령어들을 알아보자면,
- use "데이터베이스 이름"  -> 사용하고자 하는  DB를 선택할 때 사용합니다.
- create database; -> 새로운 DB를 만들 때 사용합니다.
- show databases; -> 현재 sql에서 사용하는 DB 전체 리스트를 보여 줍니다.
- show tables -> 해당 데이터 베이스 안의 table의 목록을 보고싶을 경우 사용합니다.
- +) drop database "데이터베이스 이름" -> DB를 삭제하는 명령어 입니다.  단, 삭제 시 DB안에 있는 모든 Table,Field, Data들이 전부 삭제가 되므로 신중히 진행해야 합니다.

# 자료를 이용해 특정 데이터 값을 산출해보자!

![adddata](C:\Users\tjoeun\Desktop\adddata.JPG)

![selectfrom.](C:\Users\tjoeun\Desktop\selectfrom..JPG)





![desc](C:\Users\tjoeun\Desktop\desc.JPG)

[테이블 필드명 확인]
`desc 테이블 명;`을 사용하면  



테이블 안의 Data 확인하는 데는 여러 방법이 존재합니다.

- select * from 테이블 명; -> * 사용 시 모든 필드를 지칭함
- select 필드 명 from 테이블 명; -> 해당 필드에 있는 모든 값만 출력합니다.
- select 필드 명1, 필드 명2, 필드 명4 from 테이블 명; -> 각각 다른 필드 명만 골라서 데이터를 확인합니다.

- select * from 테이블 명 where 필드 명="데이터 값"; 외 따옴표든 쌍 따옴표든 상관 없습니다.
  이것은 동명이인이 존재하는 상황에서 사용하는데, 아이디는 중복되지 않을 거니까 사용이 가능한 것이다.
- select * from 테이블 명 where 필드 명 > 숫자; -> 해당 필드 속성이 무조건 숫자 속성(부등호기호 + '=' 사용)
  select * from 테이블 명 where 필드 명 like "%데이터 값"; => 찾는 데이터 이 뒤에 붙어있는 데이터 출력
  select * from 테이블 명 where 필드 명 like "데이터 값%"; => 찾는 데이터가 앞에 붙어있는 데이터 출력
  select * from 테이블 명 where 필드 명 like "%데이터 값%"; => 위치 상관없이 찾는 데이터가 포함되어있으면 전부 출력
  select count(*) from 테이블 명;=> 총 데이터 갯수가 출력 됩니다.
  select * from 테이블 명 limit index번호, 데이터 갯수 (몇 개 뽑을 건지 범위 설정); 
