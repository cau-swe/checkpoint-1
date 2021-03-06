## UC-2 Add Pizza
### Extracting the Responsibility

| Responsibility Description                                   | Type | Concept Name        |
| ------------------------------------------------------------ | :--: | ------------------- |
| Use Case와 관련된 모든 컨셉들의 행동을 관리하고, 적절한 컨셉에게 위임한다. |  D   | Controller          |
| 새로운 Pizza에 대한 정보 입력 요청                  |  K   | AddRequest       |
| Pizza에 대한 정보를 입력할 수 있도록하는 HTML 문서  |  K   | InputPage |
| InputPage에 대한 HTML 문서를 생성한다.              |  D   | PageMaker           |
| 추가된 Pizza가 반영된 새로운 피자관리페이지 HTML문서 | K    | UpdatedPage        |
| 추가된 Pizza가 반영된 새로운 피자관리페이지 HTML문서를 생성한다.    | D    | PageMaker    |
| 입력된 피자정보를 데이터베이스에 저장할 수 있도록 하는 input parameter      | K    | StoreRequest |
| 입력된 피자정보를 저장하는 쿼리문생성, 데이터 저장    |  D   | DatabaseConnection  |
| 누락된 정보를 확인한다.                              |  D   | BlankChecker        |
| 누락된 정보를 사용자에게 알린다                       | D   | Controller          |
| 누락된 정보가 있음을 알려주는 경고메시지              |  K  | Warning             |
| 누락된 정보에 대한 경고메시지를 만든다                |  D  | PageMaker           |

### Extracting the Associations

| Concept Pair                    | Association Description                                      | Association Name |
| ------------------------------- | ------------------------------------------------------------ | ---------------- |
| AddRequest ↔ Controller         | Controller는 새로운 피자정보 입력에 대한 요청을 전달받는다.   | receives         |
| Controller ↔ PageMaker          | Controller는 InputPage를 만들거나 UpdatedPage를 만들거나 Warning을 만들것을 요청한다. 그리고 만들어진 page를 받는다. | conveys request |
| PageMaker  ↔ InputPage          | PageMaker는 InputPage를 만든다.                               | prepares        |
| PageMaker  ↔ UpdatedPage        | PageMaker는 UpdatedPage를 만든다.                             | prepares        |
| PageMaker ↔ Warning             | PageMaker는 Warning을 만든다.                                 | prepares        |
| StoreRequest ↔ Controller       | Controller는 새로운 피자정보 저장에 대한 요청을 전달받는다     | receives        |
| StoreRequest ↔ BlankChecker     | StoreRequest는 BlankChecker에게 input parameter를 전달한다.   | receives        |
| Controller ↔ BlankChecker       | Controller는 input parameter에 빈칸이 있는지 물어본다.        | checks blank    |
| PageMaker ↔ Warning             | PageMaker는 Warning을 만든다.                                 | prepares        |  
| Controller ↔ DatabaseConnection | Controller는 DatabaseConnection에게 입력된 피자정보저장 요쳥을 전달한다.       | conveys request  |
| Controller ↔ InputPage          | Controller는 InputPage를 사용자에게 전달한다.                  | posts           |
| Controller ↔ UpdatedPage        | Controller는 UpdatedPage를 사용자에게 전달한다.                | posts           |
| Controller ↔ Warning            | Controller는 Warning을 사용자에게 전달한다.  | posts |


### Extracting the Attributes

| Concept       | Attributes        | Attribute Description                   |
| ------------- | ----------------- | --------------------------------------- |
| StoreRequest  | input parameters  | 사이즈, 사진, 이름, 설명, 가격          |
| PageMaker     | input parameters  | UpdatedPage를 만들때 필요하다.          |



## UC-3 Edit Pizza
### Extracting the Responsibility

| Responsibility Description                                   | Type | Concept Name        |
| ------------------------------------------------------------ | :--: | ------------------- |
| Use Case와 관련된 모든 컨셉들의 행동을 관리하고, 적절한 컨셉에게 위임한다. |  D   | Controller          |
| 선택한 Pizza에 대한 정보 수정 요청                  |  K   | EditRequest       |
| Pizza에 대한 정보를 입력할 수 있도록하는 HTML 문서  |  K   | InputPage |
| InputPage에 대한 HTML 문서를 생성한다.              |  D   | PageMaker           |
| 추가된 Pizza가 반영된 새로운 피자관리페이지 HTML문서 | K    | UpdatedPage        |
| 추가된 Pizza가 반영된 새로운 피자관리페이지 HTML문서를 생성한다.    | D    | PageMaker    |
| 수정된 피자정보를 데이터베이스에 저장할 수 있도록 하는 input parameter      | K    | StoreRequest |
| 선택한 피자정보를 검색해서 반환, 수정된 피자정보를 저장하는 쿼리문생성, 데이터 저장    |  D   | DatabaseConnection  |
| 누락된 정보를 확인한다.                              |  D   | BlankChecker        |
| 누락된 정보를 사용자에게 알린다                       | D   | Controller          |
| 누락된 정보가 있음을 알려주는 경고메시지              |  K  | Warning             |
| 누락된 정보에 대한 경고메시지를 만든다                |  D  | PageMaker           |

### Extracting the Associations

| Concept Pair                    | Association Description                                      | Association Name |
| ------------------------------- | ------------------------------------------------------------ | ---------------- |
| EditRequest ↔ Controller        | Controller는 선택된 피자정보 수정에 대한 요청을 전달받는다.   | receives         |
| Controller ↔ PageMaker          | Controller는 InputPage를 만들거나 UpdatedPage를 만들거나 Warning을 만들것을 요청한다. 그리고 만들어진 page를 받는다. | conveys request |
| PageMaker  ↔ InputPage          | PageMaker는 InputPage를 만든다.                               | prepares        |
| PageMaker  ↔ UpdatedPage        | PageMaker는 UpdatedPage를 만든다.                             | prepares        |
| PageMaker ↔ Warning             | PageMaker는 Warning을 만든다.                                 | prepares        |
| StoreRequest ↔ Controller       | Controller는 수정된 피자정보 저장에 대한 요청을 전달받는다     | receives        |
| StoreRequest ↔ BlankChecker     | StoreRequest는 BlankChecker에게 input parameter를 전달한다.   | receives        |
| Controller ↔ BlankChecker       | Controller는 input parameter에 빈칸이 있는지 물어본다.        | checks blank    |
| PageMaker ↔ Warning             | PageMaker는 Warning을 만든다.                                 | prepares        |  
| Controller ↔ DatabaseConnection | Controller는 DatabaseConnection에게 선택된 피자정보요청을 전달한다, 입력된 피자정보저장 요쳥을 전달한다.       | conveys request  |
| DatabaseConnection  ↔ PageMaker | DatabaseConnection은 선택된 피자 정보를 PageMaker에게 전달한다  | provides-data   |
| Controller ↔ InputPage          | Controller는 InputPage를 사용자에게 전달한다.                  | posts           |
| Controller ↔ UpdatedPage        | Controller는 UpdatedPage를 사용자에게 전달한다.                | posts           |
| Controller ↔ Warning            | Controller는 Warning을 사용자에게 전달한다.  | posts |


### Extracting the Attributes

| Concept       | Attributes        | Attribute Description                   |
| ------------- | ----------------- | --------------------------------------- |
| EditRequest   | pizza ID          | 어떤 피자를 수정할 지에 대한 정보        |
| StoreRequest  | input parameters  | 사이즈, 사진, 이름, 설명, 가격          |
| PageMaker     | input parameters  | UpdatedPage를 만들때 필요하다.          |



## UC-4 Delete Pizza
### Extracting the Responsibility

| Responsibility Description                                   | Type | Concept Name        |
| ------------------------------------------------------------ | :--: | ------------------- |
| Use Case와 관련된 모든 컨셉들의 행동을 관리하고, 적절한 컨셉에게 위임한다. |  D   | Controller          |
| 어떤 Pizza를 삭제할 것인지를 선택할 수 있도록 요청함                  |  K   | SelectRequest       |
| 삭제할 Pizza를 선택할 수 있도록하는 HTML 문서 |  K  | SelectPage |
| SelectPage에 대한 HTML 문서를 생성한다.       |  D   | PageMaker           |
| 삭제된 Pizza가 반영된 새로운 피자관리페이지 HTML문서 | K    | UpdatedPage        |
| 삭제된 Pizza가 반영된 새로운 피자관리페이지 HTML문서를 생성한다.    | D    | PageMaker    |
| 삭제된 피자정보를 데이터베이스에서 삭제할 수 있도록 하는 delete parameter      | K    | DeleteRequest |
| 선택된 피자정보를 삭제하는 쿼리문생성, 데이터 저장    |  D   | DatabaseConnection  |

### Extracting the Associations

| Concept Pair                    | Association Description                                      | Association Name |
| ------------------------------- | ------------------------------------------------------------ | ---------------- |
| SelectRequest ↔ Controller      | Controller는 삭제할 피자 선택에 대한 요청을 전달받는다.       | receives         |
| Controller ↔ PageMaker          | Controller는 InputPage를 만들거나 UpdatedPage를 만든다 그리고 만들어진 page를 받는다. | conveys request |
| PageMaker  ↔ InputPage          | PageMaker는 InputPage를 만든다.                               | prepares        |
| PageMaker  ↔ UpdatedPage        | PageMaker는 UpdatedPage를 만든다.                             | prepares        |
| DeleteRequest ↔ Controller      | Controller는 선택한 피자정보 삭제에 대한 요청을 전달받는다     | receives        | 
| Controller ↔ DatabaseConnection | Controller는 DatabaseConnection에게 선택된 피자정보삭제 요쳥을 전달한다.       | conveys request  |
| Controller ↔ InputPage          | Controller는 InputPage를 사용자에게 전달한다.                  | posts           |
| Controller ↔ UpdatedPage        | Controller는 UpdatedPage를 사용자에게 전달한다.                | posts           |


### Extracting the Attributes

| Concept       | Attributes        | Attribute Description                   |
| ------------- | ----------------- | --------------------------------------- |
| DeleteRequest | delete parameters | 어떤 피자를 삭제할 지에 대한 정보, 여러 개의 pizzaID |
| PageMaker     | delete parameters | UpdatedPage를 만들때 필요하다.          |


## UC-5 View Order Records
### Extracting the Responsibility

| Responsibility Description                                   | Type | Concept Name        |
| ------------------------------------------------------------ | :--: | ------------------- |
| Use Case와 관련된 모든 컨셉들의 행동을 관리하고, 적절한 컨셉에게 위임한다. |  D   | Controller          |
| Order Records를 보여달라고 요청                               |   K     | ViewRequest   |
| 데이터베이스에 있는 Order Records를 반환한다                  |  D      | DatabaseConnection|
| 획득한 Order Records기록이 정렬된 HTML Page                    |  K     |  RecordsPage   |
| 획득한 Order Records기록을 사용자가 볼 수 있도록 HTML Page 제작  |  D    | PageMaker     |

### Extracting the Associations

| Concept Pair                    | Association Description                                      | Association Name |
| ------------------------------- | ------------------------------------------------------------ | ---------------- |
| ViewRequest ↔ Controller        | Controller는 Order Records기록에 대한 요청을 전달받는다.      | receives         |
| Controller ↔ PageMaker          | Controller는 PageMaker에게 RecordPage를 만들라고 요청한다 그리고 만들어진 page를 받는다. | conveys request |
| PageMaker  ↔ RecordPage         | PageMaker는 RecordPage를 만든다.                             | prepares        |
| Controller ↔ RecordPage         | Controller는 RecordPage를 사용자에게 전달한다.                | posts           |
| Controller ↔ DatabaseConnection | Controller는 DatabaseConnection에게 Order Record를 요청한다.  | conveys request |
| DatabaseConnection ↔  PageMaker | DatabaseConnection은 PageMaker에게 Order Record를 전달한다.   | provides-data   |

### Extracting the Attributes

| Concept       | Attributes        | Attribute Description                   |
| ------------- | ----------------- | --------------------------------------- |


## UC-6 View Reviews
### Extracting the Responsibility

| Responsibility Description                                   | Type | Concept Name        |
| ------------------------------------------------------------ | :--: | ------------------- |
| Use Case와 관련된 모든 컨셉들의 행동을 관리하고, 적절한 컨셉에게 위임한다. |  D   | Controller          |
| Review를 보기 원하는 피자를 선택하도록 요청                               |   K     | SelectRequest   |
| 선택한 피자에 대한 Review를 볼수있도록 요청                               |   K     | ReviewRequest   |
| 피자를 선택할 수 있도록 하는 사용자인터페이스 페이지                      |    K     | SelectPage    |
| Review기록이 정렬된 HTML Page                                            |    K     | ReviewPage    |
| 획득한 Review기록을 사용자가 볼 수 있도록 HTML Page 제작  |  D    | PageMaker     |
| 데이터베이스에 있는 Review를 반환한다                  |  D      | DatabaseConnection|

### Extracting the Associations

| Concept Pair                    | Association Description                                      | Association Name |
| ------------------------------- | ------------------------------------------------------------ | ---------------- |
| SelectRequest ↔ Controller      | Controller는 피자선택에 대한 요청을 전달받는다.               | receives         |
| Controller ↔ PageMaker          | Controller는 PageMaker에게 SelectPage 또는 ReviewPage를 만들라고 요청한다 그리고 만들어진 page를 받는다. | conveys request |
| PageMaker ↔ SelectPage          | PageMaker는 SelectPage를 만든다.                             | prepares         |
| PageMaker  ↔ RecordPage         | PageMaker는 ReviewPage를 만든다.                             | prepares        |
| Controller ↔ RecordPage         | Controller는 SelectPage를 사용자에게 전달한다.                | posts           |
| Controller ↔ RecordPage         | Controller는 ReviewPage를 사용자에게 전달한다.                | posts           |
| Controller ↔ DatabaseConnection | Controller는 DatabaseConnection에게 Review를 요청한다.  | conveys request |
| DatabaseConnection ↔  PageMaker | DatabaseConnection은 PageMaker에게 Review를 전달한다.   | provides-data   |

### Extracting the Attributes

| Concept       | Attributes        | Attribute Description                   |
| ------------- | ----------------- | --------------------------------------- |
| SelectRequest | pizzaID           | 어떤 피자를 선택했는지                  |


## UC-7 Add Employee
### Extracting the Responsibility

| Responsibility Description                                   | Type | Concept Name        |
| ------------------------------------------------------------ | :--: | ------------------- |
| Use Case와 관련된 모든 컨셉들의 행동을 관리하고, 적절한 컨셉에게 위임한다. |  D   | Controller          |
| 새로운 Employee에 대한 정보 입력 요청                  |  K   | AddRequest       |
| Employee에 대한 정보를 입력할 수 있도록하는 HTML 문서  |  K   | InputPage |
| InputPage에 대한 HTML 문서를 생성한다.              |  D   | PageMaker           |
| 추가된 Employee가 반영된 새로운 피자관리페이지 HTML문서 | K    | UpdatedPage        |
| 추가된 Employee가 반영된 새로운 피자관리페이지 HTML문서를 생성한다.    | D    | PageMaker    |
| 입력된 Employee정보를 데이터베이스에 저장할 수 있도록 하는 input parameter      | K    | StoreRequest |
| 입력된 Employee정보를 저장하는 쿼리문생성, 데이터 저장    |  D   | DatabaseConnection  |
| 누락된 정보를 확인한다.                              |  D   | BlankChecker        |
| 누락된 정보를 사용자에게 알린다                       | D   | Controller          |
| 누락된 정보가 있음을 알려주는 경고메시지              |  K  | Warning             |
| 누락된 정보에 대한 경고메시지를 만든다                |  D  | PageMaker           |

### Extracting the Associations

| Concept Pair                    | Association Description                                      | Association Name |
| ------------------------------- | ------------------------------------------------------------ | ---------------- |
| AddRequest ↔ Controller         | Controller는 새로운 Employee정보 입력에 대한 요청을 전달받는다.   | receives         |
| Controller ↔ PageMaker          | Controller는 InputPage를 만들거나 UpdatedPage를 만들거나 Warning을 만들것을 요청한다. 그리고 만들어진 page를 받는다. | conveys request |
| PageMaker  ↔ InputPage          | PageMaker는 InputPage를 만든다.                               | prepares        |
| PageMaker  ↔ UpdatedPage        | PageMaker는 UpdatedPage를 만든다.                             | prepares        |
| PageMaker ↔ Warning             | PageMaker는 Warning을 만든다.                                 | prepares        |
| StoreRequest ↔ Controller       | Controller는 새로운 Employee정보 저장에 대한 요청을 전달받는다     | receives        |
| StoreRequest ↔ BlankChecker     | StoreRequest는 BlankChecker에게 input parameter를 전달한다.   | receives        |
| Controller ↔ BlankChecker       | Controller는 input parameter에 빈칸이 있는지 물어본다.        | checks blank    |
| PageMaker ↔ Warning             | PageMaker는 Warning을 만든다.                                 | prepares        |  
| Controller ↔ DatabaseConnection | Controller는 DatabaseConnection에게 입력된 Employee정보저장 요쳥을 전달한다.       | conveys request  |
| Controller ↔ InputPage          | Controller는 InputPage를 사용자에게 전달한다.                  | posts           |
| Controller ↔ UpdatedPage        | Controller는 UpdatedPage를 사용자에게 전달한다.                | posts           |
| Controller ↔ Warning            | Controller는 Warning을 사용자에게 전달한다.  | posts |


### Extracting the Attributes

| Concept       | Attributes        | Attribute Description                   |
| ------------- | ----------------- | --------------------------------------- |
| StoreRequest  | input parameters  | 이름, 전화번호, 월급, 권한              |
| PageMaker     | input parameters  | UpdatedPage를 만들때 필요하다.          |



## UC-8 Edit Employee
### Extracting the Responsibility

| Responsibility Description                                   | Type | Concept Name        |
| ------------------------------------------------------------ | :--: | ------------------- |
| Use Case와 관련된 모든 컨셉들의 행동을 관리하고, 적절한 컨셉에게 위임한다. |  D   | Controller          |
| 선택한 Employee 대한 정보 수정 요청                  |  K   | EditRequest       |
| Employee 대한 정보를 입력할 수 있도록하는 HTML 문서  |  K   | InputPage |
| InputPage에 대한 HTML 문서를 생성한다.              |  D   | PageMaker           |
| 추가된 Employee가 반영된 새로운 피자관리페이지 HTML문서 | K    | UpdatedPage        |
| 추가된 Employee가 반영된 새로운 피자관리페이지 HTML문서를 생성한다.    | D    | PageMaker    |
| 수정된 Employee정보를 데이터베이스에 저장할 수 있도록 하는 input parameter      | K    | StoreRequest |
| 선택한 Employee정보를 검색해서 반환, 수정된 Employee정보를 저장하는 쿼리문생성, 데이터 저장    |  D   | DatabaseConnection  |
| 누락된 정보를 확인한다.                              |  D   | BlankChecker        |
| 누락된 정보를 사용자에게 알린다                       | D   | Controller          |
| 누락된 정보가 있음을 알려주는 경고메시지              |  K  | Warning             |
| 누락된 정보에 대한 경고메시지를 만든다                |  D  | PageMaker           |

### Extracting the Associations

| Concept Pair                    | Association Description                                      | Association Name |
| ------------------------------- | ------------------------------------------------------------ | ---------------- |
| EditRequest ↔ Controller        | Controller는 선택된 Employee정보 수정에 대한 요청을 전달받는다.   | receives         |
| Controller ↔ PageMaker          | Controller는 InputPage를 만들거나 UpdatedPage를 만들거나 Warning을 만들것을 요청한다. 그리고 만들어진 page를 받는다. | conveys request |
| PageMaker  ↔ InputPage          | PageMaker는 InputPage를 만든다.                               | prepares        |
| PageMaker  ↔ UpdatedPage        | PageMaker는 UpdatedPage를 만든다.                             | prepares        |
| PageMaker ↔ Warning             | PageMaker는 Warning을 만든다.                                 | prepares        |
| StoreRequest ↔ Controller       | Controller는 수정된 Employee정보 저장에 대한 요청을 전달받는다     | receives        |
| StoreRequest ↔ BlankChecker     | StoreRequest는 BlankChecker에게 input parameter를 전달한다.   | receives        |
| Controller ↔ BlankChecker       | Controller는 input parameter에 빈칸이 있는지 물어본다.        | checks blank    |
| PageMaker ↔ Warning             | PageMaker는 Warning을 만든다.                                 | prepares        |  
| Controller ↔ DatabaseConnection | Controller는 DatabaseConnection에게 선택된 Employee정보요청을 전달한다, 입력된 Employee정보저장 요쳥을 전달한다.       | conveys request  |
| DatabaseConnection  ↔ PageMaker | DatabaseConnection은 선택된 Employee 정보를 PageMaker에게 전달한다  | provides-data   |
| Controller ↔ InputPage          | Controller는 InputPage를 사용자에게 전달한다.                  | posts           |
| Controller ↔ UpdatedPage        | Controller는 UpdatedPage를 사용자에게 전달한다.                | posts           |
| Controller ↔ Warning            | Controller는 Warning을 사용자에게 전달한다.  | posts |


### Extracting the Attributes

| Concept       | Attributes        | Attribute Description                   |
| ------------- | ----------------- | --------------------------------------- |
| EditRequest   | Employee ID       | 어떤 Employee를 수정할 지에 대한 정보        |
| StoreRequest  | input parameters  | 이름, 전화번호, 월급, 권한          |
| PageMaker     | input parameters  | UpdatedPage를 만들때 필요하다.          |

## UC-9 Delete Employee
### Extracting the Responsibility

| Responsibility Description                                   | Type | Concept Name        |
| ------------------------------------------------------------ | :--: | ------------------- |
| Use Case와 관련된 모든 컨셉들의 행동을 관리하고, 적절한 컨셉에게 위임한다. |  D   | Controller          |
| 어떤 Employee를 삭제할 것인지를 선택할 수 있도록 요청함                  |  K   | SelectRequest       |
| 삭제할 Employee를 선택할 수 있도록하는 HTML 문서 |  K  | SelectPage |
| SelectPage에 대한 HTML 문서를 생성한다.       |  D   | PageMaker           |
| 삭제된 Employee가 반영된 새로운 피자관리페이지 HTML문서 | K    | UpdatedPage        |
| 삭제된 Employee가 반영된 새로운 피자관리페이지 HTML문서를 생성한다.    | D    | PageMaker    |
| 삭제된 Employee정보를 데이터베이스에서 삭제할 수 있도록 하는 delete parameter      | K    | DeleteRequest |
| 선택된 Employee정보를 삭제하는 쿼리문생성, 데이터 저장    |  D   | DatabaseConnection  |

### Extracting the Associations

| Concept Pair                    | Association Description                                      | Association Name |
| ------------------------------- | ------------------------------------------------------------ | ---------------- |
| SelectRequest ↔ Controller      | Controller는 삭제할 Employee 선택에 대한 요청을 전달받는다.       | receives         |
| Controller ↔ PageMaker          | Controller는 InputPage를 만들거나 UpdatedPage를 만든다 그리고 만들어진 page를 받는다. | conveys request |
| PageMaker  ↔ InputPage          | PageMaker는 InputPage를 만든다.                               | prepares        |
| PageMaker  ↔ UpdatedPage        | PageMaker는 UpdatedPage를 만든다.                             | prepares        |
| DeleteRequest ↔ Controller      | Controller는 선택한 Employee정보 삭제에 대한 요청을 전달받는다     | receives        | 
| Controller ↔ DatabaseConnection | Controller는 DatabaseConnection에게 선택된 Employee정보삭제 요쳥을 전달한다.       | conveys request  |
| Controller ↔ InputPage          | Controller는 InputPage를 사용자에게 전달한다.                  | posts           |
| Controller ↔ UpdatedPage        | Controller는 UpdatedPage를 사용자에게 전달한다.                | posts           |


### Extracting the Attributes

| Concept       | Attributes        | Attribute Description                   |
| ------------- | ----------------- | --------------------------------------- |
| DeleteRequest | delete parameters | 어떤 Employee를 삭제할 지에 대한 정보, 여러 개의 Employee ID |
| PageMaker     | delete parameters | UpdatedPage를 만들때 필요하다.          |
