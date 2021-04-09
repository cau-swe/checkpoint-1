# Domain Model


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

## UC-8 결제하기
### Extracting the Responsibility

| Responsibility Description                                   | Type | Concept Name        |
| ------------------------------------------------------------ | :--: | ------------------- |
| Use Case와 관련된 모든 컨셉들의 행동을 관리하고, 적절한 컨셉에게 위임한다. |  D   | Controller          |
| 결제하려는 피자들의 ID를 전달한다.                    |  K   | Search Request       |
| 주문한 피자들을 결제하기 위한 HTML 문서                              |  K   | Payment Page |
| 디스플레이하기 위한 HTML 문서를 생성한다.                                        |  D   | Page Maker           |
| 데이터베이스 질의를 통해 해당 피자에 대한 가격 정보를 반환한다.    |  D   | Database Connection  |
| 주문하려는 피자들의 총 가격을 계산한다.    |  D   | Calculator  |


### Extracting the Associations

| Concept Pair                     | Association Description                                      | Association Name |
| -------------------------------- | ------------------------------------------------------------ | ---------------- |
| Search Request ↔ Controller       | Controller는 조회에 필요한 조건들을 전달받는다.                | receives         |
| Controller ↔ Database Connection  | Controller는 Database Connection에게 조건에 해당하는 데이터 조회를 요청한다. | conveys request  |
| Controller ↔ Payment Page | Controller는 결제하기 위한 Payment Page를 고객에게 전달한다.        | posts            |
| Controller ↔ Page Maker           | Controller는 페이지 생성에 필요한 데이터를 전달한다.           | conveys request  |
| Page Maker ↔ Payment Page  | Page Maker는 피자를 결제하기 위한 페이지를 만든다.      | prepares         |
| Database Connection ↔ Page Maker   | PageMaker는 Database Connection로부터 주문 상세 정보와 주문 상태를 전달받는다. | provides data    |
| Calculator ↔ Database Connection  | Calculator는 Database Connection에게 가격을 계산하고 전달해준다. | calculates data  |



### Extracting the Attributes

| Concept       | Attributes        | Attribute Description                                        |
| ------------- | ----------------- | ------------------------------------------------------------ |
| SearchRequest | Pizza ID | 해당 피자 이름(ID)을 가지고 있다. |
| Calculator | Pizza Price |  해당 피자의 가격 정보를 가지고 있다.   |

![Domain Model(UC8)](./DomainModel(UC8).png)
