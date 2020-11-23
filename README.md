# Assignment 3: DB Designing

2020 KWEB 가을학기 준회원 스터디

과제 3은 메신저 서버의 데이터베이스를 디자인하는 과제입니다. 

### Required Tables

- 모든 테이블은 기본 키 `id`가 반드시 있어야 합니다.
- 각 테이블의 column 이름과 자료형을 정하고, 옵션을 정해야 합니다.
    - 자료형은 각 column에 맞게 적절히 정합니다.
- `users` : 메신저 사용자에 관한 정보
    - 사용자 아이디
    - 사용자 비밀번호
    - 사용자 닉네임
    - 프로필 사진 링크
    - 프로필 상태 메시지
    - 탈퇴 여부 (T/F) ; 기본값은 `0`
    - 가입 날짜
- `channels`: 채팅 채널에 관한 정보
    - 이름
    - 채널을 생성한 사용자
    - 채널의 링크
    - 최대 수용 인원
    - 탈퇴 여부 (T/F) ; 기본값은 `0`
    - 채널 생성 날짜
- `chats`: 각 채팅에 관한 정보
    - 채팅 내용
    - 채팅 작성자
    - 채팅 채널
    - 채팅 생성 날짜
- `follows`: 팔로우에 관한 정보
    - 팔로우한 사람 (follower)
    - 팔로우되는 사람 (followee)
    - 팔로우 날짜
- `blocks`: 사용자 간 차단에 관한 정보
    - 차단을 한 사람
    - 차단을 당한 사람
    - 차단 날짜

### Object

- 앞의 Required Tables 부분을 참고하여, 데이터베이스를 설계하세요.
- 주어진 정보를 모두 저장할 수 있는 테이블을 각각 생성하는 SQL문을 작성합니다.
- SQL문을 모두 chats.sql 파일에 작성한 후, 깃헙에 업로드하여 제출합니다.

### Tips

- SQL 파일은 다음과 같이 작성하면 됩니다.

```sql
CREATE TABLE users (
	-- Your code here
) ENGINE=InnoDB DEFAULT CHARSET=utf8;

CREATE TABLE channels (
	-- Your code here
) ENGINE=InnoDB DEFAULT CHARSET=utf8;

-- chats / blocks table code here

CREATE TABLE follows (
	-- Your code here
) ENGINE=InnoDB DEFAULT CHARSET=utf8;
```

- DB에 직접 SQL문을 작성하여 잘 작동하는지 확인해봅니다. `DESC` 키워드를 이용하여 테이블이 어떻게 설계되었는지 확인할 수 있습니다.
- 외래 키가 있는 테이블을 생성할 때 참조되는 column이 있는 테이블이 없으면, 테이블은 생성되지 않습니다.
    - 예를 들어, 스터디 자료의 courses 테이블과 departments 테이블에서 courses.department column이 departments.id column을 참조하는데, departments 테이블을 생성하지 않은 채로 courses 테이블을 생성하려고 하면 에러가 발생합니다.
- 깃헙에 업로드할 때 .gitignore은 작성하지 않아도 됩니다.

### Submission

- 제출 기한은 11/14 (토)입니다. 지각 제출 기한은 11/16 (월)입니다.
- 각 분반 오픈채팅방의 톡 게시판에 과제 3 제출 게시글에 깃헙 저장소의 링크를 댓글로 남겨주시면 됩니다.
- 깃헙 저장소가 Private이면 열람이 불가능하니 반드시 Public으로 설정해주세요.
- 모르거나 궁금한 것이 있으면 구글에 검색해보는 것도 좋고, 스터디장에게 질문해보시는 것도 좋습니다!