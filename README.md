# 리눅스 프로세스 관리 명령어

리눅스에서 시스템 모니터링 및 프로세스 관리를 위해 자주 사용되는 명령어인 'top', 'ps', 'jobs', 'kill'에 대한 설명이다.

<img src="https://blogcodestates.com/wp-content/uploads/2022/12/%EB%A6%AC%EB%88%85%EC%8A%A4-%EA%B8%B0%EB%B3%B8-%EB%AA%85%EB%A0%B9%EC%96%B4.-%EB%AA%A8%EC%9D%8C.png?fit=900%2C675&ssl=1" width="500" height="300">


### `top` 명령

'top' 명령어는 실시간으로 시스템의 프로세스 정보를 모니터링하는 도구이다. CPU 사용률, 메모리 사용량, 실행 중인 프로세스 목록 등을 실시간으로 보여준다.

- **기본 사용법**: 터미널에 'top' 입력 후 엔터.
- **주요 단축키**:
  + q: top 명령어 종료.
  + k: 특정 PID의 프로세스를 종료.
  + P: CPU 사용률 기준으로 정렬.
  + M: 메모리 사용률 기준으로 정렬.


******

#### `ps` 명령어

ps 명령어는 현재 실행 중인 프로세스의 스냅샷을 찍어 보여주는 도구이다. top 명령어와 달리 실시간 업데이트는 없으며, 특정 시점의 프로세스 상태를 보여준다.

- **기본 사용법**:
  + ps: 현재 쉘의 프로세스만 보여줌.
  + ps aux: 시스템의 모든 프로세스를 상세히 보여줌.
  + ps -ef: 시스템의 모든 프로세스를 풀 포맷으로 보여줌.
 
>> bash 스크립트(script)를 통한 자동화에도 ps 명령어가 자주 사용되는데,주로 특정 프로세스에 시그널(signal)을 보내야 할 때 PID(process id)를 식별하기 위해서 쓰이기도 하고, 프로세스가 중단되면 다시 실행시키기 위해 감시하는 목적으로 쓰이기도 한다.  


#### Common Options

| Option   | Description                                                                               |
|----------|-------------------------------------------------------------------------------------------|
| `a`      | Display processes associated with the terminal. Typically used with `x` to show all processes. |
| `e`      | Display environment variables related to the process.                                      |
| `f`      | Display processes in a tree format showing relationships.                                  |
| `l`      | Display detailed (long) information about processes.                                       |
| `u`      | Display processes based on the process owner.                                              |
| `x`      | Display processes not associated with a terminal.                                          |
| `p`      | Display the specified process.                                                             |
| `-a`     | Display all processes except session leaders and processes not associated with a terminal. |
| `-A`     | Display all processes.                                                                     |
| `-C [process]` | Display only the specified process.                                                  |
| `-e`     | Display all processes.                                                                     |
| `-f`     | Display processes in UNIX style format.                                                    |
| `-o [value]` | Specify output format, where value can be `pid`, `tty`, `time`, etc.                   |
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
  1. SIGTERM (15): 프로세스를 정상적으로 종료 (기본 신호).
  2. SIGKILL (9): 프로세스를 강제로 종료.


[리눅스명령어참고링크](https://inpa.tistory.com/entry/LINUX-%F0%9F%93%9A-%ED%94%84%EB%A1%9C%EC%84%B8%EC%8A%A4-%EA%B4%80%EB%A6%AC-%EB%AA%85%EB%A0%B9%EC%96%B4-%F0%9F%92%AF-%EC%A0%95%EB%A6%AC-Foreground-Background)
