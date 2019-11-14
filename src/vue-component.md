# 싱글파일 컴포넌트
화면의 특정 영역에 대한 HTML, CSS, JS 코드를 한 파일에서 관리하는 방법.
vue 확장자를 가진 파일을 모두 싱글 파일 컴포넌트라고 함


```
<!-- .vue 파일 구조 -->
<template>
  <!-- html (뷰 컴포넌트의 표현단, 템플릿 문법) -->
</template>

<script>
  // 자바스크립트 (뷰 컴포넌트 내용)
</script>

<style>
  /* CSS (뷰 템플릿의 스타일링) */
</style>

```


### 동작 원리
싱글 파일 컴포넌트가 웹브라우저에서 인식할 수 있는 형태의 파일로 변환되어야 하는데, 그때 필요한 것이 뷰로더. <br>
싱글파일 컴포넌트는 뷰로더에 의해 HTML, CSS, JS 와 같은 웹 자원으로 분리되어 실행됨.<br>
뷰로더는 웹펙에서 지원하는 라이브러리이고, 뷰 CLI로 프로젝트를 생성하면  기본 설정이 되어 있음.

<br>

**읽어보면 좋은거!**<br>
[뷰에서 컴포넌트 템플릿을 정의하는 7가지 방법](https://github.com/FEDevelopers/tech.description/wiki/Vue%EC%97%90%EC%84%9C-%EC%BB%B4%ED%8F%AC%EB%84%8C%ED%8A%B8-%ED%85%9C%ED%94%8C%EB%A6%BF%EC%9D%84-%EC%A0%95%EC%9D%98%ED%95%98%EB%8A%94-7%EA%B0%80%EC%A7%80-%EB%B0%A9%EB%B2%95)



<br>
<br>


## 템플릿
template은 HTML,CSS 등 마크업 속성과 뷰 인스턴스에서 정의한 데이터 및
로직들을 연결하여 브라우저에서 볼 수 있는 형태의 HTML로 변환해 주는 속성

뷰 내부적으로 template 속성에서 정의한 마크업 + 뷰 데이터를
가상 돔 기반의 render() 함수로 변환한다.
이 render함수는 최종적으로 사용자가 볼 수 있게 화면을 그리는 역할을 한다.


#### 사용 방법
1. ES5에서 뷰 인스턴스 template속성을 활용
2. 싱글 파일 컴포넌트 체계의 `<template>` 코드 활용.  <- 우리가 사용하는거

<br>
<br>

## 템플릿 문법
https://kr.vuejs.org/v2/guide/syntax.html


1. 데이터 바인딩
    - {{}}
      - 이중괄호/mustache/콧수염 괄호
      - 기본적 텍스트 삽입 방식. (다른 프레임 워크에서도 사용.)
      - 괄호 안에 있는 속성 값으로 대체. -> 값이 변경될때 마다 변경
      - 스크립트 사용가능 (선언문과 분기구문은 사용 할 수 없음. + 복잡한 연산은 인스턴스 안에서..)
    ```
     <p>Hello {{ message }}</p>
    ```

      - v-text
      이중괄호와 거의 동일하게 작동.
      ```
      <p>Hello <span v-html="message"></span></p>
      ```

    - v-html
  HTML문자열을 그대로 바인딩



    * 주의 : 웹사이트에서 임의의 HTML을 동적으로 렌더링하면  XSS취약점으로 이어질 수 있어서 위험함. 신뢰할 수 있는 콘텐츠에서만 보간을 사용하고 사용자가 제공한 콘텐츠에서는 절대 사용하면 안됨.



2. 디렉티브
HTML 태그 안에 v-접두사를 가지는 모든 속성.
- v-if : if문 , 태그 완전 삭제 (코드에서 안보임.)
  - https://kr.vuejs.org/v2/guide/conditional.html#v-if
  - https://beomy.tistory.com/51
- v-for : for문. :key값 반드시 써줘야함
    - https://kr.vuejs.org/v2/guide/list.html#기본-사용방법
    - https://kr.vuejs.org/v2/guide/list.html#v-for%EC%99%80-%EA%B0%9D%EC%B2%B4
    - https://beomy.tistory.com/52?category=646688
- v-show : if와 비슷하나 display:none 시켜 실제 태그는 남아있고, 화면에서는 안보임.
    - https://kr.vuejs.org/v2/guide/conditional.html#v-show
- v-bind : html 태그 기본 속성과 뷰 데이터 속성 연결
  - https://medium.com/@hozacho/%EB%A7%A8%EB%95%85%EC%97%90-vuejs-003-vuejs-directive-v-bind-a4844574e6ae
- v-on : 이벤트 수신


[vue 공식 가이드](https://kr.vuejs.org/v2/guide/syntax.html)









