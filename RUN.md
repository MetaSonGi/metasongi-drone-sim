# Unity 실행

1. Python 3.10+에서 `python setup_unity.py` 실행.
2. Unity Hub > Add project from disk > 생성된 `UnityProject` 폴더를 Unity 6.3 편집기 (프로젝트 기준 6000.3.0f1, 설치된 호환 패치 선택 가능)로 엽니다. Built-in 렌더러용 코드입니다.
3. Edit > Project Settings > Player > Active Input Handling을 **Both** 또는 **Input Manager (Old)** 로 설정합니다.
4. 상단 **MetaSonGi > Create Demo Scene** 실행 후 Play. 씬 생성은 기존 열린 씬을 교체하므로 작업 중인 씬은 먼저 저장하세요.
5. 실행 파일은 File > Build Profiles에서 플랫폼을 선택해 Build. 생성 메뉴가 Demo 씬을 빌드 목록에 등록합니다.

자동 장면 생성 코드와 런타임 코드를 포함합니다. 외부 3D 에셋 없이 기본 도형으로 동작합니다. Unity 편집기·실제 헤드셋은 이 개발 환경에 없어 컴파일·기기 검증은 아직 하지 못했습니다.

## 선택: 헤드셋 VR
Unity Package Manager에서 해당 Unity 버전과 호환되는 XR Plug-in Management 및 OpenXR를 설치하고, 대상 플랫폼의 OpenXR를 켠 뒤 Project Validation 항목을 해결하세요. 기본 데스크톱 실행에는 패키지가 필요 없습니다.
공간 전시·공장 프로젝트는 헤드 포즈와 오른손 트리거 레이, 왼손 스틱 이동 코드를 포함합니다. 헤드셋 입력 프로필은 대상 기기에 맞게 설정해야 합니다. OnGUI 패널은 데스크톱 UI이며 VR 안에 표시되지 않습니다. 공장은 월드 콘솔로 조작하고, 전시는 PC에서 작품을 먼저 배치합니다.

저장 파일은 Unity의 `Application.persistentDataPath`에 생성됩니다.

## 범위
12대 군집, Grid/Ring/V 대형, Grid 군집 분리, 간격·기종 속도 프리셋 저장/불러오기, FPV 카메라, WASD·Q/E 비행을 구현했습니다.
운동학 제어 연습용이며 모터·공력 시뮬레이션이나 강화학습 모델은 없습니다. 기체별 Trainer/Racer/Heavy 속도 프로필 혼합과 드론 수 변경, 훈련 보고서 JSON 저장을 지원합니다. 기체별 장기 훈련 이력과 충돌 기반 채점은 후속 범위입니다.
FPV에서도 방향키는 월드 좌표의 리더 이동이며 실제 레이싱 드론의 자세·스로틀 조작이 아닙니다.
