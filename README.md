# top-ps-jobs-kill

1. *top*
2. *ps*
3. *jobs*
4. *kill*



***top***
주로 개발하고 있는 프로세스의 cpu점유율과 메모리 상태를 알아보기 위해 사용되는 명령어입니다.
'top[옵션]'

실시간 모드: top명령어에서는 -d옵션을 사용하여 실시간 모드로 변경할 수 있습니다. 이 모드에서는 일정한 시간 간격으로 프로세스 정보를 갱신하며, 이를 통해 프로세스의 동적인 상태를 모니터링 할 수 있습니다. 이러한 기능들을 통해 top명령어는 리눅스 시스템에서의 성능 분석, 문제 해결, 자원 관리 등에 유용하게 사용될 수 있습니다.

보통 상단의 정보에는 cpu사용율과 메모리 사용율이 나타납니다.
하단의 정보에는 프로세스의 *cpu메모리 사용율을 나타냅니다
프로세스의 표시가 갱신되는 시간은 기본 3초인데 매초마다 갱신하고 싶은 경우는 탑이
실행되고 있는 화면에서 d키를 누르고 2를 입력한 후 엔터키를 누르면 됩니다. 아니면 탄 명령을 실행할 때 esd옵션의 1이라는 값을 줘도 됩니다. 그 외에 탑이 실행되는 화면에서 h키를 누르면 사용할 수 있는 옵션이 출력됩니다.

**아래 표는 top의 옵션을 정리한 것입니다.**
![top 옵션](https://github.com/Chayuyeon/top-ps-jobs-kill/assets/171216969/4d1e0b5b-35ae-4d8e-b78f-8e4af0bfd351)

부가적인 설명과 더 쉬운 이해를 위해 영상 자료를 참고하면 좋을 것 같습니다.
<https://www.youtube.com/watch?v=7QarWHdwbQw>




***ps***
현재 리눅스 서버의 구동 중인 프로세스의 정보를 출력해주는 명령어입니다.
프로세서와 프로세스가 있는데 프로세서에서 어는 cpu를 의미하고 프로세스는 실행 파일이 메모리에 업로드 된 상태를 의미합니다.
ps 명령어는 다음과 같은 형식으로 사용됩니다.
'$ps [options]'

**여기서 options는 ps 명령어의 여러 옵션들을 나타냅니다. 몇 가지 주요한 옵션들은 다음과 같습니다.**
![ps 옵션](https://github.com/Chayuyeon/top-ps-jobs-kill/assets/171216969/1db886a7-8c90-4bfe-9730-ff082af62b78)

옵션을 조합하여 원하는 정보를 얻을 수 있습니다. 예를 들어, ps -ef 명령어는 이 리눅스 서버에서 구동중인 모든 프로세스의 상태가 출력됩니다.너무 많은 정보가 출력되다보니 특정 프로세스의 상태만 알고 싶을 경우가 있는데 이전에 배웠던 파이프 라인과 문자열을 검색하는 g명령어를 활용하면 됩니다.
ps -2f명령어의 파이프라인을 연결해서 g명령으로 전달하고 찾고자 하는 프로세스의 이름을 적으면 됩니다

밑의 테이블표는 자주쓰는 명령어를 정리한 것입니다.
|자주쓰는 명령어|해석|비고|
|------|---|---|
|$ps -p 1|프로세스 번호가 1인 프로세스 출력|테스트3|
|$ps -fd[PID]|PID를 키워드로 프로세스 정보를 확인|테스트3|
|$ps -u root|특정 사용자가 돌리는 프로세스의 정보를 알고 싶을 때|테스트3|

**ps 명령어의 장점과 단점은 다음과 같습니다.**
**장점**: ps 명령어를 사용하면 현재 실행 중인 모든 프로세스의 정보를 한 눈에 확인할 수 있습니다.
다양한 옵션을 사용하여 원하는 조건에 따른 프로세스만 필터링할 수 있습니다.
**단점**: ps 명령어는 현재 상태의 스냅샷을 보여주기 때문에 실시간으로 변하는 프로세스 상태를 확인하기에는 적합하지 않을 수 있습니다.
모든 프로세스를 보여준다는 점에서 출력 결과가 많을 수 있기 때문에 원하는 정보를 찾기에 다소 어려움이 있을 수 있습니다.

부가적인 설명과 더 쉬운 이해를 위해 아래 동영상을 참고하시면 좋을 것 같습니다.
<https://www.youtube.com/watch?v=sHNWxIxdT7g>



***jobs***
현재 돌아가고 있는 백그라운드 프로세스 리스트를 모두 출력해주는 명령어입니다.
백스라운드 프로세스는 스택처럼 쌓이는데 +는 스택의 가장 위에 있다는 뜻이고,
-는 바로 그 다음 밑에 있다는 뜻입니다.
'$jobs [option][job name or number]'
ps 명령어만으로는 현재 터미널에서 실행 중인 프로세스만 확인할 수 있습니다. 만약 백그라운드에서 실행 중인 프로세스를 확인하고 싶다면 jobs 명령어를 사용하면 됩니다.
'jobs'
위의 명령어를 실행하면 현재 백그라운드에서 실행 중인 작업 목록이 출력됩니다. 각 작업에는 고유번호와 상태가 표시됩니다.

**jobs 명령어에는 다양한 옵션을 사용할 수 있습니다.**
|jobs의 명령어 옵션|설명|비고|
|------|---|---|
|-j|작업 번호를 지정하여 해당 작업의 상태를 확인할 수 있습니다. 예를 들어, "jobs -j 1" 명령어를 입력하면 1번 작업의 상태를 확인할 수 있습니다.|테스트3|
|-l| 작업 상세 정보를 출력합니다. 이 옵션을 사용하면 작업 번호, 프로세스 ID, 상태, 시작 시간 등의 정보를 확인할 수 있습니다.|테스트3|
|-p|작업에 할당된 프로세스 ID를 출력합니다. 이 옵션을 사용하면 작업 번호와 함께 해당 작업에 할당된 프로세스 ID를 확인할 수 있습니다.|테스트3|
|-r|현재 중지된 작업을 다시 시작합니다. 예를 들어, "jobs -r %1" 명령어를 입력하면 1번 작업이 다시 시작됩니다.|테스트3|
|-s|모든 작업의 상태를 출력합니다. 이 옵션을 사용하면 모든 작업의 상태를 한 눈에 확인할 수 있습니다.|테스트3|


**jobs 명령어의 장점과 단점은 다음과 같습니다.**
**장점**: 현재 쉘 세션에서 실행 중인 작업 목록을 간단하게 확인할 수 있습니다.
**단점**: 백그라운드에서 실행 중인 다른 쉘 세션의 작업 목록을 확인할 수 없으며, 자세한 정보를 제공하지 않습니다.




***kill***
해당 프로세스를 강제로 종료할 수 있는 명령어 입니다.
kill 명령어를 사용하기 위해서는 먼저 종료하려는 프로세스의 프로세스 ID(PID)를 알아야 합니다. 일반적으로 ps 명령어를 사용하여 현재 실행 중인 프로세스 목록을 확인한 후, 종료하려는 프로세스의 PID를 찾아야 합니다. 그런 다음 kill 명령어를 사용하여 해당 PID의 프로세스를 종료할 수 있습니다.

**kill 명령어에는 다양한 옵션을 사용할 수 있습니다.**
-s <signal>: 특정 시그널(signal)을 사용하여 프로세스를 종료합니다. 기본적으로 SIGTERM 시그널이 사용됩니다.
![kill 옵션 실행한 거](https://github.com/Chayuyeon/top-ps-jobs-kill/assets/171216969/f34e2109-4bcc-42a3-8d78-b63097517eee)
몇 가지 더 유용한 옵션을 아래 테이블표를 통해 학습할 수 있습니다.
|kill의 명령어 옵션|설명|비고|
|------|---|---|
|-l|시그널의 종류 출력|테스트3|
|-s|시그널의 이름을 지정하는 옵션|테스트3|
|-v|시그널 전송 결과를 출력|테스트3|


**kill 명령어의 장점과 단점은 다음과 같습니다.**
**장점**: - 간단한 명령어로 빠르게 프로세스를 종료할 수 있습니다. - 다양한 옵션을 사용하여 프로세스 동작을 제어할 수 있습니다.
**단점**: - 잘못 사용하면 의도치 않은 프로세스 종료가 발생할 수 있습니다. - SIGKILL 시그널을 사용하여 강제 종료할 경우, 프로세스가 올바르게 정리되지 않을 수 있고, 데이터 손실 등의 문제가 발생할 수 있습니다.
