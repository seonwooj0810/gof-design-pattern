# gof-design-pattern

디자인 패턴을 챕터 단위로 학습하며 구현한 저장소입니다. 패턴별 예제를 `ch01`, `ch02`...
형태로 정리합니다.

## 학습 목적

디자인 패턴을 책의 챕터 흐름에 따라 직접 구현하며 학습합니다.

## 사용 기술

- 순수 Java (별도 빌드 도구/외부 의존성 없음)
- IntelliJ IDEA 프로젝트 (`.iml`, `.idea/`)

> Gradle/Maven 등 빌드 파일이 없는 IntelliJ 프로젝트입니다. 표준 라이브러리만 사용하며,
> Observer 예제에서 Swing(`javax.swing`)을 활용합니다.

## 구현된 패턴 (코드 근거)

`src/` 하위 챕터 기준:

- **ch01 — Strategy (전략 패턴)** — `ch01/strategy/`
  - 오리 시뮬레이터 예제. `Duck`, `MallardDuck`, `ModelDuck`와
    행동 인터페이스 `FlyBehavior`(`FlyWithWings`/`FlyNoWay`/`FlyRocketPowered`),
    `QuackBehavior`(`Quack`/`Squeak`/`MuteQuack`)를 조합. 실행: `MiniDuckSimulator`.
- **ch02 — Observer (옵서버 패턴)** — `ch02/observer/`
  - 기상 관측 예제. `Subject`/`WeatherData`와 `Observer`/`DisplayElement` 디스플레이
    (`CurrentConditionsDisplay`, `ForecastDisplay`, `HeatIndexDisplay`, `StatisticsDisplay`),
    실행 `WeatherStation`. 추가로 Swing 기반 예제(`SwingObserverExample`,
    `AngelListener`, `DevilListener`).

> 예제 구성(오리 시뮬레이터·기상 관측소)은 『Head First Design Patterns』의 대표 예제와
> 동일합니다. (구성 근거 기반 추론)

## 프로젝트 구조

```
gof-design-pattern/
├── gof-design-pattern.iml
└── src
    ├── Main.java               # Hello world (진입점 샘플)
    ├── ch01/strategy/          # Strategy: Duck 시뮬레이터
    │   ├── MiniDuckSimulator.java
    │   ├── duck/               # Duck, MallardDuck, ModelDuck
    │   ├── fly/                # FlyBehavior 및 구현체
    │   └── quack/              # QuackBehavior 및 구현체
    └── ch02/observer/          # Observer: 기상 관측
        ├── subject/            # Subject, WeatherData, WeatherStation
        ├── display/            # *Display, DisplayElement
        └── swing/              # Swing 기반 Observer 예제
```
