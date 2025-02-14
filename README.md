# study-file
https://emaus301.com/entry/%EB%AF%B8%EC%88%A0%EA%B0%80-%EB%B9%9B-%EA%B8%B0%EB%B3%B8%EC%9B%90%EB%A6%AC-%EB%B0%A9%ED%96%A5

유니티 VFX(Visual Effects)의 기본기는 다음과 같은 요소들로 구성됩니다:

1. **파티클 시스템(Particle System)**:
   - 파티클 시스템은 유니티에서 가장 중요한 VFX 도구 중 하나로, 다양한 시각적 효과를 만들 때 사용됩니다. 예를 들어 불꽃, 연기, 폭발, 비, 눈 등을 표현할 수 있습니다.
   - 파티클의 속도, 크기, 색상, 생명 주기 등 여러 속성을 조절하여 복잡한 효과를 만들 수 있습니다.

2. **VFX 그래프(VFX Graph)**:
   - VFX 그래프는 유니티에서 제공하는 노드 기반의 시각적 프로그래밍 툴로, 더욱 복잡하고 세밀한 VFX를 제작할 수 있습니다.
   - GPU를 활용하여 매우 높은 성능의 시각적 효과를 구현할 수 있으며, 복잡한 이펙트와 애니메이션을 쉽게 다룰 수 있습니다.

3. **머티리얼(Material)과 셰이더(Shader)**:
   - VFX에서 효과의 시각적 품질을 높이기 위해서는 적절한 머티리얼과 셰이더를 사용하는 것이 중요합니다. 셰이더를 통해 텍스처, 반사, 빛의 반응 등을 조절하여 보다 사실감 있는 이펙트를 만들 수 있습니다.
   - VFX 그래프에서 셰이더를 결합하여 효과를 더욱 정교하게 구현할 수 있습니다.

4. **타임라인(Timeline)과 애니메이션(Animation)**:
   - VFX를 애니메이션화하여 시간에 따라 효과가 어떻게 변화하는지 제어할 수 있습니다.
   - 유니티 타임라인을 사용하면 VFX의 시간 흐름을 세밀하게 제어할 수 있으며, 여러 이펙트를 동기화시킬 수 있습니다.

5. **리소스 최적화(Optimization)**:
   - 성능을 고려한 VFX 제작이 중요합니다. 너무 많은 파티클이나 복잡한 셰이더를 사용하면 성능에 영향을 줄 수 있으므로, 최적화를 고려하여 효과를 제작해야 합니다.
   - 파티클 수, 해상도, 셰이더 효율성 등을 고려한 최적화가 필요합니다.

6. **스컬핑 및 렌더링(Scalping & Rendering)**:
   - VFX를 만들 때는 실제 환경에서 어떻게 렌더링될지를 고려해야 하며, 씬의 조명이나 카메라와의 상호작용도 중요합니다.
   - 유니티에서 VFX는 보통 카메라의 시점과 연관되어 렌더링되므로, VFX가 씬에 적합하게 보이도록 조정하는 것이 중요합니다.

이 기본적인 개념들을 이해하고 활용하는 것이 유니티 VFX 제작의 핵심입니다.

게임 제작 과정에서 2D 모션을 적용시키는 방법은 주로 **애니메이션 시스템**을 사용하여 구현됩니다. 유니티에서는 2D 모션을 적용시키기 위한 다양한 방법이 있는데, 주로 **애니메이션 클립**과 **애니메이터(Animator)**를 활용합니다. 다음은 2D 모션을 적용하는 과정에 대해 설명합니다:

### 1. **스프라이트 애니메이션 만들기**
   - **스프라이트 시트(Sprite Sheet)** 또는 **개별 스프라이트**를 사용하여 2D 캐릭터의 애니메이션을 만듭니다. 스프라이트 시트는 여러 개의 이미지를 한 번에 모아둔 텍스처입니다.
   
   - **스프라이트 시트를 분할하기**:
     1. 유니티에서 스프라이트 시트를 **스프라이트(Sprites)**로 나누기 위해, 해당 이미지를 유니티의 `Sprite Editor`에서 분할합니다.
     2. 이때 각 프레임을 개별적으로 분리하여 **스프라이트 애니메이션**을 만들 수 있습니다.

   - **애니메이션 클립 생성**:
     1. **애니메이션 클립**은 애니메이션의 세부 사항을 정의하는데 사용됩니다. 애니메이션 창에서 **스프라이트 시퀀스**(각각의 스프라이트 이미지)를 순차적으로 배치해 애니메이션을 생성합니다.
     2. 애니메이션의 **프레임 간 시간 간격**(Frame Rate)을 설정하여 애니메이션의 속도를 조절할 수 있습니다.

### 2. **애니메이터(Animator) 설정**
   - **Animator**는 유니티에서 애니메이션을 제어하는 컴포넌트입니다. 이를 통해 여러 애니메이션을 전환하거나 상태를 관리할 수 있습니다.
   
   - **애니메이터 컨트롤러(Animator Controller)** 생성:
     1. 유니티에서 `Animator Controller`를 만들고, 이 컨트롤러를 캐릭터의 `Animator` 컴포넌트에 연결합니다.
     2. 애니메이션을 전환하는 조건을 설정하는 **애니메이션 상태(State)**와 **전환(Transition)**을 정의할 수 있습니다. 예를 들어, 걷기, 달리기, 점프 등 각 상태에 대한 애니메이션을 만들고 이를 전환하는 규칙을 설정합니다.

   - **애니메이션 파라미터 설정**:
     1. `Animator Controller`에서는 파라미터를 설정하여 애니메이션의 상태 전환을 제어합니다. 파라미터는 **Trigger**, **Bool**, **Int**, **Float** 타입을 사용할 수 있습니다.
     2. 예를 들어, 캐릭터가 **걷는 애니메이션**에서 **달리기 애니메이션**으로 전환하려면, `Speed`와 같은 **Float 파라미터**를 사용하여 속도에 따른 상태 전환을 설정할 수 있습니다.

### 3. **스크립트로 모션 제어하기**
   - 게임 내에서 애니메이션을 제어하려면, C# 스크립트를 통해 애니메이션 상태를 변경하거나 파라미터를 조정할 수 있습니다.
   - 예를 들어, 플레이어가 이동하는 동안 걷기 애니메이션을, 점프할 때 점프 애니메이션을 실행할 수 있습니다.

   ```csharp
   Animator animator;

   void Start() {
       animator = GetComponent<Animator>();  // Animator 컴포넌트 참조
   }

   void Update() {
       float move = Input.GetAxis("Horizontal");  // 키보드 입력 감지
       animator.SetFloat("Speed", Mathf.Abs(move));  // Speed 파라미터로 애니메이션 전환
   }
   ```

   이 코드에서는 플레이어가 이동할 때 `Speed` 파라미터를 설정하여 걷기 애니메이션과 다른 애니메이션 간에 전환을 제어합니다.

### 4. **루프 애니메이션과 상태 전환**
   - 2D 캐릭터가 **걷기**, **달리기**, **점프** 등을 할 때, 각 상태에 맞는 애니메이션을 설정합니다. 예를 들어:
     - **걷기 애니메이션**: 캐릭터가 이동할 때 루프(반복) 애니메이션으로 설정합니다.
     - **점프 애니메이션**: 한 번만 실행되는 애니메이션입니다.
   
   - **애니메이션 상태 전환**:
     - 상태 전환을 **조건**에 맞춰 설정할 수 있습니다. 예를 들어, 캐릭터가 이동 중일 때는 **걷기/달리기** 애니메이션이 실행되고, **점프** 상태일 때는 점프 애니메이션이 실행되도록 설정합니다.

### 5. **이펙트 및 기타 모션 추가**
   - **이펙트 추가**: 2D 캐릭터 모션에 효과를 추가하려면, 예를 들어 **진동**, **파티클 시스템**, **빛 효과** 등을 사용할 수 있습니다.
   - **물리적인 모션**: 2D 물리 엔진인 **Box2D**나 **Rigidbody2D**를 사용하여 캐릭터에 물리적인 반응을 추가할 수 있습니다. 예를 들어, 중력, 충돌, 이동 등을 물리적으로 자연스럽게 처리할 수 있습니다.

### 6. **디버깅 및 최적화**
   - 애니메이션이 자연스럽게 보이도록 조정하면서 디버깅을 진행합니다. 애니메이션이 끊어지지 않도록 상태 전환을 부드럽게 만들고, 게임 성능에 영향을 미치지 않도록 최적화합니다.
   - **애니메이션 큐(Queue)**나 **이벤트(Event)**를 사용하여 특정 애니메이션 후에 다른 작업을 자동으로 실행하도록 설정할 수 있습니다.

---
초안 

스탯
스탯의 다양성을 높여 스탯간의 상호작용을 통해 인게임내에서 이를 활용할수있으면 어떨까라는 생각으로 각 스탯의 종류를 나누었고 상위 스탯의 개념을 두어서 이를 보다 활용하기 편하게 정리 해볼 것이다 일정 스탯은 스탯치의 증가나 감소에 따라 또다른 스탯치를 가져오거나 스탯치 자체가 상위 개념으로 변화하는 등의 경우를 생각해보았으며 별로면 의견을 남겨주길 바란다 현재 작성중인 내용은 어디까지나 초안이자 의견제시이다

1차 공격력 / 방어력 / 생명력 / 정신력

공격력 - 전투시 자신이 상대에게 가하는 데미지 다른 스탯들 혹은 장비 상황에 영향을 받음

방어력 - 전투시 상대가 자신에게 가하는 데미지를 차감하는 스탯 다른 스탯들 혹은 장비,상황에 영향을 받음

생명력 - 전투시 상대가 자신에게 데미지를 줄 때 차감되는 포인트 0에 수렴할시 게임이 종료되며 다양한 수단으로 이를 회복할수 있다 다른 스탯들 혹은 장비,상황에 영향을 받는다

정신력 - 상황 혹은 다른 스탯들에 영향을 줄수 있으며 역으로 영향을 받을수 있다
 	
1.	정신력 변동 사항에 따라 공격력 방어력 생명력에 영향을 줄수 있다
EX) 	정신력이 5 차감되어 방어력이 줄어드는 식으로
	
2.	정신력이 일정량 차감될시 정신과 관련된 스탯을 얻게된다 
EX) 	정신력이 10 차감되어 공격성 스탯을 흭득하는 식으로 
	
3.	정신력이 일정량 추가될시 정신과 관련된 스탯을 얻게된다 
EX) 	정신력이 15 추가되어 냉정 스탯을 흭득하는 식으로 

1차 스탯
신체스탯 힘 / 민첩 / 지능 / 건강 /

힘 
캐릭터의 근력수치를 표기한 수치로 수치에 따라 인게임내에서 특정 선택지를 고를 수 있는 스탯 전투시에 공격력 수치에 직접적 영향을 주는 스탯 캐릭터의 상황이나 상태에 따라 변동점이 있을 것이다 (게임을 진행하며 캐릭터가 부상을 당했을 경우 그 경도에 따라 근력치가 하락하는 식이나 전투시에 도핑을 하여 힘스탯이 단기적으로 증가한다는 식으로 )

민첩
캐릭터의 민첩도를 표기한 수치로 수치에 따라 인게임내에서 특정 선택지를 고를수 있는 스탯 전투시에 기습,도주,회피,반격와 같은 선택지의 확률을 다루는 스탯이자 민첩 스탯의 수치에 따라 캐릭터의 공격턴의 횟수가 달라지거나 추가타의 여부를 줄 수 있는 스탯

지능
캐릭터의 지능 수치를 표기한 수치로 수치에 따라 인게임내에서 특정 선택지를 고를 수 있는 스탯이자 게임 내에서 상점에서 교섭이나 흥정따위에 영향을 주는 스탯 지능 스탯 수치에 따라서 아이템의 정보나 적의 정보등을 추가적으로 얻을수 있다 전투시에 회피,반격와 같은 선택지의 확률을 올려주며 스킬의 습득하는데에 있어서 상위 스킬로 갈수록 캐릭터의 지능치를 요구할것이다

건강
캐릭터의 건강수치를 나타내는 수치로 인게임내에서 수치에 따라 특정선택지를 발생시킬수있으며 전투시에는 건강수치가 독,마비 등의 디버프에 대한 면역 수치 그리고 체력의 직접적 영향을 주는 스탯이 될것이다

2차 스탯
성향스탯 
나태 / 집착 / 공격성 / 부정적 / 분노 / 교만 / 신중 / 무질서 / 냉정 / 혼돈 / 공포 / 의지 / 끈질김 / 

공격성 - 스탯지수에 따라 일정확률로 전투시 공격을 제외한 다른 행동은 할수 없게되고 그에 반해 증가된 공격성으로 인해 스탯지수에 따라 추가 공격력이 붙는다 

부정적 - 스탯지수에 따라 

나태

집착 

분노

교만

신중

무질서

냉정

3차 스탯
기술
무기술 / 습격 / 도약 / 은신 / 

이 과정을 통해 2D 모션을 효과적으로 게임에 적용할 수 있습니다. 유니티에서는 애니메이션과 관련된 많은 도구와 시스템을 제공하므로, 다양한 애니메이션을 사용하여 더 자연스럽고 다채로운 게임 캐릭터 동작을 구현할 수 있습니다.

https://kr.pinterest.com/pin/282108364141966674/
