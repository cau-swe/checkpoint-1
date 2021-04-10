### Deriving Use Cases from System Requirements
|  Actor   |       Actor's Goal       |         Use Case Name         |
|:--------:|:------------------------:|:-----------------------------:|
| Administrator    |		시스템 로그인 |	Log in(UC-1)
| Administrator    |		피자정보 추가     |	Add Pizza(UC-2)
| Administrator	   |	  피자정보 수정     |	Edit Pizza(UC-3)
| Administrator    |		피자정보 삭제     |	Delete Pizza(UC-4)
| Administrator    |		주문 기록 확인    |	View Order Records(UC-5)
| Administrator    |		관리자 권한 인증	 | Authenticate Admin(UC-6)
| Administrator    |		리뷰확인          |	View Review(UC-7)
| Administrator    |		직원정보 추가	    | Add Employee(UC-8)
| Administrator    |		직원정보 수정	    | Edit Employee(UC-9)
| Administrator    |		직원정보 삭제	    | Delete Employee(UC-10)
| Administrator    |		직원에게 관리자권한부여 |	Assign Admin Authority(UC-11)
| Administrator    |    직원에게 직원권한부여   | Assign Employee Authority(UC-12)
| 피자정보저장소    |  피자정보 저장 및 정보 제공 | Add Pizza(UC-2), Edit Pizza(UC-3), Delete Pizza(UC-4)
| 주문기록저장소	   |	주문기록 저장 및 정보 제공    | View Order Records(UC-5)
| 회원정보저장소	   |	관리자 및 직원정보 저장 및 정보 제공    | Add Employee(UC-8), Edit Employee(UC-9), Delete Employee(UC-10), Authenticate Admin(UC-6), Assign Admin Authority(UC-11), Assign Employee Authority(UC-12)
| 리뷰저장소	       |	리뷰 저장 및 정보 제공        | View Review(UC-7)

UC-1 include UC-6

#### Generalizations
- Add Pizza, Edit Pizza, Delete Pizza → Manage Pizza(UC-13)
- Add Employee, Edit Employee, Delete Employee → Manage Employee(UC-14)
- 피자정보저장소, 주문기록저장소, 회원정보저장소, 리뷰저장소 → Database

|  Actor   |       Actor's Goal       |         Use Case Name         |
|:--------:|:------------------------:|:-----------------------------:|
| Administrator    |		시스템 로그인                 |	Log in
| Administrator    |	  관리자 권한 인증              |	Authentiate Admin
| Administrator    |		피자정보 추가, 수정, 삭제     |	Manage Pizza, Add Pizza, Edit Pizza, Delete Pizza
| Administrator    |		주문 기록 확인                |	View Order Records
| Administrator    |		리뷰확인                      |	View Review
| Administrator    |		직원에게 권한부여             |	Assign Admin Authority
| Administrator    |    직원에게 직원권한부여         | Assign Employee Authority
| Administrator    |		직원정보 추가, 수정, 삭제	    | Manage Employee, Add Employee, Edit Employee, Delete Employee
| Database         |  피자정보, 주문기록, 회원정보, 리뷰저장 및 정보 제공 | Manage Pizza, Add Pizza, Edit Pizza, Delete Pizza, View Order Records, Manage Employee, Add Employee, Edit Employee, Delete Employee, View Review, Authenticate Admin, Assign Admin Authority, Assign Employee Authority
