### Deriving Use Cases from System Requirements
|  Actor   |       Actor's Goal       |         Use Case Name         |
|:--------:|:------------------------:|:-----------------------------:|
| Administrator    |		시스템 로그인     |	Log in
| Administrator    |		메뉴 선택	        |	Select Menu
| Administrator    |		피자정보 추가     |	Add Pizza
| Administrator	   |	피자정보 수정       |	Edit Pizza
| Administrator    |		피자정보 삭제     |	Delete Pizza
| Administrator    |		주문 기록 확인    |	View Order Records
| Administrator    |		관리자권한인증	   |  Authenticate Admin
| Administrator    |		리뷰확인          |		View Review
| Administrator    |		직원에게 권한부여 |	?
| Administrator    |		직원정보 추가	    |Add Employee
| Administrator    |		직원정보 수정	    |Edit Employee
| Administrator    |		직원정보 삭제	    |Delete Employee
| 피자정보저장소    |  피자의 정보 저장 및 정보 제공 | Add Pizza, Edit Pizza, Delete Pizza
| 주문기록저장소	   |	주문기록 저장 및 정보 제공    | View Order Records
| 직원정보 저장소	 |	직원정보 저장 및 정보 제공    | Add Employee, Edit Employee, Delete Employee
| 리뷰저장소	       |	리뷰 저장 및 정보 제공        | View Review

#### Generalizations
- Add Pizza, Edit Pizza, Delete Pizza → Manage Pizza
- Add Employee, Edit Employee, Delete Employee → Manage Employee
- 피자정보저장소, 주문기록저장소, 직원정보저장소, 리뷰저장소 → Server
- Log in, Authenticate Admin → Authentiate Admin

|  Actor   |       Actor's Goal       |         Use Case Name         |
|:--------:|:------------------------:|:-----------------------------:|
| Administrator    |	  시스템 관리 페이지 접속       |	Authentiate Admin(UC-1)
| Administrator    |		메뉴 선택	                    |	Select Menu(UC-2)
| Administrator    |		피자정보 추가, 수정, 삭제     |	Manage Pizza(UC-3)
| Administrator    |		주문 기록 확인               |	View Order Records(UC-4)
| Administrator    |		리뷰확인                     |		View Review(UC-5)
| Administrator    |		직원에게 권한부여             |	?
| Administrator    |		직원정보 추가, 수정, 삭제	    | Manage Employee(UC-6)
| Server    |  피자의 정보, 주문기록, 직원정보, 리뷰 저장 및 정보 제공 | Manage Pizza(UC-1), View Order Records(UC-4), Manage Employee(UC-6), View Review(UC-5)
