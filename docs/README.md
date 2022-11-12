# 기능 목록

## 로또 구매
- [x] 사용자는 최초에 구입 금액을 입력하는데 이 때 구입 금액은 1,000원 단위여야 함.
- [x] 로또 숫자 범위는 1 ~ 45 (해당 범위 벗어나면 예외처리)
- [x] 각 숫자는 중복되면 안됨 (입력에 같은 수가 존재할 경우 예외처리)
- [x] 사용자에게 입력받는 로또 번호는 6개의 수로 이뤄져야 함 (6개 보다 많거나 적으면 예외처t)
- [x] 로또 번호는 (당첨 번호 + 보너스 번호 총 7글자)
- [x] 사용자가 입력한 값은 `Console` 클래스의 `readLine` 메소드를 활용해 처리
- [x] 사용자가 잘못된 값을 입력할 경우 IllegalArgumentException을 발생 시킨 뒤 에러 메시지를 출력하고 종료
- [x] 예시) [ERROR] 로또 번호는 1부터 45 사이의 숫자여야 합니다.

## 로또 번호 생성
- [x] 각 로또 번호는 `Randoms` 클래스의 `pickUniqueNumbersInRage` 메소드를 이용해 생성
- [x] 로또 번호는 사전에 제공된 `Lotto` 클래스를 이용해서 관리해야 함
- [x] 매개변수가 없는 생성자 추가 불가, number의 접근 제어자 변경 불가
- [x] 인스턴스 변수 추가 불가, 패키지 변경은 가능

## 로또 당첨 여부 확인
- [x] 사용자가 입력한 값과 `Lotto` 클래스에 저장된 값을 비교해 당첨 여부를 확인해야 함.
- [x] 입력한 값을 컴퓨터가 생성한 당첨 번호와 비교해 당첨 결과를 출력

## 수익률 계산
- [x] 수익률 = 당첨 금액 / 사용자가 사용한 구입 금액 * 100
- [x] 수익률은 소수점 둘째 자리에서 반올림

# 클래스 구성

## LottoGame
- 프로그램이 진행되는 최상위 클래스

## ManagementLottoNumber
- 로또 번호를 생성하는 `generateLottoNumber()` 메소드
- 로또 당첨 여부를 확인하는 `checkLottoNumber()` 메소드
- 수익률을 계산하는 `calcROI()` 메소드 / ROI = Return on investment

## Message
- 프로그램에서 출력되는 메세지들을 관리하는 클래스

## ProcessInput
- 사용자의 입력을 처리하는 클래스

## User
- 사용자 객체 클래스
- 해당 클래스에는 사용자가 입력한 로또 번호(6자리)가 저장됨
- 인스턴스 변수: 사용자의 번호 목록을 저장하기 위한 `List<List<Integer>> userNumbers`

## Lotto (사전 정의)
- 로또 번호 객체 클래스
- 로또 번호를 관리
- 해당 클래스에는 컴퓨터가 랜덤으로 생성한 로또 번호(6자리)가 저장됨
- 인스턴스 변수: 당첨 번호를 저장하기 위한 `List<Integer> numbers`

## ValidInput
- 사용자의 입력이 유효한지 검증하는 클래스
- 해당 클래스에서 검증할 항목은 아래와 같다.
  - 사용자의 입력이 정수로 변환 가능한가?
  - 사용자가 입력한 금액이 1,000원 단위의 정수인지?
  - 사용자가 입력한 번호가 1 ~ 45 사이의 정수인지?
  - 사용자가 입력한 번호 중 중복된 값이 존재하는지?
  - 사용자가 입력한 번호의 개수가 6개보다 작거나 큰지?

## PrintResult
- 결과를 출력하는 클래스