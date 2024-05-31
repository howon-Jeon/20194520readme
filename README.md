# 리눅스 프로세스 관리 명령어

리눅스에서 시스템 모니터링 및 프로세스 관리를 위해 자주 사용되는 명령어인 'top', 'ps', 'jobs', 'kill'에 대한 설명이다.

![image](https://www.google.com/url?sa=i&url=https%3A%2F%2Fwww.codestates.com%2Fblog%2Fcontent%2F%25EB%25A6%25AC%25EB%2588%2585%25EC%258A%25A4-%25EA%25B8%25B0%25EB%25B3%25B8-%25EB%25AA%2585%25EB%25A0%25B9%25EC%2596%25B4&psig=AOvVaw3nbBNcZu6Ng0TAdVZlcQcQ&ust=1717246793613000&source=images&cd=vfe&opi=89978449&ved=0CBIQjRxqFwoTCJCzmpf5t4YDFQAAAAAdAAAAABAE)


### `top` 명령

'top' 명령어는 실시간으로 시스템의 프로세스 정보를 모니터링하는 도구이다. CPU 사용률, 메모리 사용량, 실행 중인 프로세스 목록 등을 실시간으로 보여준다.

- **기본 사용법**: 터미널에 'top' 입력 후 엔터.
- **주요 단축키**:
  + q: top 명령어 종료.
  + k: 특정 PID의 프로세스를 종료.
  + P: CPU 사용률 기준으로 정렬.
  + M: 메모리 사용률 기준으로 정렬.

>> bash 스크립트(script)를 통한 자동화에도 ps 명령어가 자주 사용되는데,주로 특정 프로세스에 시그널(signal)을 보내야 할 때 PID(process id)를 식별하기 위해서 쓰이기도 하고, 프로세스가 중단되면 다시 실행시키기 위해 감시하는 목적으로 쓰이기도 한다.  

******

#### `ps` 명령어

ps 명령어는 현재 실행 중인 프로세스의 스냅샷을 찍어 보여주는 도구이다. top 명령어와 달리 실시간 업데이트는 없으며, 특정 시점의 프로세스 상태를 보여준다.

- **기본 사용법**:
  + ps: 현재 쉘의 프로세스만 보여줌.
  + ps aux: 시스템의 모든 프로세스를 상세히 보여줌.
  + ps -ef: 시스템의 모든 프로세스를 풀 포맷으로 보여줌.
-------
 

### jobs 명령어

jobs 명령어는 현재 쉘에서 실행 중인 백그라운드 및 포어그라운드 작업 목록을 보여줍니다.

- **기본 사용법**: 터미널에 jobs 입력 후 엔터.
- **옵션**:
  - 'jobs' -l: 각 작업의 PID와 상태를 함께 표시.


--------------
### kill 명령어

kill 명령어는 특정 프로세스를 종료시키는 도구입니다. 프로세스를 강제 종료하거나 신호를 보내 특정 작업을 수행할 수 있습니다.

- ***기본 사용법***:
  - kill PID: 기본 TERM 신호(종료)를 특정 PID의 프로세스에 보냄.
  - kill -9 PID: KILL 신호를 보내 프로세스를 강제로 종료.


- *주요 신호*:
  - SIGTERM (15): 프로세스를 정상적으로 종료 (기본 신호).
  - SIGKILL (9): 프로세스를 강제로 종료.


[리눅스명령어참고링크](https://inpa.tistory.com/entry/LINUX-%F0%9F%93%9A-%ED%94%84%EB%A1%9C%EC%84%B8%EC%8A%A4-%EA%B4%80%EB%A6%AC-%EB%AA%85%EB%A0%B9%EC%96%B4-%F0%9F%92%AF-%EC%A0%95%EB%A6%AC-Foreground-Background)
