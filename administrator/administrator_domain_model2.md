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
  
  
### Diagram   
![image](https://user-images.githubusercontent.com/37579661/115994956-2bd70280-a614-11eb-9470-a8db8d78e78a.png)
  

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

  
### Diagram    
![image](https://user-images.githubusercontent.com/37579661/115994971-3ee9d280-a614-11eb-843e-a5ae68b8e9f8.png)

  

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
  
### Diagram  
![image](https://user-images.githubusercontent.com/37579661/115994987-4e691b80-a614-11eb-92e9-4f5ca366d97b.png)


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
  
### Diagram  
![image](https://user-images.githubusercontent.com/37579661/115994997-604abe80-a614-11eb-8d07-9af9037ef243.png)
  
  
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
  
### Diagram  
![image](https://user-images.githubusercontent.com/37579661/115995004-6c368080-a614-11eb-9f32-4c30d58d75df.png)

  

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

  
### Diagram  
![image](https://user-images.githubusercontent.com/37579661/115995016-7b1d3300-a614-11eb-8527-5a7296280495.png)

  

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
  
### Diagram
![image](https://user-images.githubusercontent.com/37579661/115995031-88d2b880-a614-11eb-9aa7-144eaea94a8a.png)
  

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
  
### Diagram  
![image](https://user-images.githubusercontent.com/37579661/115995043-9c7e1f00-a614-11eb-8a42-f1ccf4d2575e.png)
  


## UC-12 Sign up
### Extracting the Responsibility

| Responsibility Description                                   | Type | Concept Name        |
| ------------------------------------------------------------ | :--: | ------------------- |
| Use Case와 관련된 모든 컨셉들의 행동을 관리하고, 적절한 컨셉에게 위임한다. |  D   | Controller          |
| 회원가입 대한 정보 입력 요청                  |  K   | SignUpRequest       |
| 회원가입에 대한 정보를 입력할 수 있도록하는 HTML 문서  |  K   | InputPage |
| InputPage에 대한 HTML 문서를 생성한다.              |  D   | PageMaker           |
| 입력된 회원가입 정보를 데이터베이스에 저장할 수 있도록 하는 input parameter      | K    | StoreRequest |
| 입력된 Employee정보를 저장하는 쿼리문생성, 데이터 저장    |  D   | DatabaseConnection  |
| 누락된 정보를 확인한다.                               | D   | BlankChecker        |
| 누락된 정보를 사용자에게 알린다                       | D   | Controller          |
| 누락된 정보가 있음을 알려주는 경고메시지              |  K  | Warning             |
| 누락된 정보에 대한 경고메시지를 만든다                |  D  | PageMaker           |
| 중복된 ID가 있는지를 확인한다.                        |  D  | RepeatChecker       |
| 중복된 ID가 있음을 사용자에게 알린다                  |  D  | Controller          |
| 중복된 ID가 있음을 알려주는 경고메시지                |  K  | Warning             |
| 중복된 ID에 대한 경고메시지를 만든다                  |  D  | PageMaker           |

### Extracting the Associations

| Concept Pair                    | Association Description                                      | Association Name |
| ------------------------------- | ------------------------------------------------------------ | ---------------- |
| SignUpRequest ↔ Controller         | Controller는 회원가입 정보 입력에 대한 요청을 전달받는다.   | receives         |
| Controller ↔ PageMaker          | Controller는 InputPage를 만들거나 UpdatedPage를 만들거나 Warning을 만들것을 요청한다. 그리고 만들어진 page를 받는다. | conveys request |
| PageMaker  ↔ InputPage          | PageMaker는 InputPage를 만든다.                               | prepares        |
| PageMaker ↔ Warning             | PageMaker는 Warning을 만든다.                                 | prepares        |
| StoreRequest ↔ Controller       | Controller는 회원가입 정보 저장에 대한 요청을 전달받는다     | receives        |
| StoreRequest ↔ BlankChecker     | StoreRequest는 BlankChecker에게 input parameter를 전달한다.   | receives        |
| StoreRequest ↔ RepeatChecker    | StoreRequest는 RepeatChecker에게 input parameter를 전달한다.   | receives        |
| Controller ↔ BlankChecker       | Controller는 input parameter에 빈칸이 있는지 물어본다.        | checks blank    |
| Controller ↔ RepeatChecker      | Controller는 RepeatChecker에게 중복된 ID가 있는지 물어본다.   | checks repeat   |
| RepeatChecker ↔ DatabaseConnection | RepeatChecker는 DatabaseConnection에서 ID정보를 가져온다.  | provides data   |
| PageMaker ↔ Warning             | PageMaker는 Warning을 만든다.                                 | prepares        |  
| Controller ↔ DatabaseConnection | Controller는 DatabaseConnection에게 입력된 회원가입 정보저장 요쳥을 전달한다.       | conveys request  |
| Controller ↔ InputPage          | Controller는 InputPage를 사용자에게 전달한다.                  | posts           |
| Controller ↔ Warning            | Controller는 Warning을 사용자에게 전달한다.                    | posts           |


### Extracting the Attributes

| Concept       | Attributes        | Attribute Description                   |
| ------------- | ----------------- | --------------------------------------- |
| StoreRequest  | input parameters  | 이름, 주소, 전화번호, ID, 비밀번호, 권한              |
| PageMaker     | input parameters  | UpdatedPage를 만들때 필요하다.          |

### Diagram  
![image](https://user-images.githubusercontent.com/37579661/115995284-a5232500-a615-11eb-8b09-5f2b4d7da4df.png)



## UC-13 Set Admin Account
### Extracting the Responsibility

| Responsibility Description                                   | Type | Concept Name        |
| ------------------------------------------------------------ | :--: | ------------------- |
| Use Case와 관련된 모든 컨셉들의 행동을 관리하고, 적절한 컨셉에게 위임한다. |  D   | Controller          |
| 입력된 관리자 계정 정보를 데이터베이스에 저장할 수 있도록 하는 input parameter      | K    | StoreRequest |
| 입력된 관리자 계정 정보를 저장하는 쿼리문생성, 데이터 저장    |  D   | DatabaseConnection  |
| 누락된 정보를 확인한다.                              |  D   | BlankChecker        |
| 누락된 정보를 사용자에게 알린다                       | D   | Controller          |
| 누락된 정보가 있음을 알려주는 경고메시지              |  K  | Warning             |
| 누락된 정보에 대한 경고메시지를 만든다                |  D  | PageMaker           |
| 중복된 ID를 확인한다.                              |  D   | RepeatChecker        |
| 중복된 ID가 있음을 사용자에게 알린다                       | D   | Controller          |
| 중복된 ID가 있음을 알려주는 경고메시지              |  K  | Warning             |
| 중복된 ID에 대한 경고메시지를 만든다                |  D  | PageMaker           |

### Extracting the Associations

| Concept Pair                    | Association Description                                      | Association Name |
| ------------------------------- | ------------------------------------------------------------ | ---------------- |
| StoreRequest ↔ Controller       | Controller는 회원가입 정보 저장에 대한 요청을 전달받는다     | receives        |
| StoreRequest ↔ BlankChecker     | StoreRequest는 BlankChecker에게 input parameter를 전달한다.   | receives        |
| StoreRequest ↔ RepeatChecker    | StoreRequest는 RepeatChecker에게 input parameter를 전달한다.   | receives       |
| PageMaker ↔ Warning             | PageMaker는 Warning을 만든다.                                 | prepares        |
| Controller ↔ BlankChecker       | Controller는 input parameter에 빈칸이 있는지 물어본다.        | checks blank    |
| Controller ↔ RepeatChecker      | Controller는 RepeatChecker에게 중복된 ID가 있는지 물어본다.   | checks repeat   |
| RepeatChecker ↔ DatabaseConnection | RepeatChecker는 DatabaseConnection에서 ID정보를 가져온다.  | provides data   | 
| Controller ↔ DatabaseConnection | Controller는 DatabaseConnection에게 입력된 직원 계정 정보저장 요쳥을 전달한다.       | conveys request  |
| Controller ↔ Warning            | Controller는 Warning을 사용자에게 전달한다.                    | posts           |


### Extracting the Attributes

| Concept       | Attributes        | Attribute Description                   |
| ------------- | ----------------- | --------------------------------------- |
| StoreRequest  | input parameters  | ID, 비밀번호, 권한              |

### Diagram  
![image](https://user-images.githubusercontent.com/37579661/115995294-b2d8aa80-a615-11eb-8685-c6f581c15108.png)
  

## UC-14 Set Employee Account
### Extracting the Responsibility

| Responsibility Description                                   | Type | Concept Name        |
| ------------------------------------------------------------ | :--: | ------------------- |
| Use Case와 관련된 모든 컨셉들의 행동을 관리하고, 적절한 컨셉에게 위임한다. |  D   | Controller          |
| 입력된 직원 계정 정보를 데이터베이스에 저장할 수 있도록 하는 input parameter      | K    | StoreRequest |
| 입력된 직원 계정 정보를 저장하는 쿼리문생성, 데이터 저장    |  D   | DatabaseConnection  |
| 누락된 정보를 확인한다.                              |  D   | BlankChecker        |
| 누락된 정보를 사용자에게 알린다                       | D   | Controller          |
| 누락된 정보가 있음을 알려주는 경고메시지              |  K  | Warning             |
| 누락된 정보에 대한 경고메시지를 만든다                |  D  | PageMaker           |
| 중복된 ID를 확인한다.                              |  D   | RepeatChecker        |
| 중복된 ID가 있음을 사용자에게 알린다                       | D   | Controller          |
| 중복된 ID가 있음을 알려주는 경고메시지              |  K  | Warning             |
| 중복된 ID에 대한 경고메시지를 만든다                |  D  | PageMaker           |

### Extracting the Associations

| Concept Pair                    | Association Description                                      | Association Name |
| ------------------------------- | ------------------------------------------------------------ | ---------------- |
| StoreRequest ↔ Controller       | Controller는 직원 계정 정보 저장에 대한 요청을 전달받는다     | receives        |
| StoreRequest ↔ BlankChecker     | StoreRequest는 BlankChecker에게 input parameter를 전달한다.   | receives        |
| StoreRequest ↔ RepeatChecker    | StoreRequest는 RepeatChecker에게 input parameter를 전달한다.   | receives       |
| PageMaker ↔ Warning             | PageMaker는 Warning을 만든다.                                 | prepares        |
| Controller ↔ BlankChecker       | Controller는 input parameter에 빈칸이 있는지 물어본다.        | checks blank    |
| Controller ↔ RepeatChecker      | Controller는 RepeatChecker에게 중복된 ID가 있는지 물어본다.   | checks repeat   |
| RepeatChecker ↔ DatabaseConnection | RepeatChecker는 DatabaseConnection에서 ID정보를 가져온다.  | provides data   | 
| Controller ↔ DatabaseConnection | Controller는 DatabaseConnection에게 입력된 직원 계정 정보 저장 요쳥을 전달한다.       | conveys request  |
| Controller ↔ Warning            | Controller는 Warning을 사용자에게 전달한다.                    | posts           |


### Extracting the Attributes

| Concept       | Attributes        | Attribute Description                   |
| ------------- | ----------------- | --------------------------------------- |
| StoreRequest  | input parameters  | ID, 비밀번호, 권한              |
  
### Diagram  
![image](https://user-images.githubusercontent.com/37579661/115995316-c08e3000-a615-11eb-88b8-1f4c2c2eb77f.png)
  

## UC-15 View Pizza Information
### Extracting the Responsibility

| Responsibility Description                                   | Type | Concept Name        |
| ------------------------------------------------------------ | :--: | ------------------- |
| Use Case와 관련된 모든 컨셉들의 행동을 관리하고, 적절한 컨셉에게 위임한다. |  D   | Controller          |
| 현재 등록된 Pizza정보 열람 요청문                                         | K    | ViewRequest |
| 등록된 Pizza정보를 불러옴, 정보 제공        |  D   | DatabaseConnection  |
| Pizza정보를 보여주는 HTML Page                   |  K   | PizzaPage     |
| Pizza정보를 사용자가 보기 좋게 PizzaPage를 만듬  |  D   | PageMaker     |

### Extracting the Associations

| Concept Pair                    | Association Description                                      | Association Name |
| ------------------------------- | ------------------------------------------------------------ | ---------------- |
| ViewRequest ↔ Controller       | Controller는 Pizza 정보 열람 요청을 전달받는다     | receives        |
| Controller ↔  DataConnection     | Controller는 Pizza 정보를 요청한다.     | receives        |
| Controller ↔ PageMaker          | Controller는 PizzaPage를 만들것을 요청한다. 그리고 만들어진 page를 받는다. | conveys request |
| PageMaker ↔ PizzaPage           | PizzaMaker는 PizzaMaker를 만든다.    | prepares    |
| DataConnection ↔ PageMaker      | DataConnection은 PageMaker에 Pizza 정보를 제공한다.   | provides data   |
| Controller ↔  PizzaPage         | Controller는 PizzaPage를 관리자에게 보여준다.      | posts |
  
### Diagram  
![image](https://user-images.githubusercontent.com/37579661/115995331-cc79f200-a615-11eb-9647-fb32a4b0ce9f.png)
  

## UC-16 View Employee Information
### Extracting the Responsibility

| Responsibility Description                                   | Type | Concept Name        |
| ------------------------------------------------------------ | :--: | ------------------- |
| Use Case와 관련된 모든 컨셉들의 행동을 관리하고, 적절한 컨셉에게 위임한다. |  D   | Controller          |
| 현재 등록된 Employee 정보 열람 요청문                                         | K    | ViewRequest |
| 등록된 Employee 정보를 불러옴, 정보 제공        |  D   | DatabaseConnection  |
| Employee 정보를 보여주는 HTML Page                   |  K   | EmployeePage     |
| Employee 정보를 사용자가 보기 좋게 EmployeePage를 만듬  |  D   | PageMaker     |

### Extracting the Associations

| Concept Pair                    | Association Description                                      | Association Name |
| ------------------------------- | ------------------------------------------------------------ | ---------------- |
| ViewRequest ↔ Controller       | Controller는 Employee 정보 열람 요청을 전달받는다     | receives        |
| Controller ↔  DataConnection     | Controller는 Employee 정보를 요청한다.     | receives        |
| Controller ↔ PageMaker          | Controller는 EmployeePage를 만들것을 요청한다. 그리고 만들어진 page를 받는다. | conveys request |
| PageMaker ↔ EmployeePage           | PizzaMaker는 EmployeeMaker를 만든다.    | prepares    |
| DataConnection ↔ PageMaker      | DataConnection은 PageMaker에 Employee 정보를 제공한다.   | provides data   |
| Controller ↔  EmployeePage         | Controller는 EmployeePage를 관리자에게 보여준다.      | posts |
  
### Diagram  
![image](https://user-images.githubusercontent.com/37579661/115995353-d7348700-a615-11eb-9a4a-e5439043f1c6.png)
  

## UC-17 View Customer Information
### Extracting the Responsibility

| Responsibility Description                                   | Type | Concept Name        |
| ------------------------------------------------------------ | :--: | ------------------- |
| Use Case와 관련된 모든 컨셉들의 행동을 관리하고, 적절한 컨셉에게 위임한다. |  D   | Controller          |
| 현재 등록된 Customer 정보 열람 요청문                                         | K    | ViewRequest |
| 등록된 Customer 정보를 불러옴, 정보 제공        |  D   | DatabaseConnection  |
| Customer 정보를 보여주는 HTML Page                   |  K   | CustomerPage     |
| Customer 정보를 사용자가 보기 좋게 CustomerPage를 만듬  |  D   | PageMaker     |

### Extracting the Associations

| Concept Pair                    | Association Description                                      | Association Name |
| ------------------------------- | ------------------------------------------------------------ | ---------------- |
| ViewRequest ↔ Controller       | Controller는 Customer 정보 열람 요청을 전달받는다     | receives        |
| Controller ↔  DataConnection     | Controller는 Customer 정보를 요청한다.     | receives        |
| Controller ↔ PageMaker          | Controller는 CustomerPage를 만들것을 요청한다. 그리고 만들어진 page를 받는다. | conveys request |
| PageMaker ↔ CustomerPage        | PageMaker는 CustomerPage를 만든다.     | prepares  |
| DataConnection ↔ PageMaker      | DataConnection은 PageMaker에 Customer 정보를 제공한다.   | provides data   |
| Controller ↔  CustomerPage       | Controller는 CustomerPage를 관리자에게 보여준다.      | posts |
  
### Diagram  
![image](https://user-images.githubusercontent.com/37579661/115995372-e1ef1c00-a615-11eb-8828-43bd3580edf6.png)
  

## UC-18 View Account
### Extracting the Responsibility

| Responsibility Description                                   | Type | Concept Name        |
| ------------------------------------------------------------ | :--: | ------------------- |
| Use Case와 관련된 모든 컨셉들의 행동을 관리하고, 적절한 컨셉에게 위임한다. |  D   | Controller          |
| 현재 등록된 Account 정보 열람 요청문                                         | K    | ViewRequest |
| 등록된 Account 정보를 불러옴, 정보 제공        |  D   | DatabaseConnection  |
| Account 정보를 보여주는 HTML Page                   |  K   | AccountPage     |
| Account 정보를 사용자가 보기 좋게 AccountPage를 만듬  |  D   | PageMaker     |

### Extracting the Associations

| Concept Pair                    | Association Description                                      | Association Name |
| ------------------------------- | ------------------------------------------------------------ | ---------------- |
| ViewRequest ↔ Controller       | Controller는 Account 정보 열람 요청을 전달받는다     | receives        |
| Controller ↔  DataConnection     | Controller는 Account 정보를 요청한다.     | receives        |
| Controller ↔ PageMaker          | Controller는 AccountPage를 만들것을 요청한다. 그리고 만들어진 page를 받는다. | conveys request |
| PageMaker ↔ AccountPage        | PageMaker는 AccountPage를 만든다.     | prepares  |
| DataConnection ↔ PageMaker      | DataConnection은 PageMaker에 Account 정보를 제공한다.   | provides data   |
| Controller ↔  AccountPage       | Controller는 AccountPage를 관리자에게 보여준다.      | posts |
   
### Diagram  
![image](https://user-images.githubusercontent.com/37579661/115995384-ea475700-a615-11eb-926f-61cfc72f7466.png)
  

## UC-19 Log out
### Extracting the Responsibility

| Responsibility Description                                   | Type | Concept Name        |
| ------------------------------------------------------------ | :--: | ------------------- |
| Use Case와 관련된 모든 컨셉들의 행동을 관리하고, 적절한 컨셉에게 위임한다. |  D   | Controller          |
| Log out 요청문                                         | K    | LogOutRequest |
| Log in할 수 있는 페이지                                | K    | LogInPage    |
| Log in 페이지를 만든다.                                | D    | PageMaker    |

### Extracting the Associations

| Concept Pair                    | Association Description                                      | Association Name |
| ------------------------------- | ------------------------------------------------------------ | ---------------- |
| LogOutRequest ↔ Controller       | Controller는 Log out 요청을 전달받는다     | receives        |
| Controller ↔ PageMaker          | Controller는 LogInPage를 만들것을 요청한다. 그리고 만들어진 page를 받는다. | conveys request |
| PageMaker ↔ LogInPage        | PageMaker는 LogInPage를 만든다.     | prepares  |
| Controller ↔  LogInPage       | Controller는 LogInPage를 관리자에게 보여준다.      | posts |

  
### Diagram  
![image](https://user-images.githubusercontent.com/37579661/115995391-f3382880-a615-11eb-8542-d76b03f62e9e.png)

  
  
## UC-1 Log in
### Extracting the Responsibility

| Responsibility Description                                   | Type | Concept Name        |
| ------------------------------------------------------------ | :--: | ------------------- |
| Use Case와 관련된 모든 컨셉들의 행동을 관리하고, 적절한 컨셉에게 위임한다. |  D   | Controller   |
| Log in을 할 수 있는 페이지  , ID와 비밀번호를 입력할 수 있다.   | K     | LogInPage   |
| Log in 요청 정보, 관리자가 입력한 ID와 비밀번호를 가지고 있다.  | K    | LogInRequest |
| 유효한 Log in 계정 정보가 저장되어있는 곳               | K    | AccountStorage  |
| 입력된 ID와 비밀번호가 올바른지 검사한다.               | D    | Verifier     |
| Log in을 한 후에 관리자에게 보여지는 페이지             | K    | PizzaPage    |
| Log in정보가 잘못됨을 알리는 경고문                     | K   | Warning      |
| Pizza 페이지를 만든다.                                  | D    | PageMaker    |
| Pizza정보를 불러오는 쿼리문 생성 및 Pizza정보 제공       | D    | DatabaseConnection |

### Extracting the Associations

| Concept Pair                    | Association Description                                      | Association Name |
| ------------------------------- | ------------------------------------------------------------ | ---------------- |
| LogInPage ↔ Controller          | Controller는 Log in 페이지를 관리자에게 보여준다.             | posts |
| LogInRequest ↔ Controller       | Controller는 Log in을 요청받는다.                             | receives|
| Controller ↔ Verifier           | Controller는 Verifier에게 로그인 요청을 전달한다.      | conveys requests  |
| Verifier ↔ LogInRequest         | Verifier는 Log in 정보가 올바른지 검사한다.             | verifies    |
| Verifier ↔ AccountStorage       | Verifier는 AccountStorage에서 유효한 계정정보를 가져온다.      | retrieves valid accounts |
| Controller ↔ PageMaker          | Controller는 PizzaPage를 만들 것을 요청한다. 그리고 만들어진 page를 받는다. | conveys request |
| Controller ↔ DatabaseConnection | Controller는 Database에서 Pizza정보를 요청한다.                 | conveys request |
| PageMaker ↔ PizzaPage           | PizzaMaker는 PizzaMaker를 만든다.    | prepares    |
| DataConnection ↔ PageMaker      | DataConnection은 PageMaker에 Pizza 정보를 제공한다.   | provides data   |
| Controller ↔  PizzaPage         | Controller는 PizzaPage를 관리자에게 보여준다.      | posts |

   
### Diagram  
![image](https://user-images.githubusercontent.com/37579661/115995398-fcc19080-a615-11eb-8d3d-9d823633a037.png)
  
