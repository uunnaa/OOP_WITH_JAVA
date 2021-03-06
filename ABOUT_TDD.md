>TDD를 적용하면서 제일 큰 유혹은 의욕에 앞서 아이디어 뿜뿜 떠오르는 것을 먼저 구현한다는 것이다. 근데 어차피 뿜뿜 떠올라도 막히기 마련인데, 테스트 케이스를 먼저 만들고 구현하면 내가 해야할 것이 더 명확해져서 더 빨리 구현하게 된다는 것을 느낀다
    TDD의 아이러니 중 하나는 TDD가 테스트 기술이 아니라는 점이다(워드 커닝엄의 선문답이다). TDD는 분석 기술이며, 설계 기술이기도 하다. 사실은 개발의 모든 활동을 구조화하는 기술이다.
     - 《테스트 주도 개발》by 켄트 벡



# TDD(Test-Driven-Develop)
- 요구사항의 테스트 요건을 먼저 고려한다.
### 사전 설계
* 테스트를 검증단계의 목적으로 사용한다.

         설  계      ->      구  현      ->       테 스 트

### T D D (점진적인 설계)
* 테스트를 설계단계의 목적으로 사용한다.

         테 스 트     ->      구  현      ->      리팩토링     
         
      (인터페이스 설계)                      (구현코드 설계)

# TDD의 목적
+ 자체 버그 검출
    - 테스트에 대한 자동화한다.
+ 소스 코드의 품질 저하 방지
    - 어디서 버그가 생길지 금방 찾을 수 있기 때문에 잘못된 코드도 고칠 수 있다.
+ 테스트 비용의 절감
    - 작은 수정에도 모든 기능을 다시 테스트 해봐야하는데, 자동화된 테스트로 비용을 절감하는 효과를 볼 수 있다. 이것은 거대한 기능을 가지고 있는 SW에서 효과적이다.
    - 예를들어 1개의 수정으로 100개의 시나리오를 테스트 해봐야한다. 자동으로 테스트 해주면 비용 절감 효과를 크게 누릴 수 있다.
+ 더욱 좋은 코드를 얻기 위한 깨달음
    - 테스트(설계) > 구현 > 리팩토링 과정을 거치면서 소스간의 결합도가 낮은 클린코드를 얻기 위해서 노력한다. 이런 수많은 과정을 반복하면서 프로그래머의 상세하게 명시하는 설계 감각과 경험이 쌓여진다.



 >   TDD는 사실 기술 자체만 보면 약간의 훈련이 필요할 뿐, 시작하는 것 자체가 어렵진 않다. 
    그런데 실제로 해보면 꽤 어렵다. 왜냐면 TDD는 기술과 프로세스, 둘을 아우르는 개념이기 때문이다. 
    목표가 불명확한 상태로 개발한다면 TDD를 하기 어렵다. 
    반대로 이야기하면, TDD를 하다보면 목표가 명확해질 수 있다. 
    우리에겐 두 가지 선택지가 있다. 
    목표가 이끄는 개발을 선택할까? 목표 없이 방황할까?

# 생산성에 직접적인 영향을 주는 요인
* 피드백 주기
* 디버깅 시간
* 테스트 실행 속도 
    - 변경사항을 검증하고 확인하기 위해 기다리는 시간
* 가독성이 떨어지는 코드
    - 분석이 어려워지고 디버거를 사용해야하는 상황까지 만들어진다.

# TDD 훈련법
### 1. 명확한 목표가 필요하다
![사진](/test/testcase1.jpg)
[출처](http://langgeek.tistory.com/entry/Effective-Unit-Testing-Chapter-1-%EC%A2%8B%EC%9D%80-%ED%85%8C%EC%8A%A4%ED%8A%B8%EC%9D%98-%EC%95%BD%EC%86%8D)

예를들면, ABC 샵에서 라면을 사는데 가장 싼 가격에 사는 프로그램을 만든다.
가격정보를 어딘가에 담아놓고 가장 저렴한 가격을 가져온다. 
가격이 같다면 BCA순서로 우선순위를 가진다.

* 요구사항에 대한 티켓발행 -> 서브테스크만들기 -> todo리스트 작성

테스트 케이스를 코드로 표현하기 위해서 기능과 동작과정을 명확히 생각하여 TODO리스트를 작성해야 한다.
TDD는 테스트를 수동이 아니라 **자동**으로 돌아가는 코드로 만든다.

### 2. 유닛코드를 작성한다
올바르게 작성하는 코드인가?
* 어떤 처리를 하면 결과가 어떻게 나올 것인가? 를 정확하게 안다.
* 결과를 내는 과정을 명확하게 적는다.(스펙을 코드로 나타낸다)


# 테스트 코드를 작성하기 어려운 이유는?
내가 지금 무엇을 만들어야 할 지 **구체적으로 표현하기 어려워서** 그렇다.
하다보면 어떻게든 되겠지라는 학습단계에서는 배울 수 있겠지만 실전에서는 큰 문제가 될 수 있다.


# TDD를 사용하면 좋은점?
작동하는 클린 코드를 얻을 수 있다.

### 1. 작동하는 코드를 얻을 수 있다.
자신의 훌륭한 코드가 **정상적**으로 돌아간다는 것을 스스로 증명한다.
    s
    - 올바르게 작동했을 때 결과값을 명확하게 코드로 작성하여 증명한다.
    - 이를 위해서 어쩔 수 없이 스펙을 명확하게 하고 결과를 확인하게 된다.
    - 예외상황도 빠르게 만들어볼 수 있다
    - 실수는 빠르게 잡을 수 있다.

### 2. 클린코드를 작성할 수 있다
디자인이 좋아지고, 디자인이 좋으면 **유연하게** 된다. 

    - 확장성있고 적응성있는 스프트웨어가 탄생한다.
        + 실제 업무할 때 비지니스환경이 빠르게 바뀌는데, SW를 바꾸면서 테스트코드도 조금씩 바꿔나갈 수 있어서 점진적 개발이 가능하다.
    - 개발하다보면 의존관계를 만들게 되는데 의존을 없애기 위해서 어쩔 수 없이 유연한 코드를 작성하게 된다

### 3. 재설계 시간의 절감
### 4. 디버깅 시간의 절감

### 결국! 개발 생산성이 좋아진다.

-------------------------------------------------------------



>너무 커다란 SW를 고치는 것? 유닛테스트코드로 굉장히 작은 부분을 고치는 것?
둘 중 선택하자면 미래의 고통을 현재로 가져오는 것이 훨씬 낫다.





###참고 URL
* [고려하면 좋은 URL](https://medium.com/@rinae/tdd-test-driven-development-%EB%A5%BC-%EC%97%B0%EC%8A%B5%ED%95%98%EB%A9%B4%EC%84%9C-%EC%B0%B8%EA%B3%A0%ED%95%98%EA%B8%B0-%EC%A2%8B%EC%9D%80-%ED%8C%81-10%EA%B0%80%EC%A7%80-d8cf46ae1806)
* [TDD 활용법](http://www.sw-eng.kr/member/customer/Webzine/BoardView.do?boardId=00000000000000035253&currPage=1&searchPrefaceId=00000000000000020135&titOrder=&writeOrder=&regDtOrder=&searchCondition=TOT&searchKeyword=)