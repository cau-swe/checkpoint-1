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
| Controller ↔ DatabaseConnection | Controller는 DatabaseConnection에게 입력된 피자정보를 저장하도록 요청한다.       | conveys request  |
| Controller ↔ InputPage          | Controller는 InputPage를 사용자에게 전달한다.                  | posts           |
| Controller ↔ UpdatedPage        | Controller는 UpdatedPage를 사용자에게 전달한다.                | posts           |
| Controller ↔ Warning            | Controller는 Warning을 사용자에게 전달한다.  | posts |


### Extracting the Attributes

| Concept       | Attributes        | Attribute Description                   |
| ------------- | ----------------- | --------------------------------------- |
| StoreRequest  | input parameters  | 사이즈, 사진, 이름, 설명, 가격           |
| PageMaker     | input parameters  | UpdatedPage를 만들때 필요하다.           |
