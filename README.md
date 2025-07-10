# 🛗 FreeRTOS 기반 STM32 엘리베이터 제어 시스템

## 📖 프로젝트 개요
STM32 MCU와 FreeRTOS를 활용하여 엘리베이터 시스템을 설계 및 구현했습니다. 다양한 입출력 장치(I2C LCD, FND, Dot Matrix, Step Motor 등)를 통합하고, 멀티태스킹, 뮤텍스, 인터럽트 처리를 적용한 RTOS 기반 임베디드 시스템입니다.

## 🚀 기술 스택
- **언어:** C (STM32CubeIDE)
- **플랫폼:** STM32 MCU, FreeRTOS
- **기술:** FSM, Task 분리, Mutex, I2C, SPI, PWM, GPIO, External Interrupt

## 🛠 주요 기능
| 기능 | 설명 |
|---|---|
| 🎯 FSM 기반 엘리베이터 제어 | 대기 → 이동 → 도착 → 문열림 상태 전이 |
| 🖥 I2C LCD & FND & Dot Matrix | 현재층/목표층/상태 시각화, 층수 표시, 운행 상태 애니메이션 |
| 🚪 스텝모터 문 제어 | 정밀한 속도/위치 제어로 도어 개폐 |
| 🔗 블루투스 & 버튼 입력 | 수동 조작 및 무선 제어 지원 |
| ⚙️ 우선순위 기반 Task 관리 | LCD, 모터, 디스플레이, 센서 Task 분리 & 효율화

## 🖥 시스템 구성도
![image](https://github.com/user-attachments/assets/d3e811ab-fae2-4b5c-9455-1e805976367f)

- 버튼/센서 ↔ STM32 ↔ FreeRTOS Task ↔ I2C LCD/FND/Dot Matrix ↔ Step Motor ↔ 사용자

## 📊 결과 및 성과
- FreeRTOS 기반 멀티태스킹 → 안정적 동작
- Mutex 적용 → LCD 자원 충돌 해결
- 우선순위 기반 Task → 실시간성 개선

## 📝 설치 및 실행 방법
- STM32CubeIDE로 빌드 → STM32 보드 다운로드
- FreeRTOS 설정 및 Task 우선순위 조정 가능

## 📁 프로젝트 구조
```
Elevator_FreeRTOS_STM32/
├── main.c
├── elevator_fsm.c
├── lcd_task.c
├── motor_task.c
├── display_task.c
└── button_interrupt.c
```

## ✉️ 개선 포인트
- Queue 기반 목표층 관리 → Circular Queue 도입 예정
- 중첩 반복문 개선 → 함수 분리 및 Switch-case 적용
- Task 간 통신 → Event Group 활용 가능성 검토

## 🔗 참고자료
[시연 영상] https://youtu.be/gPqQQHl4VWA

---
✅ 키워드: #STM32 #FreeRTOS #Elevator #FSM #멀티태스킹 #I2C #SPI #StepMotor #임베디드시스템
