# Arduino UNO + 조도센서 AO

빛의 변화를 아날로그 입력으로 읽고 시리얼 모니터에 출력하는 입문 예제입니다.

## 부품

- Arduino UNO R3, USB 케이블
- 5V 지원 모듈형 LDR 센서(VCC, GND, AO, DO 표시), 점퍼선 3개
- 두 다리만 있는 LDR 원소자는 이 배선을 사용할 수 없습니다.

## 연결

USB 전원을 뺀 상태에서 연결하세요. 모듈마다 핀 순서가 다르므로 실크 인쇄를 확인하세요.

| Arduino UNO | 센서 | 용도 |
|---|---|---|
| 5V | VCC | 전원 |
| GND | GND | 공통 기준 |
| A0 | AO | 아날로그 입력 |
| 미연결 | DO | 이번 예제에서 사용하지 않음 |

![배선도](arduino_uno_cds_ao.png)

## 실행

1. Arduino IDE에서 보드 Arduino UNO와 연결된 포트를 선택합니다.
2. `sketch.ino`를 열어 업로드합니다. 추가 라이브러리는 필요하지 않습니다.
3. 시리얼 모니터를 9600 baud로 엽니다.
4. 센서를 가렸다가 빛을 비추며 `CDS AO:` 뒤의 숫자를 비교합니다.

`setup()`은 시리얼 통신을 준비합니다. `loop()`는 A0의 값을 읽고 출력한 뒤 500ms 기다리는 과정을 반복합니다. UNO의 기본 ADC 결과는 0~1023이며 lux 값이 아닙니다. 실제 모듈은 밝을수록 값이 커지거나 작아질 수 있으니 두 환경에서 측정해 확인하세요.

## 파일

- `sketch.ino`: 업로드용 전체 코드
- `diagram.json`: Wokwi 편집용 회로
- `circuit_preview.html`: 핀 좌표 기반 회로 미리보기(Wokwi elements CDN 필요)
- `arduino_uno_cds_ao.png`: 회로 이미지
- `cards/`: 카드뉴스 PNG 7장
- `caption.md`: 게시용 캡션 초안

## 확인 범위

핀 연결, 연결표와 코드의 A0 대응, 카드 PNG 렌더링을 검수한 교육용 예제입니다. 실제 하드웨어 업로드·측정은 아직 수행하지 않았습니다. ESP32/Pico에는 전압과 핀 연결을 그대로 적용하지 마세요.

## 근거

- [Arduino analogRead](https://docs.arduino.cc/language-reference/en/functions/analog-io/analogRead/)
- [Wokwi 조도센서 모듈](https://docs.wokwi.com/parts/wokwi-photoresistor-sensor)

CODEPLANT · 배움이 자라나는 코딩·메이킹 교육
