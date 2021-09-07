이름을 잘 짓는 간단한 규칙

1. 의도를 분명히 밝혀라
  1-1. 변수의 이름은 이 질문들에 모두 답해야 한다. 
    * 변수의 존재 이유는?
    * 수행 기능은?
    * 사용 방법은?

2. 그릇된 정보를 피하라
3. 의미 있게 구분하라
4. 인코딩을 피하라
5. 클래스 이름 ->
  5-1. 명사나 명사구가 적합, Customer, WikiPage, Account, AddressParser
  5-2. 동사 사용 x
6. 메서드 이름 -> 동사, 동사구가 적합 postPayment, deletePage, save
   ```java
    // 생성자를 중복정의 할 때는 정적 팩토리 메서드를 사용한다.
    // 메서드는 인수를 설명하는 이름을 사용한다.
    Complex fulcrumPoint = Complext.FromRealNumber(23.0); // (0)
    
    Complex fulcrumPoint = new Complex(23.0);  // (x)
   ```
7. 기발한 이름은 피하라 
8. 한 개념에 한 단어를 사용
9. 말장난을 하지 마라 
10. 해법 영역에서 가져온 이름을 사용하라
11. 문제 영역에서 가져온 이름을 사용하라(도메인에 관련된 이름을 사용하는 듯(그레이토터스))
12. 의미 있는 맥락을 추가하라
    ```java
      public class GuessStatisticsMessage {
        private String number;
        private String verb;
        private String pluralModifier;

        public String make(char candidate, int count) {
          createPluralDependentMessageParts(count);
          return String.format(
            "Thene %s %s %s%s",
            verb, number, candidate, pluralModifier
          );
        }

        private void createPluralDependentMessageParts(int count) {
          if (count == 0) {
            thereAreNoLetters(); // 여기서 함수 하나 더 타게 하는게 굉장히 좋은 방식인것 같다!!
          } else if (count == 1) {
            thereIsOneLetter(); 
          } else {
            thereAreManyLetters(count);
          }
        }

        private void therAreManyLetters(int count) {
          number = Integer.toString(count);
          verb = "are";
          pluralModifier = "s";
        }

        private void thereIsOneLetter() {
          number = "1";
          verb = "is";
          pluralModifier = "";
        }

        private void thereAreNoLetters() {
          number = "no";
          verb = "are";
          pluralModifier = "s";
        }
      }    
    ```
13. 불필요한 맥락을 없애라