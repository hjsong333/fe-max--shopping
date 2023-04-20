# 🛒 아마존 쇼핑몰
## 🎯 학습 목표

### Week #1
- sass 문법을 다양한 방식으로 적용하고 이해하기
- 모달의 작동 방식을 이해하고 구현하기
- DOM 조작으로 Carousel 구현하기
- 애니메이션 관련 CSS 속성을 이해하고 부드러운 전환 동작 구현해보기

### Week #2
- js 코드의 목적을 기준으로 디렉토리 구조 개선
- 객체지향 프로그래밍이 뭔지, 웹 프론트엔드에서 어떻게 구현할지 찾아보기
- ES Classes 표현 방식 적용
- (추가)`this`가 무엇을 가리키는지 공부

### Week #3
- Promise패턴 동작 방식 이해하고 활용하기
- json-server와 연동해서 데이터를 가져오는 방식을 히어로, 검색창, 사이드 메뉴에 적용하기

## 🔨 작업 리스트

### **상단 네비게이션바**
- [x] HTML, Sass로 상단 네비게이션 바의 기본 구조를 만든다.
- [x] 메인 페이지에 처음 진입하면 1초 뒤 로그인 모달이 나타난다.
  - [x] 로그인 모달 Element를 생성한다.
  - [x] 모달이 나타나는 동작을 로드 이벤트에 등록한다.
- [x] 로그인 영역에 마우스를 올리면 로그인 모달을 확장하고 배경을 딤처리 한다.
  - [x] 로그인 모달 확장.
  - [x] 배경 딤처리.
- [x] 주소 영역에 마우스를 올릴 때의 기능.
  - [x] 주소 모달이 나타난다.
  - [x] 배경 딤처리.
- [x] 마우스가 로그인 영역과 모달을 벗어나면 모든 레이어와 효과가 사라진다.
- [x] 모달이 나타나고 사라지고 확장하는 동작은 끊김없이 부드럽게 이루어진다.
- [x] 화면의 가로 사이즈가 1120px 이상으로 늘어날 경우, 검색바가 길어지며 사이즈에 맞춰진다.

### **히어로 영역**
- [x] 좌우 화살표를 클릭하면 내용을 변경한다.
- [x] 무한히 내용을 반복해서 보여준다.
- [x] 넘어가는 동작은 끊김없이 부드럽게 이루어진다.
- [x] 화살표를 누르지 않는 경우, 10초 후 다음 내용으로 넘어간다.
- [x] 콘텐츠가 임의로 늘어나도 동작한다.
- [x] 초기 이미지 URL를 json-server에서 받아온다.
- [x] 받아온 데이터로 DOM element를 렌더링한다.

### **검색창**
- [x] 검색바를 클릭하면 추천 검색어 10개가 표시된 레이어를 화면에 렌더링한다.
- [x] 검색한 내역을 최대 5개까지 추천 검색어 레이어에 표시하고 그 아래로 추천 검색어를 10개 표시한다.
- [x] 추천 검색어 레이어와 동시에 딤처리 영역을 렌더링한다.
- [x] 키보드의 화살표 키로 검색 내역과 추천 검색어를 이동하면 배경색을 변경한다.
- [ ] 검색한 키워드를 저장하고 최근 검색 목록에 표시한다.
- [ ] X아이콘을 누르면 최근 검색 목록을 제거한다.
- [ ] 검색어를 입력하면 연관 검색어를 10개까지 표시한다.

### **사이드 바**
- [ ] Figma 디자인에 있는 데이터로 초기 레이아웃 구현
- [ ] 사이드바 데이터를 json-server 데이터베이스에 넣기
- [ ] json-server에서 데이터를 가져와서 초기 컴포넌트 구현

## 🔑 기술 키워드

### Week #1
- CSS 전처리기(sass/scss)
- 웹 애니메이션(requestAnimationFrame/keyframe/transform + transition)
- HTMLDialogElement

### Week #2
- 객체지향 프로그래밍(OOP)
- ES Classes
- `this`

### Week #3
- fetch API
- Promise 패턴

## 🎊 고민과 해결

### Week #1
**JS, CSS 코드가 복잡하고 길어져서 나누고 구조를 잡아줘야 할 것 같다.**
- 히어로 영역 구현이 끝나고 리팩토링을 해봐야겠다.
- 새로 프로젝트를 만드는 것보다 지금 코드를 나눠보라고 추천을 한 이유가 뭘까?(feat.남세)

**모달을 HTML로 미리 작성해놓는게 JS 코드 가독성 면에서 더 좋지 않을까?**
- 모달 이벤트 핸들링 코드보다 DOM Element 만드는 코드가 더 길어서 중요한 로직에 집중할 수 없다.
- HTML로 미리 작성하는 것과 DOM Element를 렌더링 하는 것 중 어느게 성능상으로 더 좋을까?

**로그인/배송지 주소 탭에서 모달로 이동할 때, mouseout 이벤트가 발생하지 않으려면 두 요소를 바짝 붙이는 방법밖에 없을까?**

### Week #2
**js 모듈이 어떤 구조로 나눠져 있으면 이어서 개발하는 사람이 필요한 부분을 편하고 빠르게 찾을 수 있을까?**
- 단순하고 이해하기 쉽기 때문에 가장 일반적인 구조를 선택한다.
  ```
  js/
  │
  ├── components/
  │   ├── modal.js
  │   ├── navbar.js
  │   └── ...
  │
  ├── utils/
  │   ├── constants.js
  │   ├── helpers.js
  │   └── ...
  │
  └── index.js
  ```
- 메인 페이지만 구현하기 때문에 pages 디렉토리는 생략한다. (필요하게 되면 추가할 예정)

**DOM을 JS에서 생성,추가해야만 할까?**
- 동적으로 값을 추가해야할 필요가 있는 부분 외에는 HTML로 구조를 잡아주는 편이 JS에서 작업하기 훨씬 수월하다.
- 모달을 열고 닫는 동작의 구현에 집중할 수 있고, 코드도 훨씬 간결하다.

**SearchResultList에서 데이터를 받아온 후 처리하는 과정이 복잡하다**
- DataManager에서 2종류의 데이터를 한 번에 받고, 처리를 할 때 분리해서 처리한다.
- 데이터에서 렌더링까지의 흐름이 일관적이지 못하고 분기처리가 많이 일어난다.
- DataManager를 상속받는 객체들을 만들고, SearchResultList도 상속받는 객체들을 만들어서 짝을 지어주면 되지 않을까? 다형성을 사용하면 메서드 이름을 공유할 수 있어서 로직이 심플하게 정리될 것 같다.
- 구현은 했지만 templateBuilder와 dataManager가 로직상 강하게 결합되어 있어서 외부 주입이 아니라 내부에서 생성하게 했다.

### Week #3
**히어로 이벤트 핸들러를 등록할 때 렌더링된 아이템 개수를 어떻게 가져올까**
히어로 슬라이더의 기능 중 아이템 개수로 계산해야하는 함수가 있다. HTML로 아이템들을 미리 만들어뒀을때는 초기화할 때 DOM API로 아이템을 읽어와서 개수를 미리 확보할 수 있었다. 하지만, 서버에서 데이터를 받아와서 렌더링하는 방식을 적용한 후에는 이것이 불가능해졌다.

가장 간단한 방법은 해당 함수를 실행할 때마다 DOM 쿼리셀렉터로 아이템 개수를 세는거다. 하지만 불필요한 비용이라고 생각해서 다른 방법을 고민했다. 별다른 방법이 생각나지 않아 이벤트 등록 전에 쿼리셀렉터로 아이템을 찾고 매개변수로 필요한 함수까지 내려주는 방식을 적용했다. 이 방식이 마음에 들지는 않지만, slideTo() 함수에서 사용하던 쿼리셀렉터를 제거하는 부가효과가 생겨서 비용 절감 효과가 생겼다.

**사이드바의 백드롭을 body의 자식으로 둬야할까**
백드롭을 클릭이벤트로 사이드바를 닫아야하기 때문에 컴포넌트를 분리하는 것보다는 함께 관리하는 것이 좋다고 생각한다.
