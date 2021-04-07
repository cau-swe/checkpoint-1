 <h2 align="center"> :pizza: 피자 서비스  </h2>     
 </br>
<div align="center">

![CAU SWE](https://img.shields.io/badge/CAU--blue) ![Pizza](https://img.shields.io/badge/Pizza--red) ![Software-Engineering](https://img.shields.io/badge/SoftwareEngineering--yellow) 

   피자를 시킬 수 있는 최고의 서비스를 만들고자 하는 소프트웨어공학 2분반 팀프로젝트 README.md 에 오신걸 환영합니다! 
   
  <br>
  
 **Team Members**  
| **김경준** | **박정미** |  **유창선** | **임정택** | **정상민** |  **선민승** |
|:-----:|:-----:|:------:|:-----:|:-----:|:------:|
 |[kouz95](https://github.com/kouz95)|[Jummi10](https://github.com/Jummi10)|[yoochangseon](yoochangseon/https://github.com/yoochangseon)|[TedLeem](https://github.com/TedLeem)|[Topslug](https://github.com/Topslug)|[MinseungSeon](https://github.com/minseungseon) |
</div>  


</br>

 <h2 align="center">  :bulb: problem-statement  </h2>   


#### :mag_right: the problem
전화로 피자를 배달시켜 먹어야 할 때가 있습니다. 전화로 주문하는 것은 쉬워보이지만 의사소통에 오류가 있을 수 있습니다. 전화 주문을 하면 메뉴가 눈으로 보이는 것이 아니기 때문에 직원들은 잘 이해하지 못해 고객이 한 말을 되물을 수 있습니다. 이와 같은 상황이 계속되면 시간 낭비일뿐만 아니라 고객을 짜증나게 할 수 있습니다. 직원들 역시 이것 때문에 시간을 많이 낭비합니다. 

하지만 온라인으로 피자를 주문하면 더 편하게 주문할 수 있습니다. 유저는 단순히 원하는 피자를 고르고 앱이나 온라인으로 결제를 하면 배달 받을 수 있기 때문입니다. 만약 직접 매장에 가서 주문할 경우에는 최소 15분 이상 피자가 만들어지기 까지 기다려야합니다. 하지만 앱이나 온라인으로 주문을 하면 그럴 필요가 없습니다. 예상 픽업시간을 알려주기 때문에 그 때 피자를 가지러 가면 됩니다.

저희는 이처럼 전화주문보다 간단하고 편리한 피자 주문 시스템을 제공하려 합니다.


#### :email: Scenarios

관리자가 online pizza ordering system에 접속하면, username과 password를 입력하는 창이 뜨고 해당 정보를 입력하여 로그인을 합니다. 시스템에 접속하면 상단에 “Add Pizza”, “Edit Pizza”, “Update Order Status”, “View Feedback” 4개의 옵션이 있습니다. “Add Pizza”를 눌러 피자 사이즈와 사진, 이름, 설명, 가격을 입력하여 새로운 피자의 정보를 입력하여 추가합니다. “Edit Pizza”를 선택하면 기존 피자들에 대해 변경사항이 있을 경우 정보를 수정할 수도, 삭제할 수도 있습니다. 또한 “Update Order Status”에서는 주문 정보 리스트를 확인하고, 다 만들어지고 배달이 시작된 주문건은 배달 중, 배달이 완료된 주문은 배달 완료로 상태를 업데이트합니다. "View Feedback"을 선택하면 유저들이 남긴 리뷰들을 볼 수 있습니다.

주문자도 시스템에 처음 접속하여 username과 password를 입력하여 로그인합니다. 상단에는 “Menu”, “View Cart”, “Track Order”, “Feedback” 4가지 옵션이 있습니다. “Menu”를 선택하여 메뉴 중에 원하는 피자를 선택하고 수량과 요청사항을 입력하고 장바구니 혹은 지금 구매를 누릅니다. 주문이 완료되면 “Track Order”에서 주문 상태와 예상시간을 확인할 수 있으며, "Feedback"에 들어가 리뷰를 남길 수 있습니다.

직원이 관리자에게 권한을 얻은 후, online pizza ordering system에 접속하면, username과 password를 입력하는 창이 뜨고 정보를 입력하여 로그인을 합니다. 주문 관리 페이지에 접속하여 주문 정보 리스트를 확인할 수 있습니다. 주문 정보 리스트를 통해 주문자의 주소, 핸드폰 번호와 주문 메뉴, 추가 요청 사항을 확인합니다. 또한 주문이 최초로 만들어졌을 때에는 대기 중 상태이고, 이를 확인하여 준비 중 상태로 바꿀 수 있습니다. 이후 배달이 시작된 주문건은 배달 중, 배달이 완료된 주문은 배달 완료로 상태를 업데이트하여 고객들로 하여금 본인의 주문 상태를 알 수 있도록 합니다.


</br>

 <h2 align="center">  :adhesive_bandage: requirements  </h2>   
 
  ##### 1. [customer](Customer.md)
  ##### 2. [employee](Employee.md)
  ##### 3. [administrator](Administrator.md)


