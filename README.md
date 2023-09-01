# 키친포스

## 퀵 스타트

```sh
cd docker
sudo docker compose -p kitchenpos up -d
```

## 요구 사항
- 손님들에게 주문을 받아 메뉴를 판매할 수 있는 애플리케이션을 개발하는 것이 목표입니다.
- 상품
    - [ ] 상품을 등록 할 수 있어야 한다.
        - [ ] 상품의 가격은 필수 항목이며, 음수 값을 가질 수 없다.
        - [ ] 상품의 이름은 필수 항목이며, 비속어를 사용하지 않아야 한다.
    - [ ] 상품의 가격을 변경할 수 있다.
        - [ ] 상품의 가격은 필수 항목이며, 음수 값을 가질 수 없다.
        - [ ] 상품의 가격과 수량을 곱한 가격이 메뉴 가격보다 크면 전시 된 메뉴를 숨겨야 한다.
    - [ ] 등록된 상품을 조회할 수 있어야 한다.
- 메뉴 그룹
    - [ ] 전시되거나 숨겨야 할 메뉴의 그룹 단위를 '메뉴 그룹' 이라고 한다.
    - [ ] 메뉴 그룹을 등록할 수 있어야 한다.
        - [ ] 메뉴 그룹의 이름은 필수 항목이다.
    - [ ] 등록된 메뉴 그룹을 조회할 수 있어야 한다.
- 메뉴
    - [ ] 메뉴 등록을 통해 손님에게 상품을 판매 할 수 있다.
    - [ ] 메뉴를 등록할 수 있어야 한다.
        - [ ] 메뉴 가격은 필수 항목이며, 음수의 값을 가질 수 없다.
        - [ ] 메뉴 그룹은 필수 항목이다.
        - [ ] 상품을 1개 이상 포함해야 한다.
        - [ ] 상품의 수량은 음수 값을 가질 수 없다.
        - [ ] 메뉴 가격은 상품의 가격과 수량을 곱한 가격과 같거나 높아야 한다.
        - [ ] 메뉴 이름은 필수 항목이며, 비속어를 사용하지 않아야 한다.
        - [ ] 메뉴를 전시하거나 숨길 수 있어야 한다.
    - [ ] 메뉴의 가격을 변경할 수 있어야 한다.
        - 메뉴 가격은 필수 항목이며, 음수의 값을 가질 수 없다.
        - 메뉴 가격은 상품의 가격과 수량을 곱한 가격과 같거나 높아야 한다.
    - [ ] 메뉴를 전시할 수 있어야 한다.
        - 메뉴 가격이 상품의 가격과 수량을 곱한 가격과 같거나 높지 않은지 체크해야 한다.
    - [ ] 메뉴를 숨길 수 있어야 한다.
    - [ ] 등록된 메뉴를 조회할 수 있어야 한다.
- 주문
    - [ ] 주문의 진행 상태는 대기(WAITING), 접수(ACCEPTED), 서빙(SERVED), 배달시작(DELIVERING), 배달완료(DELIVERED), 완료(COMPLETED) 중 1개의 상태를
      가진다.
    - [ ] 메뉴를 주문할 수 있어야 한다.
        - [ ] 주문 유형은 필수 항목이며, 배달(DELIVERY), 포장(TAKEOUT), 매장(EAT_IN) 중에서 선택해야 한다.
        - [ ] 메뉴를 1개 이상 포함해야 한다.
        - [ ] 매장(EAT_IN) 주문을 제외 한 주문 유형의 경우, 주문 항목의 수량이 음수 값을 가질 수 없다.
        - [ ] 전시 된 메뉴만 주문이 가능한다.
        - [ ] 주문한 가격은 메뉴의 가격과 수량을 곱한 가격과 같아야 한다.
        - [ ] 배달(DELIVERY) 주문의 배달 주소는 필수 항목이다.
        - [ ] 매장(EAT_IN) 주문은 테이블에 앉아 있어야 한다.
        - [ ] 주문을 등록하고 대기(WAITING)해야 한다.
    - [ ] 주문을 접수(ACCEPTED)해야 한다.
        - [ ] 대기(WAITING) 중인 주문만 접수(ACCEPTED) 가능하다.
        - [ ] 배달(DELIVERY) 주문은 배달 대행사를 호출 해야 한다.
    - [ ] 주문을 서빙(SERVED)해야 한다.
        - [ ] 접수(ACCEPTED)된 주문만 서빙(SERVED) 가능하다.
    - [ ] 주문을 배달 시작(DELIVERING)해야 한다.
        - [ ] 서빙(SERVED)된 배달(DELIVERY) 주문만 가능하다.
    - [ ] 주문을 배달 완료(DELIVERED) 해야 한다.
        - [ ] 배달 시작(DELIVERING)된 주문만 가능하다.
    - [ ] 주문 완료(COMPLETED) 해야 한다.
        - [ ] 배달 완료(DELIVERED)된 배달(DELIVERY) 주문이거나,서빙(SERVED)된 포장(TAKEOUT) 또는 매장(EAT_IN) 주문이어야 한다.
        - [ ] 주문 완료(COMPLETED)된 매장(EAT_IN) 주문은 테이블을 비워야 한다.
        - [ ] 주문 완료(COMPLETED)되지 않은 매장(EAT_IN) 주문이 있다면 테이블을 비울 수 없어야 한다.
    - [ ] 등록된 주문을 조회할 수 있어야 한다.
- 테이블
    - [ ] 테이블을 등록해야 한다.
        - [ ] 테이블 이름은 필수 항목이다.
    - [ ] 테이블에 앉을 수 있어야 한다.
    - [ ] 테이블을 비울 수 있어야 한다.
        - [ ] 완료(COMPLETED)되지 않은 주문이 있다면 테이블을 비울 수 없다.
    - [ ] 손님의 수를 변경 할 수 있어야 한다.
        - [ ] 손님의 수는 음수 값을 가질 수 없다.
        - [ ] 빈 테이블이 아니어야 한다.
    - [ ] 등록된 테이블을 조회할 수 있어야 한다.

## 용어 사전

| 한글명 | 영문명 | 설명 |
| --- | --- | --- |
|  |  |  |

## 모델링
