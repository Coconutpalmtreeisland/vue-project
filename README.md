# vue를 이용한 포트폴리오 사이트 만들기
Vue.js, 일반적으로 "뷰"라고 불리는 JavaScript 프론트엔드 프레임워크입니다. Vue는 웹 애플리케이션의 사용자 인터페이스(UI)를 개발하기 위한 도구로, 데이터와 UI를 효과적으로 관리하고 구성할 수 있도록 도와주는 오픈 소스 라이브러리입니다. Vue.js는 직관적이며 가볍고 빠른 프레임워크로 많은 웹 개발자들에게 사랑받고 있습니다.

1. Vue.js의 주요 특징과 개념은 다음과 같습니다:

2. Component-Based Architecture (컴포넌트 기반 아키텍처): Vue.js는 UI를 작은 컴포넌트로 분해합니다. 각 컴포넌트는 재사용 가능하며 독립적으로 작동합니다. 이를 통해 애플리케이션의 구성 및 유지 관리가 용이해집니다.

3. Vue 인스턴스: Vue 애플리케이션은 Vue 인스턴스로 구성됩니다. Vue 인스턴스는 데이터, 메서드, 계산된 속성, 감시자 등을 정의하여 애플리케이션의 동작을 제어합니다.

4. 양방향 데이터 바인딩: Vue.js는 모델과 뷰 간의 양방향 데이터 바인딩을 지원합니다. 이것은 데이터의 변경이 자동으로 UI에 반영되고, UI에서의 변경이 데이터에 반영되는 것을 의미합니다.

5. Directives: Vue에서 사용하는 지시자(Directives)는 HTML 요소에 특별한 속성을 추가하여 DOM 조작 및 데이터 연결을 수행할 수 있도록 합니다. 예를 들어, v-for, v-if, v-bind, v-on 등의 지시자가 있습니다.

6. Computed Properties (계산된 속성): Vue.js에서는 계산된 속성을 정의하여 데이터에 기반한 동적인 값 계산을 간편하게 수행할 수 있습니다. 이를 통해 뷰의 업데이트를 효율적으로 처리할 수 있습니다.

7. 이벤트 처리: Vue.js는 이벤트 핸들링을 간편하게 제공하며, 이벤트 메서드와 메서드 호출을 통해 사용자 상호작용을 처리합니다.

8. 라우팅 및 상태 관리: Vue Router를 사용하여 앱 내에서 페이지 라우팅을 관리하고, Vuex를 사용하여 상태 관리를 효율적으로 수행할 수 있습니다.

9. 생명주기 훅: Vue 컴포넌트는 다양한 생명주기 훅을 가지고 있어, 컴포넌트의 생성, 업데이트, 제거 등의 이벤트를 제어하고 작업을 수행할 수 있습니다.

Vue.js는 간단한 프로젝트부터 대규모 웹 애플리케이션까지 다양한 프로젝트에서 사용됩니다. 뛰어난 문서화와 활발한 커뮤니티 지원이 있는 Vue.js를 사용하면 웹 개발 작업을 효율적으로 수행할 수 있습니다.

## 초기 설정
1. 최근 버전 설치 `npm init vue@latest`
2. 파일 이름 설정 Project name: ... `vue-project`
3. 추가 설치 설정
√ Add TypeScript? ... `No` / Yes   
√ Add JSX Support? ... No / `Yes`
√ Add Vue Router for Single Page Application development? ... No / `Yes`   
√ Add Pinia for state management? ... `No` / Yes   
√ Add Vitest for Unit Testing? ... `No` / Yes   
√ Add an End-to-End Testing Solution? » `No` / Yes   
√ Add ESLint for code quality? ... No / `Yes`   
√ Add Prettier for code formatting? ... No / `Yes`

4. 해당 파일 들어가기 `cd vue-project`
5. 파일에 vue 설치 `npm install`
6. 페이지 열기 `npm run dev`
7. GitHub에 Repositories에 `vue-project` 생성

## 플러그인 설치
gsap 설치 : `npm install gsap`
sass 설치 : `npm install sass`
lenis 설치 : `npm install @studio-freight/lenis`

## 파일 정리
- assets: 폴더 안 삭제
- components: 폴더 안 삭제
- router: index.js 빼고 삭제
- views: HomeView.vue 빼고 삭제

- main.js: css 삭제
- index.js: about 삭제

## 페이지 설정 App.vue
<details>
    <summary>App.vue 설정</summary>

    <script setup>
    import { RouterView } from "vue-router";
    </script>
    <template>
    <RouterView />
    </template>

</details>

## 페이지 설정 HomeView.vue
<details>
    <summary>HomeView.vue 설정</summary>

    <script setup>
    import ContactSection from '../components/ContactSection.vue';
    import FooterSection from '../components/FooterSection.vue';
    import HeaderSection from '../components/HeaderSection.vue';
    import IntroSection from '../components/IntroSection.vue';
    import PortSection from '../components/PortSection.vue';
    import SiteSection from '../components/SiteSection.vue';
    import SkillSection from '../components/SkillSection.vue';
    import SkipSection from '../components/SkipSection.vue';
    </script>
    <template>
    <SkipSection />
    <HeaderSection />
    <main id="main" role="main">
        <IntroSection />
        <SkillSection />
        <SiteSection />
        <PortSection />
        <ContactSection />
    </main>
    <FooterSection />
    </template>
    
</details>

## scss 설정

## 트러블 슈팅
<details>
    <summary>
        Whitespace 에러(LF will be replaced by CRLF the next time Git touches it)
    </summary>

    `git config --global core.autocrlf true`

</details>

## 배포 (vercel)
1. Select a Git Namespace
2. Add Github Account 계정 선택
3. 배포할 git Import 클릭
4. depoly 클릭
5. 자동으로 배포 완료
6. 도메인 이름 변경 `coconut-vue-project-omega-vert.vercel.app`