# vuejs-practice
vuejs spring

vue.js 구조 
SPA : Single Page Application 하나의페이지에서 정보를 보여줌
SFC : Single File component : 하나의 컴포넌트안에서 html ,css, js가 관리됨

Options API : data, methods, mounted 같은 객체를 활용하여 컴포넌트 로직을 정의하는 방식
this.함수로 접근가능

Composition API : import 키워드를 통해서 가져온 Vue.js API 함수 또는 속성들을 사용하여 컴포넌트 로직을 정의하는 스타일

data : 데이터들을 관리  method : 속성값을 변경,업데이트 할수있는 함수, 템플릿 내에서 이벤트 핸들러로 바인딩 가능

데이터바인딩의 형태 {{}}이중 중괄호(텍스트로 해석함)

v-if : 조건식이 true를 반환하는 경우에만 렌더링
v-show : v-if랑 비슷하지만 v-show가있는 엘리먼트는 항상 렌더링되서 DOM에 남아있음
v-if 전환비용높음 v-show : 초기 렌더링 비용높음: 당연히 다 렌더링되기때문에

v-for는 item in items 의 문법이 사용됨
item : 배열내 반복되는 엘리먼트 별칭  items : 배열데이터
key값을 써야하는이유 id를 기반으로 삭제되는 기능을 식별하기떄문에 dom이 하나만 제거
key가 없으면 더많은 dom을 업데이트해야함(즉 부하가많다)

<div v-for="(user, index) in users" :key="index> 이렇게 key값을 index값으로 받으면안됨 user.name이런 고유한 값으로 받아야함
고유한값이아니면 그전에 있던 데이터가 써지기떄문

인라인핸들러 : 기능을 동작하는코드가 HTML Element 내에 직접 할당이되있음
<button onclick="alert('Hello, World!')">클릭하세요</button> 이렇게 onclick처럼 안에 직접 할당되어있음
HTML 요소의 속성 안에 직접적으로 이벤트 처리 코드를 작성하는 것을 말함

메서드 핸들러 : 메서드를 이벤트에 할당해주는 방식

watch 속성 :어떤 데이터를 감시하다가 그 데이터값이 변했을 때 그것을 감지하여 그와관련된 함수나 로직을 사용할수있게함
예를들어 게시판페이지에서 번호를 클릭했을때 선택한 페이지에 대한 리스트를 보여주는데 쓰는데 적합함

computed : 캐싱이 default

Prop은 부모-자식 관계의 Components관계에서 실행된다

뷰에서 말하는 라우터는 쉽게 말해서 URL에 따라 어떤 페이지를 보여줄지 매핑해주는 라이브러리라고 보면 된다.
URL을 입력하거나 페이지이동이 감지되면 routes에 정의된 path를 기준으로 맵핑을해서 연결된 컴포넌트를 router-view에 렌더링
router-link 는 매칭된 경로로 이동시켜줌

Axios는 자바스크립트로 HTTP 요청을 처리하기 위한 Promise 기반의 HTTP 클라이언트JSON 형식

vscode에서 vue 실행 yarn serve --port 8800

:class="{ active: active.name }"는 active.name이 true일 때만 active라는 클래스 이름을 추가합니다.
Vue 컴포넌트가 렌더링될 때, active.name의 초기값을 읽어 :class로 동적 클래스를 적용합니다.
사용자가 active.name 값을 바꾸면 (예: 버튼 클릭 등), Vue가 이 변화를 감지합니다.
Vue는 변화를 기반으로 DOM을 업데이트하여, 클래스(active)를 추가하거나 제거합니다.
