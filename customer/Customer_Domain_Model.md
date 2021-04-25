# Domain Model
## UC-1 메뉴(피자)보기
### Extracting the Responsibility
| Responsibility Description                                   | Type | Concept Name        |
| ------------------------------------------------------------ | :--: | ------------------- |
| Use Case와 관련된 모든 컨셉들의 행동을 관리하고, 적절한 컨셉에게 위임한다. |  D   | Controller          |
| 피자 메뉴를 보여주기 위한 HTML 문서                |  K   | Menu Page       |
| 디스플레이로 피자 메뉴 페이지를 생성한다.                                 |  D   | PageMaker           |
| 데이터베이스로부터 모든 피자메뉴에 대한 정보를 불러온다.  |  D   | Database Connection  |

### Extracting the Associations

| Concept Pair                     | Association Description                                      | Association Name |
| -------------------------------- | ------------------------------------------------------------ | ---------------- |
| Controller ↔ Database Connection  | Controller는 DataBaseConnection에게 전체 피자메뉴에 대한 조회를 요청을 하고 받는다. | conveys request  |
| Controller ↔ Menu Page           |  Controller는 Menu Page를 사용자에게 전달한다.        | Conveys page           |
| Controller ↔ Page Maker           |  Controller는 페이지 생성에 필요한 데이터를 전달한다.           | conveys request  |
| Page Maker ↔ Menu Page  | Page Maker는 모든 피자정보를 반영하여 페이지를 만든다.       | prepares         |

![Domain Model(UC1)](./DomainModel(UC1).jpg)

---
## UC-2 장바구니
### Extracting the Responsibility

| Responsibility Description                                   | Type | Concept Name        |
| ------------------------------------------------------------ | :--: | ------------------- |
| Use Case와 관련된 모든 컨셉들의 행동을 관리하고, 적절한 컨셉에게 위임한다. |  D   | Controller          |
| 장바구니를 열기 위해 해당 고객의 ID를 전달한다.                   |  K   | SearchRequest       |
| 고객의 장바구니를 보여주는 HTML 문서                               |  K   | Cart Page |
| 디스플레이하기 위한 HTML 문서를 생성한다.                                        |  D   | PageMaker           |
| 데이터베이스 질의문을 통해 해당하는 주문 정보를 반환한다.    |  D   | Database Connection  |


### Extracting the Associations

| Concept Pair                     | Association Description                                      | Association Name |
| -------------------------------- | ------------------------------------------------------------ | ---------------- |
| Search Request ↔ Controller       |  Controller는 조회에 필요한 조건들을 전달받는다.                | receives         |
| Controller ↔ Database Connection  | Controller는 DatabaseConnection에게 조건에 해당하는 데이터 조회를 요청한다. | conveys request  |
| Controller ↔ Cart Page           |  Controller는 Cart Page를 사용자에게 전달한다.        | posts            |
| Controller ↔ Page Maker           |  Controller는 페이지 생성에 필요한 데이터를 전달한다.           | conveys request  |
| Page Maker ↔ Cart Page  | PageMaker는 장바구니 상태를 반영하여 페이지를 만든다.       | prepares         |
| Database Connection ↔ PageMaker   | PageMaker는 DatabaseConnection로부터 주문 정보를 전달받는다. | provides data    |


### Extracting the Attributes

| Concept       | Attributes        | Attribute Description                                        |
| ------------- | ----------------- | ------------------------------------------------------------ |
| SearchRequest | Customer ID | 장바구니를 조회하기 위한 고객 ID를 가지고 . |

![Domain Model(UC2)](./DomainModel(UC2).png)

---
## UC-3 주문하기
### Extracting the Responsibility

| Responsibility Description                                   | Type | Concept Name        |
| ------------------------------------------------------------ | :--: | ------------------- |
| Use Case와 관련된 모든 컨셉들의 행동을 관리하고, 적절한 컨셉에게 위임한다. |  D   | Controller          |
| 주문에 대한 요청                |  K   | Order Request      |
| 주문관련 페이지를 보여주기 위한 HTML 문서                              |  K   | Order Page |
| 디스플레이하기 위한 HTML 문서를 생성한다.                                        |  D   | Page Maker           |
| 데이터베이스로 주문에 대한 정보를 저장한다.    |  D   | Database Connection  |

### Extracting the Associations

| Concept Pair                     | Association Description                                      | Association Name |
| -------------------------------- | ------------------------------------------------------------ | ---------------- |
| Order Request ↔ Controller       | Controller는 주문에 대해 필요한 여러 정보들을 요청을 받는다.             | receives         |
| Controller ↔ Database Connection  | Controller는 Database Connection에게  데이터 저장을 요청한다. | conveys request  |
| Controller ↔ Order  Page | Controller는 Order Page를 사용자에게 전달한다.        | posts            |
| Controller ↔ Page Maker           | Controller는 페이지 생성과 업데이트에 필요한 데이터를 전달한다.           | conveys request  |
| Page Maker ↔ Orde Info Page  | Page Maker는 주문 주문 페이지를 생성하고 주문 완료되었음을 반영한다.       | prepares         |

### Extracting the Attributes

| Concept       | Attributes        | Attribute Description                                        |
| ------------- | ----------------- | ------------------------------------------------------------ |
| Order Request | Customer ID , Order Id | 주문하기위한 고객 ID와 주문상품에대한 ID|

![Domain Model(UC3)](./DomainModel(UC3).jpg)

---
## UC-4 주문정보 확인
### Extracting the Responsibility

| Responsibility Description                                   | Type | Concept Name        |
| ------------------------------------------------------------ | :--: | ------------------- |
| Use Case와 관련된 모든 컨셉들의 행동을 관리하고, 적절한 컨셉에게 위임한다. |  D   | Controller          |
| 고객의 피자 주문 정보(결제 정보 및 주분 상태)에 해당하는 ID를 전달한다.                     |  K   | Search Request       |
| 고객의 주문 정보(결제 정보 및 주분 상태)를 보여주는 HTML 문서                               |  K   | Order Info Page |
| 디스플레이하기 위한 HTML 문서를 생성한다.                                        |  D   | Page Maker           |
| 데이터베이스 질의문을 통해 해당하는 주문 정보를 반환한다.    |  D   | Database Connection  |
| 고객에게 예상 배달/픽업 시간에 가까워지면 알려준다.    |  D   | Notifier  |


### Extracting the Associations

| Concept Pair                     | Association Description                                      | Association Name |
| -------------------------------- | ------------------------------------------------------------ | ---------------- |
| Search Request ↔ Controller       | Controller는 조회에 필요한 조건들을 전달받는다.                | receives         |
| Controller ↔ Database Connection  | Controller는 Database Connection에게 조건에 해당하는 데이터 조회를 요청한다. | conveys request  |
| Controller ↔ Order Info Page | Controller는 Order Info tPage를 사용자에게 전달한다.        | posts            |
| Controller ↔ Page Maker           | Controller는 페이지 생성에 필요한 데이터를 전달한다.           | conveys request  |
| Page Maker ↔ Orde Info Page  | Page Maker는 주문 상세 정보와 주문 상태를 담고 있는 페이지를 만든다.      | prepares         |
| Database Connection ↔ Page Maker   | PageMaker는 Database Connection로부터 주문 상세 정보와 주문 상태를 전달받는다. | provides data    |
| Notifier ↔ Controller  | Controller는 Notifier가 배달/픽업 예상 시간에 근접했다는 정보를 전달받는다. | notifies time  |


### Extracting the Attributes

| Concept       | Attributes        | Attribute Description                                        |
| ------------- | ----------------- | ------------------------------------------------------------ |
| SearchRequest | Order Id | 해당 주문의 ID(정보)를 가지고 있다. |
| Nofitier | Time Info | 해당 주문의 시간 정보를 가지고 있다. |

![Domain Model(UC4)](./DomainModel(UC4).png)

---
## UC-5 리뷰 작성하기
### Extracting the Responsibility

| Responsibility Description                                   | Type | Concept Name        |
| ------------------------------------------------------------ | :--: | ------------------- |
| Use Case와 관련된 모든 컨셉들의 행동을 관리하고, 적절한 컨셉에게 위임한다. |  D   | Controller          |
| 입력 받은 리뷰에 대한 저장 요청            |  K   | Review Request       |
| 리뷰 페이지를 보여주기 위한 HTML 문서                               |  K   | Review Page |
| 디스플레이하기 위한 HTML 문서를 생성한다.                                        |  D   | Page Maker           |
| 사용자가 주문한 메뉴에 대한정보를 데이터베이스로 받고 사용자가 작성한 리뷰에 대한 데이터를 저장함   |  D   | Database Connection  |

### Extracting the Associations

| Concept Pair                     | Association Description                                      | Association Name |
| -------------------------------- | ------------------------------------------------------------ | ---------------- |
| Review  Request ↔ Controller       | Controller는 조회에 대해 필요한 여러 정보들을 요청한다.
컨트롤러는 리뷰 저장에 대해 필요한 여러정보 들을 입력받은 후 요청한다.
                | receives         |
| Controller ↔ Database Connection  | Controller는 Database Connection에게 데이터 저장을 요청한다. | conveys request  |
| Controller ↔ Review Page | Controller는 해당 피자 Review 작성 Page를 고객에게 전달한다.       | posts            |
| Controller ↔ Page Maker           | Controller는 페이지 생성에 필요한 데이터를 전달한다.           | conveys request  |
| Page Maker ↔ Review Page           | Page Maker는 사용자가 주문한 피자 정보를 반영하여 리뷰 작성 페이지를 만든다.      | prepares         |


### Extracting the Attributes

| Concept       | Attributes        | Attribute Description                                        |
| ------------- | ----------------- | ------------------------------------------------------------ |
| Review Request | Customer ID , OrderId | 주문한 고객 ID와 주문상품에대한 ID|
  
![Domain Model(UC5)](./DomainModel(UC5).jpg)

---
## UC-6 리뷰보기
### Extracting the Responsibility

| Responsibility Description                                   | Type | Concept Name        |
| ------------------------------------------------------------ | :--: | ------------------- |
| Use Case와 관련된 모든 컨셉들의 행동을 관리하고, 적절한 컨셉에게 위임한다. |  D   | Controller          |
| 리뷰를 보고 싶은 피자의 ID를 전달한다.                  |  K   | Search Request       |
| 해당 피자에 관한 리뷰들을 보여주는 HTML 문서                               |  K   | Review Page |
| 디스플레이하기 위한 HTML 문서를 생성한다.                                        |  D   | Page Maker           |
| 데이터베이스 질의문을 통해 해당하는 피자에 대한 리뷰들을 반환한다.    |  D   | Database Connection  |


### Extracting the Associations

| Concept Pair                     | Association Description                                      | Association Name |
| -------------------------------- | ------------------------------------------------------------ | ---------------- |
| Search Request ↔ Controller       | Controller는 조회에 필요한 조건들을 전달받는다.                | receives         |
| Controller ↔ Database Connection  | Controller는 Database Connection에게 조건에 해당하는 데이터 조회를 요청한다. | conveys request  |
| Controller ↔ OReview Page | Controller는 해당 피자 Review Page를 고객에게 전달한다.       | posts            |
| Controller ↔ Page Maker           | Controller는 페이지 생성에 필요한 데이터를 전달한다.           | conveys request  |
| Page Maker ↔ Review Page           | Page Maker는 해당 피자에 관한 리뷰들을 담고 있는 페이지를 만든다.      | prepares         |
| Database Connection ↔ Page Maker   | PageMaker는 Database Connection로부터 해당 피자에 리뷰 정보를 전달받는다. | provides data    |



### Extracting the Attributes

| Concept       | Attributes        | Attribute Description                                        |
| ------------- | ----------------- | ------------------------------------------------------------ |
| SearchRequest | Pizza ID | 해당 피자 이름(ID)을 가지고 있다. |


![Domain Model(UC6)](./DomainModel(UC6).png)


---
## UC-7 로그인
### Extracting the Responsibility


| Responsibility Description                                   | Type | Concept Name        |
| ------------------------------------------------------------ | :--: | ------------------- |
| Use Case와 관련된 모든 컨셉들의 행동을 관리하고, 적절한 컨셉에게 위임한다. |  D   | Controller          |
| 사용자 정보에 대한 조회 요청                   |  K   | Get Request       |
| 로그인 페이지를 보여주기 위한 HTML 문서                            |  K   | Login Page |
| 디스플레이하기 위한 HTML 문서를 생성한다.                                        |  D   | Page Maker           |
| 요청을 통해 받은 사용자 정보를 이용하여 데이터베이스에게 쿼리 요청    |  D   | Database Connection  |

### Extracting the Associations

| Concept Pair                     | Association Description                                      | Association Name |
| -------------------------------- | ------------------------------------------------------------ | ---------------- |
| Search Request ↔ Controller       | Controller는 조회에 필요한 조건들을 전달받는다.                | receives         |
| Controller ↔ Database Connection  | Controller는 Database Connection에게 조건에 해당하는 데이터 조회를 요청한다. | conveys request  |
| Controller ↔ Login Page | Controller는 결제하기 위한 Payment Page를 고객에게 전달한다.        | posts            |
| Controller ↔ Page Maker           | Controller는 페이지 생성에 필요한 데이터를 전달한다.           | conveys request  |
| Page Maker ↔ Login Page  | Page Maker는 로그인 페이지를 만들고 로그인 정보를 반영하여 페이지를 업데이트 한다.      | prepares         |

### Extracting the Attributes

| Concept       | Attributes        | Attribute Description                                        |
| ------------- | ----------------- | ------------------------------------------------------------ |
| Login Request | User ID | 로그인 ID|

![Domain Model(UC9)](./DomainModel(UC9).jpg)
