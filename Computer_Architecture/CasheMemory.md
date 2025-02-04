# :money_with_wings: CasheMemory

### 정의

자주 사용하는 데이터나 값을 미리 복사하여 저장해두기 위한 메모리

> **캐시(Cashe)**<br>
> 데이터에 접근하는 시간을 절약하기 위해 임시로 데이터를 저장해두는 장소

### 특징

- CPU와 메인 메모리 사이에서 데이터의 빠른 전달을 위해 존재한다.
- 메인 메모리에 비해 작고 비싸다.
- 임시 저장소로, 캐시 메모리에 저장된 데이터는 언제든 지워질 수 있다.

### 동작 방식

CPU는 여러개의 캐시 메모리를 사용하는데, 속도와 크기에 따라 분류하여 L1, L2, L3 등으로 나타낸다.

순차적으로 검사하여 데이터를 찾아나가는데, 데이터에 접근할 때 지역성(Locality)을 따른다.

#### 지역성

지역성은 데이터에 균등하게 접근하는 것이 아니라, 특정 부분을 집중적으로 참조하는 특성이다.

대표적인 캐시의 지역성에는 `시간 지역성(Temporal Locality)` / `공간 지역성(Spatial Locality)`이 있다.

> <strong>시간 지역성</strong><br>
> 최근에 사용했던 데이터가 재참조될 가능성이 높음

> <strong>공간 지역성</strong><br>
> 최근에 접근했던 데이터의 인접 데이터가 참조될 가능성이 높음

### 성능 평가

CPU가 필요로 하는 데이터를 얼마나 자주 캐시 메모리에서 찾을 수 있는가(`Hit Ratio`)가 평가의 기준이 된다.

이때, 필요한 데이터가 캐시 메모리에 존재하는 경우를 `Cashe Hit` , 존재하지 않아 메모리에서 가져와야 하는 경우를 `Cashe Miss`라고 한다.

Hit이 많이 발생하는 것보다, Miss가 적게 발생하는 것이 중요하다.

### 캐시 미스(Cashe Miss)

#### 종류

1. Cold miss
   - = Compulsory Miss
   - 데이터에 처음 접근하려할 때(컴퓨터를 처음 켰을 때 등) 강제적으로 발생
   - 이 미스가 발생하면, 메모리에서 데이터를 불러와 저장한다.
2. Capacity miss
   - 접근하려는 데이터의 크기가 캐시의 크기보다 클 때 발생
3. Conflict miss
   - = Collision miss
   - 하나의 캐시 주소에 여러 데이터를 저장하려 할 때 발생

#### 해결법

1. 캐시의 수명(저장 기간)을 늘린다.
2. 캐시 교체 알고리즘을 최적화한다.
3. 메모리 크기를 늘린다.

### 캐시 활용 사례

- 컨텐츠 딜리버리 서버: 자주 사용하는 파일을 가까운 지역의 서버에 저장하면서 빠르게 접근할 수 있도록 함

### 추가 공부 내용

- 캐시 메모리의 내부 구조
- 캐시 메모리의 주소 매핑 방식
- 캐시 교체 알고리즘(캐시 정책)

### 참고자료

- [CPU의 캐시 메모리는 어떤 역할을 하는가?](https://it.donga.com/215/)
- [캐시 메모리 (Cache Memory) 개념, 기법](https://wikidocs.net/65523)
- [Cache Miss](https://redis.com/glossary/cache-miss/)
