gmail parkdaeho.dev@gmail.com

github Parkdaeho99


1byte = 8bit
( 0,1,0,1 bit의 전기신호로 값을 보낸다 )

□□□□□□□□ (8bit)
0 0  0 0 0  0 0 0
1 1  1 1 1  1 1 1

2^8의 개수만큼 표시 가능
(0~255 = 256가지 수)

boolean = 1bit ( true = 1 , false = 0 )
char = 2byte (문자)
short = 2byte (정수)
int = 4byte (정수)
long = 8byte (정수)
float = 4byte (실수) [ long < float 왜냐하면 실수라서 더 큼 ]
double = 8byte (실수)

부호비트 0 = 양수, 1 = 음수
(대신 맨 앞 비트를 부호로 쓰기 때문에 0~255까지 표현 가능하던 게 -128 ~ 127 로 변함)
(즉, 맨 앞 비트는 부호비트로 써야하기 때문에 표현하고자 하는 값이 마이너스든 아니든간에 1비트를 소모해야해서 -128~127까지만 표현 가능)

고정소수점 - 우리가 쓰는 소수(ex. 1.523)
부동소수점 - 컴퓨터가 고정소수점을 알아먹을 수 있게 변환시킨 것

152.23 -> 1.523*10^2 -> 1.523*e2
(고정)  -> (1차변환)    -> (2차변환, 부동소수점 완성)
                                [컴퓨터는 지수 표현 불가능 -> 10^2 -> e2]

한글 한칸 3byte
영어, 숫자 한칸 1byte
저장공간에는 byte 단위로 저장하기 때문에 boolean은 1bit만 쓰이지만, 실제로 저장될 땐 1byte 공간을 차지

상수 선언
final int num = 4;

System.out.println("\\"); => \

void = 공간이 비었다
null = 공간조차 없다

대문자와 소문자의 아스키코드 숫자 차이는 32다.
'A' + 32 = 'a'
'a' - 32 = 'A'

Math.random() => 0이상 1미만의 수, Math 클래스는 기본지원 클래스이므로 임포트X
Random rd = new Random() =>Random 클래스
	rd.nextInt(10) => 0이상 10미만의 수

		Math class	VS	Random class
클래스 기본제공	O			X
범위			0포함 ~ 지정숫자 미만
객체생성		X			O [Random rd = new Random()]
사용		Math.random()		rd.nextInt();
0~9난수생성	Math.random() * 10	rd.nextInt(10);
0~100난수생성	Math.random() * 101	rd.nextInt(101);
50~100난수생성	Math.random() * 51 + 50	rd.nextInt(51)+50;

실수는 정확하게 연산하지 않는다. 
그러므로 정수로 먼저 계산 후 실수로 표현
-> 1.0 - 0.1*7 = 0.29999999993

컴퓨터에서 3 - 3을 하려면 3 + (-3)으로 계산함
1의보수 : 비트 반전 -> 컴퓨터가 이걸로 음수표현을 못함 -> 2의보수 사용
2의보수 : 1의보수를 한 후에 +1

3	  -> 1의보수    -> 2의보수 (-3)
0000 0011 -> 1111 1100 -> 1111 1101
그렇다면 -3의 2진수인 1111 1101을 보고 +3을 구하려면 -1을 한 후에 다시 반전시키면 되나

String str = "LUCK";
-> String은 다른 변수랑 다르게 첫글자가 대문자다 = 이는 곧 타입이 아니라 클래스라는 의미
-> 클래스는 LUCK를 HEAP 메모리에 저장해두고 HEAP 메모리에서 LUCK가 저장된 주소를 String에서 참조
-> 즉, String에 LUCK 값이 저장되는 것이 아니라 그 값이 가지고 있는 메모리 주소가 저장된다.

String + 숫자 = String
-> 10 + 10 + "" -> 1010 ( 편법 )

valueof()
-> XXXX.valueof()
->Integer.valueof(str); // str을 int로 바꾼다
parseInt()
-> XXXX.parseInt();
-> Integer.parseInt(str); // str을 int로 바꾼다.

Integer.valueof(), Integer.parseInt() , Math.randon()
전부 클래스인데, 객체생성을 하지 않고 바로 사용한다.
Scanner처럼 new하고 쓰는게 아닌데 먼 차이지?
-> statci으로 구현되어 있어서 생성안하고 사용 가능하다?

GIT(깃)
버전 관리 도구( ex.깃허브, 서브버전, 비트버켓)
버전이 업데이트 될 때마다 코드,개발내역,코멘트 등이 기록됨 (이처럼 갱신하는걸 commit 이라 부른다)
장점 - 이전 버전으로 롤백 가능

깃허브 원격 remote저장소
	↕
내피시 로컬 local저장소
피시 -> 깃허브로 데이터 집어넣는다 PUSH
깃허브 -> 피시로 데이터를 당겨온다 PULL
추가/수정/삭제된폴더/파일들을 1개 버전으로 간주하여 내 컴퓨터 로컬에 버전 정보를 기록한다. 내가 실행을 하겠다? COMMIT
커밋한 뒤에 PUSH 해야한다.
(commit -> local repository / push -> remote repository)

Branch - 가지치기 / 메인시스템이 잘못될수도 있으니 임시공간을 추가하여 그곳에서 개발
Tag - 개발 진행도에서 한번에 찾아갈수있도록 태그를 설정(메인시스템도 버전이 막 달라질거고 브런치도 마구마구 생길테니까 햇갈림 그래서 만든게 태그)
Merge - 개발하다보면 브런치 공간도 생기고 메인시스템도 점점 발전돼가는데 결국 나중엔 메인,브런치를 다 합쳐져야하는데 이걸 머지라고함
fork - 깃허브에서 남이만든 코드를 내 깃허브저장소로 이동시킴( 블로그 공유 같은거인듯 )
( 남에꺼 포크 -> 내 깃허브에 저장되고 -> 풀해서 내피시에 저장하고 -> 그걸 커밋하고 내 깃허브로 푸쉬 )

내피시에서 코딩하다가 local repository에 commit하고
commit된 파일을 remote repository에 push한다.
그후, remote repository에 push된 파일을 다른 피시에서 pull해서 다른 피시의 local repository로 가져오고,
작업 후에 다시 local repository에 commit하고... 반복
