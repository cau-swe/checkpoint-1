### Deriving Use Cases from System Requirements
|  Actor   |       Actor's Goal       |         Use Case Name				  |
|:--------:|:------------------------:|:-----------------------------:|
| Administrator    |		시스템 접속후 관리자 권환획득     |	Log in(UC-1)
| Administrator    |		피자정보 추가     |	Add Pizza(UC-2),Log in(UC-1)
| Administrator	   |	  피자정보 수정     |	Edit Pizza(UC-3),Log in(UC-1)
| Administrator    |		피자정보 삭제     |	Delete Pizza(UC-4),Log in(UC-1)
| Administrator    |		주문 기록 확인    |	View Order Records(UC-5),Log in(UC-1)
| Administrator    |		리뷰확인          |	View Review(UC-6),Log in(UC-1)
| Administrator    |		직원정보 추가	    | Add Employee(UC-7),Log in(UC-1)
| Administrator    |		직원정보 수정	    | Edit Employee(UC-8),Log in(UC-1)
| Administrator    |		직원정보 삭제	    | Delete Employee(UC-9),Log in(UC-1)
| 피자정보저장소    |  피자정보 저장 및 정보 제공 | Add Pizza(UC-2), Edit Pizza(UC-3), Delete Pizza(UC-4)
| 주문기록저장소	   |	주문기록 저장 및 정보 제공    | View Order Records(UC-5)
| 회원정보저장소	   |	관리자 및 직원정보 저장 및 정보 제공    | Add Employee(UC-7), Edit Employee(UC-8), Delete Employee(UC-9)
| 리뷰저장소	       |	리뷰 저장 및 정보 제공        | View Review(UC-6)
| Customer         |      회원가입        | Sign up(UC-12)
| Administrator     |  
| Customer          |  고객에서 직원으로 변경시 직원권한 획득 | ChangeAuthority( UC-13)  |

피자정보(사이즈, 사진, 이름, 설명, 가격)
직원정보(이름, 전화번호, 월급, ID, 비밀번호, 직원권한)
고객정보(이름, 전화번호, 주소, ID, 비밀번호, 고객권한)

#### Generalizations
- Add Pizza, Edit Pizza, Delete Pizza → Manage Pizza(UC-10)
- Add Employee, Edit Employee, Delete Employee → Manage Employee(UC-11)
- 피자정보저장소, 주문기록저장소, 회원정보저장소, 리뷰저장소 → Database

#### Relationships
UC-1 include UC-6

|  Actor   |       Actor's Goal       |         Use Case Name         |
|:--------:|:------------------------:|:-----------------------------:|
| Administrator    |		시스템 접속후 관리자 권환획득  |	Log in(UC-1)
| Administrator    |		피자정보 추가, 수정, 삭제     |	Manage Pizza(UC-10), Add Pizza(UC-2), Edit Pizza(UC-3), Delete Pizza(UC-4), Log in(UC-1)
| Administrator    |		주문 기록 확인                |	View Order Records(UC-5), Log in(UC-1)
| Administrator    |		리뷰확인                      |	View Review(UC-6), Log in(UC-1)
| Administrator    |		직원정보 추가, 수정, 삭제	    | Manage Employee(UC-11), Add Employee(UC-7), Edit Employee(UC-8), Delete Employee(UC-9), Log in(UC-1)
| Database         |  피자정보, 주문기록, 회원정보, 리뷰저장 및 정보 제공 | Manage Pizza(UC-10), Add Pizza(UC-2), Edit Pizza(UC-3), Delete Pizza(UC-4), View Order Records(UC-5), Manage Employee(UC-11), Add Employee(UC-7), Edit Employee(UC-8), Delete Employee(UC-9), View Review(UC-6)
| Customer         |      회원가입        | Sign up(UC-12)


|  Req't   |  PW  | UC1  | UC2  | UC3  | UC4  | UC5  | UC6  | UC7  | UC8  | UC9  | UC10 | UC11 | UC12 |
| :------: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: |
|   REQ1   |  3   |  X   |      |      |      |      |      |      |      |      |      |      ||
|   REQ2   |  5   |  X   |  X   |      |      |      |      |      |      |      |  X   |      ||
|   REQ3   |  4   |  X   |      |  X   |  X   |      |      |      |      |      |  X   |      ||
|   REQ4   |  2   |  X   |      |      |      |  X   |      |      |      |      |      |      ||
|   REQ5   |  2   |  X   |      |      |      |      |  X   |      |      |      |      |      ||
|   REQ6   |  5   |  X   |      |      |      |      |      |  X   |  X   |  X   |      |  X   | |
|   REQ7   |  1   |  X   |      |      |      |      |      |  X   |  X   |      |      |  X   ||
|   REQ8   |  5   |      |      |      |      |      |      |      |      |      |      |      |   X  |      
|  Max PW  |      |  5   |  5   |  4   |  4   |  2   |  2   |  5   |  5   |  5   |  5   |  5   |  5   |
| Total PW |      |  24  |  5   |  4   |  4   |  2   |  2   |  8   |  8   |  5   |  9   |  8   |  5   |

---

| Use Case UC-1:                            |  Log in                                             |
| ----------------------------------------- | --------------------------------------------------- |
| Related Requirement:                      | REQ1,REQ2,REQ3,REQ4,REQ5,REQ6,REQ7             |
| Initiating Actor:                         | Administrator                                       |
| Actor's Goal:                             | - 시스템을 관리하기 위해, 시스템에 관리자 권한으로 접속한다.         |
| Participating Actors:                     | Database                                            |
| Preconditions:                            | - Database에 관리자로 등록이 되어있어야 한다.        |
|                                           | - 프로그램을 실행하여 로그인 화면에 접속된 상태이다. |
| Postconditions:                           | - 관리자권한을 가지고 관리페이지에 접속이 되어있다.  |
| Flow of Events for Main Success Scenario: |                                                     |
| →                                         | 1. ID입력창에 ID를 입력하고 비밀번호 입력창에 비밀번호를 입력한 다음 로그인버튼을 누른다.       |
| ←                                         | 2. System은 입력된 ID와 비밀번호가 Database에 있는지 확인하고 관리자인지 확인한다.       |
| ←                                         | 3. System은 Administrator에게 로그인에 성공했다고 알려주고 관리자권한을 부여한다.   |
| ←                                         | 4. System은 Administrator에게 관리페이지를 보여준다.     |
|Flow of Events for Extensions (Alternate Scenarios): ||
|2a. 입력된 ID와 비밀번호가 Database에 없는 경우||
| ←                                         | 1. System은 Administrator에게 잘못된 ID또는 잘못된 비밀번호라고 알려준다. |
| →                                         | 2. Administrator는 ID와 비밀번호를 다시 입력한다.|
|                                           | 3. 위에 3,4번과정과 같다.|
|2b. 해당계정이 관리자가 아닌 경우||
| ←                                         | 1. System은 직원이 로그인시도를 하는 경우 직원의 권한을 주고, 고객일 경우 고객권한을 부여한다.|

---

| Use Case UC-2:                            |  Add Pizza                                          |
| ----------------------------------------- | --------------------------------------------------- |
| Related Requirement:                      | REQ2                                                |
| Initiating Actor:                         | Administrator                                       |
| Actor's Goal:                             | - 새로운 피자추가시, 피자정보를 입력할 수 있다.      |
| Participating Actors:                     | Database                                            |
| Preconditions:                            | - 관리자권한을 가지고 로그인된 상태이다.                 |
|                                           | - 현재 피자관리페이지에 접속해있고 Add Pizza버튼을 보고있다. |
| Postconditions:                           | - 새로운 피자의 정보가 입력되어있는 상태이다.        |
| Flow of Events for Main Success Scenario: |                                                     |
| →                                         | 1. Add 버튼을 누른다.       |
| ←                                         | 2. System은 새로운 피자를 입력하는 창을 보여준다.    |
| →                                         | 3. Administrator는 입력창에 피자에 대한 정보(사이즈, 사진, 이름, 설명, 가격)를 입력한다. |
| ←                                         | 4. System은 피자정보를 Database에 저장한다.          |
| ←                                         | 5. System은 Administrator에게 업데이트된 페이지를 보여준다. |
|Flow of Events for Extensions (Alternate Scenarios): ||
|3a. Administrator가 어떤 정보를 누락했을 경우||
| ←                                         | 1. (a)System은 공란을 확인한다. (b) administrator에게 공란이 있다고 알려준다.|
| →                                         | 2. Administrator는 누락된 정보를 다시 입력한다.|
|                                           | 3. 위에 4,5번과정과 같다.|

---

| Use Case UC-3:                            |  Edit Pizza                                          |
| ----------------------------------------- | --------------------------------------------------- |
| Related Requirement:                      | REQ3                                                |
| Initiating Actor:                         | Administrator                                       |
| Actor's Goal:                             | - 새로 업데이트된 피자정보를 수정할 수 있다.      |
| Participating Actors:                     | Database                                            |
| Preconditions:                            | - 관리자권한으로 로그인된 상태이다.                 |
|                                           | - 현재 피자관리페이지에 접속해있고 피자목록에 있는 Edit버튼을 보고있다.         |
| Postconditions:                           | - 새로운 피자의 정보가 업데이트 되어있는 상태이다.        |
| Flow of Events for Main Success Scenario: |                                                     |
| →                                         | 1. Edit 버튼을 누른다.       |
| ←                                         | 2. System은 피자정보를 수정할 수 있는 창을 보여준다.(기존정보가 표시되어있는 입력창)    |
| →                                         | 3. Administrator는 입력창에 변경된 정보를 입력한다. |
| ←                                         | 4. System은 피자정보를 Database에 저장한다.          |
| ←                                         | 5. System은 Administrator에게 업데이트된 페이지를 보여준다. |
|Flow of Events for Extensions (Alternate Scenarios): ||
|3a. Administrator가 어떤 정보를 누락했을 경우||
| ←                                         | 1. (a)System은 공란을 확인한다. (b) administrator에게 공란이 있다고 알려준다.|
| →                                         | 2. Administrator는 누락된 정보를 다시 입력한다.|
|                                           | 3. 위에 4,5번과정과 같다.|

---

| Use Case UC-4:                            |  Delete Pizza                                          |
| ----------------------------------------- | --------------------------------------------------- |
| Related Requirement:                      | REQ3                                                |
| Initiating Actor:                         | Administrator                                       |
| Actor's Goal:                             | - 더 이상 팔지 않는 피자의 정보를 삭제할 수 있다.    |
| Participating Actors:                     | Database                                            |
| Preconditions:                            | - 관리자권한으로 로그인된 상태이다.                 |
|                                           | - 현재 피자관리페이지에 접속해있고 Delete Pizza버튼을 보고있다.         |
| Postconditions:                           | - 삭제하고자 하는 피자의 정보가 삭제되어 있는 상태이다.        |
| Flow of Events for Main Success Scenario: |                                                     |
| →                                         | 1. Delete 버튼을 누른다.       |
| ←                                         | 2. System은 삭제하고자 하는 피자가 무엇인지 선택할 수 있는 창을 보여준다.    |
| →                                         | 3. Administrator는 삭제하고자 하는 피자를 선택한다.  |
| ←                                         | 4. System은 Database에 선택된 피자정보를 삭제한다.          |
| ←                                         | 5. System은 Administrator에게 업데이트된 페이지를 보여준다. |

---

| Use Case UC-5:                            |  View Order Records                                 |
| ----------------------------------------- | --------------------------------------------------- |
| Related Requirement:                      | REQ4                                                |
| Initiating Actor:                         | Administrator                                       |
| Actor's Goal:                             | - 현재까지 어떤 피자가 판매되었는지 기록을 확인할 수 있다.    |
| Participating Actors:                     | Database                                            |
| Preconditions:                            | - 관리자권한으로 로그인된 상태이다.             |
|                                           | - 관리자페이지에서 Order Records 버튼을 보고있다. |
| Postconditions:                           | - 주문기록이 나오는 페이지를 보고있는 상태이다.      |
| Flow of Events for Main Success Scenario: |                                                     |
| →                                         | 1. Order Records 버튼을 누른다.       |
| ←                                         | 2. System은 Database에서 주문기록을 가져온 후 관리자에게 기록을 보여준다.   |

---

| Use Case UC-6:                            |  View Review                                        |
| ----------------------------------------- | --------------------------------------------------- |
| Related Requirement:                      | REQ5                                                |
| Initiating Actor:                         | Administrator                                       |
| Actor's Goal:                             | - 피자의 품질, 서비스등을 개선하기 위해 고객들의 리뷰를 확인한다.      |
| Participating Actors:                     | Database                                            |
| Preconditions:                            | - 관리자권한으로 로그인된 상태이다.                  |
|                                           | - 관리자페이지에서 Review 버튼을 보고있다.        |
| Postconditions:                           | - 각 피자제품에 해당하는 고객의 Review를 볼 수 있다. |
| Flow of Events for Main Success Scenario: |                                                     |
| →                                         | 1. Review 버튼을 누른다.                            |
| ←                                         | 2. System은 등록되어 있는 피자목록을 보여준다.       |
| →                                         | 3. Administrator는 확인하고 싶은 Pizza를 선택한다.   |
| ←                                         | 2. System은 Database에서 해당피자의 Review정보를 가져와서 Administrator에게 보여준다.     |

---

| Use Case UC-7:                            |  Add Employee                                       |
| ----------------------------------------- | --------------------------------------------------- |
| Related Requirement:                      | REQ6,REQ7                                           |
| Initiating Actor:                         | Administrator                                       |
| Actor's Goal:                             | - 새로운 직원에 대한 정보를 추가한다.                |
| Participating Actors:                     | Database                                            |
| Preconditions:                            | - 관리자권한으로 로그인된 상태이다.                  |
|                                           | - 직원관리페이지에서 직원목록에 있는 Add 버튼을 보고있다.        |
| Postconditions:                           | - 직원관리페이지에서 추가된 직원정보가 반영된 페이지가 보인다. |
| Flow of Events for Main Success Scenario: |                                                     |
| →                                         | 1. Add 버튼을 누른다.       |
| ←                                         | 2. System은 새로운 직원정보를 입력하는 창을 보여준다.    |
| →                                         | 3. Administrator는 입력창에 직원에 대한 정보(이름, 전화번호, 월급)를 입력한다. |
| →                                         | 4. Administrator는 직원의 권한(직원/관리자)을 선택한다.
| ←                                         | 5. System은 직원정보를 Database에 저장한다.          |
| ←                                         | 6. System은 Administrator에게 업데이트된 페이지를 보여준다. |
|Flow of Events for Extensions (Alternate Scenarios): ||
|3a. Administrator가 어떤 정보를 누락했을 경우||
| ←                                         | 1. (a)System은 공란을 확인한다. (b) administrator에게 공란이 있다고 알려준다.|
| →                                         | 2. Administrator는 누락된 정보를 다시 입력한다.|
|                                           | 3. 위에 4,5,6번과정과 같다.|
|4a. 직원권한이 선택되지 않았을 경우         ||
| ←                                         | 1. System은 공란을 확인하고 Administrator에게 공란이 있다고 알린다.
| →                                         | 2. Administrator는 권한을 다시 선택한다.|
|                                           | 3. 위에 5,6번과정과 같다.|

---

| Use Case UC-8:                            |  Edit Employee                                       |
| ----------------------------------------- | --------------------------------------------------- |
| Related Requirement:                      | REQ6,REQ7                                              |
| Initiating Actor:                         | Administrator                                       |
| Actor's Goal:                             | - 직원에 대한 정보를 수정한다.                |
| Participating Actors:                     | Database                                            |
| Preconditions:                            | - 관리자권한으로 로그인된 상태이다.                  |
|                                           | - 직원관리페이지에서 직원목록에 있는 Edit 버튼을 보고있다.        |
| Postconditions:                           | - 직원관리페이지에서 수정된 직원정보가 반영된 페이지가 보인다. |
| Flow of Events for Main Success Scenario: |                                                     |
| →                                         | 1. 수정하고자하는 직원의 Edit 버튼을 누른다.       |
| ←                                         | 2. System은 Database에서 직원정보를 가져온 후 수정할 수 있는 창을 보여준다.(기존에 입력되어 있는 정보가 보이는 입력창)    |
| →                                         | 3. Administrator는 입력창에 직원에 대한 정보(이름, 전화번호, 월급)를 입력한다. |
| →                                         | 4. Administrator는 직원의 권한(직원/관리자)을 선택한다.
| ←                                         | 5. System은 직원정보를 Database에 저장한다.          |
| ←                                         | 6. System은 Administrator에게 업데이트된 페이지를 보여준다. |
|Flow of Events for Extensions (Alternate Scenarios): ||
|3a. Administrator가 어떤 정보를 누락했을 경우||
| ←                                         | 1. (a)System은 공란을 확인한다. (b) administrator에게 공란이 있다고 알려준다.|
| →                                         | 2. Administrator는 누락된 정보를 다시 입력한다.|
|                                           | 3. 위에 4,5,6번과정과 같다.|
|4a. 직원권한이 선택되지 않았을 경우         ||
| ←                                         | 1. System은 공란을 확인하고 Administrator에게 공란이 있다고 알린다.
| →                                         | 2. Administrator는 권한을 다시 선택한다.|
|                                           | 3. 위에 5,6번과정과 같다.|

---

| Use Case UC-9:                            |  Delete Employee                                       |
| ----------------------------------------- | --------------------------------------------------- |
| Related Requirement:                      | REQ7                                               |
| Initiating Actor:                         | Administrator                                       |
| Actor's Goal:                             | - 직원이 일을 그만두게 되었을 경우, 해당직원의 정보를 삭제한다.  |
| Participating Actors:                     | Database                                            |
| Preconditions:                            | - 관리자권한으로 로그인된 상태이다.                  |
|                                           | - 직원관리페이지에서 직원목록에 있는 Delete 버튼을 보고있다.        |
| Postconditions:                           | - 직원관리페이지에서 삭제된 직원정보가 반영된 페이지가 보인다. |
| Flow of Events for Main Success Scenario: |                                                     |
| →                                         | 1. 수정하고자하는 직원의 Delete 버튼을 누른다.       |
| ←                                         | 2. System은 해당직원의 정보를 Database에서 삭제한다. |
| ←                                         | 3. System은 Administrator에게 업데이트된 페이지를 보여준다. |

---

| Use Case UC-10:                           |  Manage Pizza                                       |
| ----------------------------------------- | --------------------------------------------------- |
| Related Requirement:                      | REQ2, REQ3                                          |
| Initiating Actor:                         | Administrator                                       |
| Actor's Goal:                             | - 피자정보를 추가, 수정, 삭제할 수 있다.             |
| Participating Actors:                     | Database                                            |
| Preconditions:                            | - 관리자권한으로 로그인된 상태이다.                  |
|                                           | - 관리자페이지에서 Manage Pizza버튼을 보고있다.        |
| Postconditions:                           | - 관리자페이지에서 업데이트된 정보가 반영된 페이지가 보인다. |
| Flow of Events for Main Success Scenario: |                                                     |
| →                                         | 1. Manage Pizza 버튼을 누른다.       |
| ←                                         | 2. System은 피자관리페이지를 Administrator에게 보여준다. |
| →                                         | 3. Administrator는 3개 버튼(Add, Edit, Delete)중에 선택하여 해당 작업을 진행한다. |
| ←                                         | 4. System은 Administrator에게 업데이트된 페이지를 보여준다. |
|Flow of Events for Extensions (Alternate Scenarios): ||
|3a. Add버튼을 클릭하면 새로운 피자정보를 추가한다.  | : include Add Pizza(UC-2)|
|3b. Edit버튼을 클릭하면 기존의 피자정보를 수정한다. | : include Edit Pizza(UC-3)|
|3c. Delete버튼을 클릭하면 해당 피자정보를 삭제한다. | : include Delete Pizza(UC-4)|

---

| Use Case UC-11:                           |  Manage Employee                                       |
| ----------------------------------------- | --------------------------------------------------- |
| Related Requirement:                      | REQ6, REQ7                                          |
| Initiating Actor:                         | Administrator                                       |
| Actor's Goal:                             | - 직원정보를 추가, 수정, 삭제할 수 있다.             |
| Participating Actors:                     | Database                                            |
| Preconditions:                            | - 관리자권한으로 로그인된 상태이다.                  |
|                                           | - 관리자페이지에서 Manage Employee버튼을 보고있다.        |
| Postconditions:                           | - 관리자페이지에서 업데이트된 정보가 반영된 페이지가 보인다. |
| Flow of Events for Main Success Scenario: |                                                     |
| →                                         | 1. Manage Employee 버튼을 누른다.       |
| ←                                         | 2. System은 직원관리페이지를 Administrator에게 보여준다. |
| →                                         | 3. Administrator는 3개 버튼(Add, Edit, Delete)중에 선택하여 해당 작업을 진행한다. |
| ←                                         | 4. System은 Administrator에게 업데이트된 페이지를 보여준다. |
|Flow of Events for Extensions (Alternate Scenarios): ||
|3a. Add버튼을 클릭하면 새로운 직원정보를 추가한다.  | : include Add Employee(UC-7)|
|3b. Edit버튼을 클릭하면 기존의 직원정보를 수정한다. | : include Edit Employee(UC-8)|
|3c. Delete버튼을 클릭하면 해당 직원정보를 삭제한다. | : include Delete Employee(UC-9)|

| Use Case UC-12:                           |  Sign up                                       |
| ----------------------------------------- | --------------------------------------------------- |
| Related Requirement:                      | REQ8                                          |
| Initiating Actor:                         | Customer                                    |
| Actor's Goal:                             | - 고객은 회원가입을 할 수 있다.            |
| Participating Actors:                     | Database                                            |
| Preconditions:                            | - 고객이 시스템에 접속된 상태이다.                |
|                                           | - 피자메뉴페이지에서 회원가입버튼을 보고있다.       |
| Postconditions:                           | - 회원가입이 완료되서 데이터베이스에 등록된 상태이다. |
| Flow of Events for Main Success Scenario: |                                                     |
| →                                         | 1. 회원가입 버튼을 누른다.       |
| ←                                         | 2. System은 회원가입페이지를 고객에게 보여준다. |
| →                                         | 3. 고객은 회원정보를 입력한다. (주문시 위치의 기본설정값, 전화번호, 이름, 아이디, 비밀번호) |
| ←                                         | 4. System은 고객에게 고객권한(주문가능, 주문 시 리뷰작성가능)을 부여한다. |
| ←                                         | 5. System은 데이터베이스에 고객정보를 저장한다. |
