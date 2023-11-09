# vue를 이용한 포트폴리오 사이트 만들기
Vue.js는 웹 애플리케이션을 구축하기 위한 프로그레시브 프레임워크입니다. HTML, CSS 및 JavaScript를 사용하여 사용자 인터페이스를 개발하는 데 도움이 되는 오픈 소스 JavaScript 프레임워크입니다. Vue는 단일 페이지 애플리케이션(SPA) 및 웹 애플리케이션의 구성 요소 기반 아키텍처를 채택하여 UI를 만들고 관리하는 것을 목표로 합니다.

Vue.js는 다른 프레임워크인 React나 Angular와 비슷한 기능을 제공하지만, 상대적으로 가볍고 간편한 문법과 사용자 친화적인 API를 제공하여 학습 곡선이 낮고 빠르게 개발할 수 있도록 도와줍니다.

반응성 (Reactivity): Vue는 데이터와 UI 간의 반응적인 연결을 제공하여 데이터 변경 시 UI가 자동으로 업데이트됩니다.

컴포넌트 기반 구조: Vue는 재사용 가능한 작은 구성 요소들로 애플리케이션을 구축하는 데 중점을 두고 있습니다. 이는 코드의 유지보수와 재사용성을 높여줍니다.

가상 DOM (Virtual DOM): Vue는 변경 사항을 추적하고 실제 DOM에 적용하기 전에 가상 DOM을 사용하여 효율적으로 업데이트를 처리합니다.

템플릿 및 JSX: Vue는 HTML 기반 템플릿을 사용하여 UI를 설계할 수 있지만, 필요에 따라 JavaScript 안에서 JSX와 같은 문법을 사용할 수도 있습니다.

라우팅 및 상태 관리: Vue Router를 사용하여 클라이언트 측 라우팅을 지원하고, Vuex와 같은 상태 관리 패턴을 통해 애플리케이션 상태를 효율적으로 관리할 수 있습니다.

## 셋팅 
`npm init vue@latest`
√ Project name: ... vue-project         
√ Add TypeScript? ... <span="color: blue">No</span> / Yes       
√ Add JSX Support? ... No / <span="color: blue">Yes</span>      
√ Add Vue Router for Single Page Application development? ... No / <span="color: blue">Yes</span>       
√ Add Pinia for state management? ... <span="color: blue">No</span> / Yes       
√ Add Vitest for Unit Testing? ... <span="color: blue">No</span> / Yes      
√ Add an End-to-End Testing Solution? » No      
√ Add ESLint for code quality? ... No / <span="color: blue">Yes</span>      

## [미리보기]()

## 작업 순서
1. 리액트 설치
2. git에 업로드
3. [lenis 사이트](https://github.com/studio-freight/lenis)

## 설치
2. gsap 설치 `npm install gsap`
3. sass 설치 `npm install sass`
4. lenis 설치 `npm i @studio-freight/lenis`

## 트러블 슈팅
<details>
<summary>Whitespace 에러 </summary>
유닉스 시스템에서는 한 줄의 끝이 LF(Line Feed)로 이루어지는 반면,
윈도우에서는 줄 하나가 CR(Carriage Return)와 LF(Line Feed), 즉 CRLF로 이루어지는데
Git이 이 둘 중 어느 쪽을 선택할지 혼란이 온 것이다!

해결방법   
`git config --global core.autocrlf true // 시스템 전체에 적용`   
`git config core.autocrlf true // 해당 프로젝트에만 적용`   
</details>

### GSAP
GSAP, 또는 GreenSock Animation Platform은 웹 애니메이션을 만들기 위한 강력한 JavaScript 라이브러리입니다. GSAP는 HTML, SVG, 캔버스 등 다양한 웹 요소를 애니메이션화하는 데 사용됩니다.   
   
이 라이브러리는 강력한 기능과 직관적인 API를 제공하여 다양한 애니메이션 효과를 만들기 쉽게 합니다. GSAP는 성능이 우수하며, 애니메이션의 부드러움과 자연스러움을 유지하는 데 강점을 가지고 있습니다.

### lenis
lenis.js는 JavaScript로 작성된 오픈 소스 웹 프레임워크입니다. 이 프레임워크는 웹 애플리케이션 및 API를 개발하기 위해 사용됩니다. lenis.js는 경량화되고 빠른 속도로 동작하며, 간단한 문법과 구조를 제공하여 개발자가 쉽게 웹 애플리케이션을 구축할 수 있도록 도와줍니다.

## firebase
프로젝트 생성
firebase login
Yes
firebase init
Yes
Hosting: Configure files for Firebase Hosting and (optionally) set up GitHub Action deploys 스페이스바로 선택
Use an existing project
react-project23 (react-project23)

build
No
No
No

## class 이름에 v-for key결합

img :id=" `thumbnail_${id}` " :src="image"/
article :class="`port__item p${key + 1}`" v-for="(art, key) in portText" :key="key"


##toggle menu
:class="{ show: isNavVisible } // show클래스 추가(isNavVisible이 true일때)
:aria-expanded="isNavVisible.toString()" // 토글메뉴에
                @click="toggleMobileMenu" // 토글메뉴에

export default {
    data() {
        return {
            isNavVisible: false,
        };
    },
    methods: {
        toggleMobileMenu() {
            this.isNavVisible = !this.isNavVisible; //값 반전시킴
        },
    },
};