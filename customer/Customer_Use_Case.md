### Deriving Use Cases from System Requirements
|Actor|                                 Actor's Goal                       |         Use Case Name              |
|:---:|:------------------------------------------------------------------:|:----------------------------------:|
| 고객 |  피자 메뉴를 볼 수 있으며 선택할 수 있어야 한다.                              |       메뉴(피자) 보기 (Use case 1)    |
| 고객 |  장바구니를 보고 선택한 피자 목록을 보고 수정할 수 있어야 한다.                   |      장바구니 (Use case 2)           |
| 고객 |     원하는 피자 메뉴를 주문할 수 있어야 한다.                                |       주문하기 (Use case 3)          |
| 고객 |      주문이 정상적으로 들어갔음과 배달 현황/픽업 시간을 확인할 수 있어야 한다.       |        주문 정보 확인 (Use case 4)    |
| 고객 | 주문한 피자에 대해 리뷰를 남길 수 있어야 한다.                                |    리뷰 작성하기 (Use case 5)         |
| 고객 |     피자 메뉴에 대한 리뷰를 확인할 수 있어야 한다.                            |    리뷰 보기 (Use case 6)            |
| 고객 |     배달인지 픽업인지 선택할 수 있어야 한다.                                 |    수령 방법 입력 (Use case 7)        |
| 고객 |     주문한 피자를 결제할 수 있어야 한다.                                    |    결제하기 (Use case 8)             |
| 고객 |     로그인할 수 있어야 한다.                                             |    로그인 (Use case 9)              |

### Use Case Diagram

![Use_Case_Diagram](./Use_Case_Diagram.png)




### Traceability Matrix

|  FR't   |  PW  | UC1  | UC2  | UC3  | UC4  | UC5  | UC6  | UC7  | UC8  | UC9  |
| :-----: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: |
|   FR1   |  5   |      |      |      |      |      |      |      |      |   X  |
|   FR2   |  5   |   X  |      |   X  |      |      |      |   X  |   X  |   X  |
|   FR3   |  5   |   X  |      |      |      |      |      |      |      |      |
|   FR4   |  2   |   X  |      |      |      |      |  X   |      |      |      |
|   FR5   |  4   |   X  |   X  |      |      |      |      |      |      |   X  |
|   FR6   |  4   |   X  |   X  |      |      |      |      |      |      |   X  |
|   FR7   |  3   |      |      |      |      |      |      |   X  |      |   X  |
|   FR8   |  4   |      |      |      |      |      |      |      |   X  |   X  |
|   FR9   |  3   |   X  |      |   X  |   X  |      |      |   X  |   X  |   X  |
|   FR10  |  4   |   X  |      |   X  |   X  |      |      |   X  |   X  |   X  |
|   FR11  |  2   |   X  |      |   X  |      |   X  |      |   X  |   X  |   X  |
|  Max PW |      |   5  |   4  |   5  |   4  |   2  |   2  |   5  |   5  |   5  |
| Total PW|      |   29 |   8  |   14 |   7  |   2  |   2  |  17  |  18  |  34  |


### Schema for Detailed Use Cases

| Use Case UC-2:                            | 장바구니                                      |
| ----------------------------------------- | --------------------------------------------------- |
| Related Requirement:                      | FR5, FR6                                                |
| Initiating Actor:                         | 고객                                            |
| Actor's Goal:                             | 장바구니를 보고 선택한 피자 목록을 보고 수정할 수 있어야 한다.  |
| Participating Actors:                     | X                                                   |
| Preconditions:                            | 원하는 피자를 선택 했어야 한다.                           |
| Postconditions:                           | X                                                   |
| Flow of Events for Main Success Scenario: |                                                     |
| →                                         | 1. 장바구니를 선택한다.                     |
| ←                                         | 2. 고객이 선택한 피자 목록을 보여준다.             |
| →                                         | 3. 선택한 피자에 대해 수정 및 취소를 한다.                     |
| ←                                         | 4. 수정 및 취소가 된 장바구니를 보여준다.            |

---

| Use Case UC-4:                            | 주문 정보 확인                                      |
| ----------------------------------------- | --------------------------------------------------- |
| Related Requirement:                      | FR9, FR10                                                |
| Initiating Actor:                         | 고객                                            |
| Actor's Goal:                             | 주문이 정상적으로 들어갔음과 배달 현황/픽업 시간을 확인할 수 있어야 한다.  |
| Participating Actors:                     | 타이머                                                   |
| Preconditions:                            | 1.결제가 완료 되어 있어야 한다.
|                                           | 2.배달/픽업 시간의 타이머가 작동해야한다.                    |
| Postconditions:                           | X                                                   |
| Flow of Events for Main Success Scenario: |                                                     |
| →                                         | 1. 주문 정보 확인을 선택한다.                     |
| ←                                         | 2. 주문 정보와 주문 상태(배달 상황 등)을 보여준다.            |

---

| Use Case UC-6:                            | 리뷰 보기                                      |
| ----------------------------------------- | --------------------------------------------------- |
| Related Requirement:                      | FR4                                                |
| Initiating Actor:                         | 고객                                            |
| Actor's Goal:                             | 피자 메뉴에 대한 리뷰를 확인할 수 있어야 한다.  |
| Participating Actors:                     | X                                                   |
| Preconditions:                            | 리뷰들이 존재해야 한다.
| Postconditions:                           | X                                                   |
| Flow of Events for Main Success Scenario: |                                                     |
| →                                         | 1. 리뷰를 보고 싶은 피자를 선택한다.             |
| ←                                         | 2. 해당 피자에 대한 리뷰를 보여준다.            |

---

| Use Case UC-8:                            | 결제하기                                      |
| ----------------------------------------- | --------------------------------------------------- |
| Related Requirement:                      | FR8, FR9, FR10, FR11                                                |
| Initiating Actor:                         | 고객                                            |
| Actor's Goal:                             | 장바구니를 보고 선택한 피자 목록을 보고 수정할 수 있어야 한다.  |
| Participating Actors:                     | X                                                   |
| Preconditions:                            | 원하는 피자를 선택 했어야 한다.                           |
| Postconditions:                           | X                                                   |
| Flow of Events for Main Success Scenario: |                                                     |
| →                                         | 1. 결제하기를 선택한다.                     |
| ←                                         | 2. 결제 금액을 고객에게 알려준다.             |
| →                                         | 3. 결제를 한다.                     |
| ←                                         | 4. 결제가 완료 되었음을 고객에게 알려준다.            |
