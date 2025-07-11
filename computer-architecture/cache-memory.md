> **📅 업로드 날짜**  
> 2025-07-07  
> 
> **🗂 분류**  
> Computer Architecture  
>
> **🔗 노션 링크**  
> [노션에서 보기](https://www.notion.so/205a654e658a81398057e2b246e14adc?source=copy_link)
>

# **캐시 메모리(Cache Memory)**

**캐시 메모리는 CPU와 주기억장치(RAM) 사이에서 데이터 접근 속도를 빠르게 해주는 고속의 임시 저장소**

---

💡  
**[왜 필요할까?]**

CPU는 빠르게 동작하는 반면, RAM은 상대적으로 느리다.  
매번 RAM에서 데이터를 읽으면 속도 차이로 인해 CPU가 놀게 되어 병목 현상이 발생함 

그래서 자주 사용하는 데이터를 CPU 근처의 더 빠른 메모리인 캐시에 저장해두고,  
먼저 여기서 데이터를 찾도록 하기 위해서 필요!

 캐시에는 **원본이 아니라 RAM의 데이터를 복사해서 보관**함

---

💡  
**[많이 쓰지 못하는 이유]**

- 비싸고
- 공간을 많이 차지하고
- 관리가 어렵기 때문에  
→ 무작정 많이 쓸 수 없음

- 캐시는 일반적으로 → `SRAM`  
- RAM은 일반적으로 → `DRAM`

---

💡  
**[캐시 메모리의 계층 구조]**

캐시 메모리는 다음과 같은 딜레마가 있음:  
**빠른 속도 ↔ 작은 용량 ↔ 높은 비용**

이 문제를 해결하기 위해 계층 구조(L1, L2, L3)가 도입됨.

- **L1**: 작고 빠르며, CPU 코어 내부에 존재
- **L2**: 중간 속도, 보통 코어마다 하나씩 존재
- **L3**: 크고 느리며, 모든 코어가 공유

- 데이터 탐색 순서: **L1 → L2 → L3 → RAM**

---

💡  
**[작동 원리]**

- 캐시는 CPU가 앞으로 사용할 데이터를 **예측해서 미리 저장**함
- **작은 용량의 캐시 안에 유용한 데이터가 얼마나 들어 있느냐**가 성능을 좌우함

 **시간적 지역성**
- 최근 접근한 데이터는 다시 접근될 확률이 높다
- 예: 같은 주소를 반복적으로 읽고 쓸 때

 **공간적 지역성**
- 인접한 데이터도 곧 접근될 가능성이 높다
- 캐시는 데이터를 1바이트씩이 아니라, **Block(라인)** 단위로 미리 가져와 저장함

---

💡  
**[Cache Hit]**

- CPU가 요청한 데이터가 **캐시에 이미 있어서** 빠르게 가져올 수 있는 경우  
→  성능 향상!

---

💡  
**[Cache Miss]**

- CPU가 요청한 데이터가 **캐시에 없어서**,  
→ 다음 계층(L2, L3, RAM)을 탐색해야 하는 경우

미스의 종류:

-  **Cold Miss (강제 미스)**: 캐시가 비어 있을 때 발생. 프로그램 처음 실행 시 자주 발생
-  **Capacity Miss (용량 미스)**: 캐시 크기가 작아서 데이터를 담지 못할 때 발생
-  **Conflict Miss (충돌 미스)**: 서로 다른 데이터가 **같은 슬롯**을 사용하려고 할 때 발생  
  (특히 **Direct Mapping** 방식에서 잘 발생)

---

💡  
**[용어 정리]**

- **CPU** → 계산하고 명령 실행
- **RAM** → 데이터 저장 및 제공
- **캐시** → CPU와 RAM 사이에 있는 빠른 임시 저장소

---
