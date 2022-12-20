---
sidebar_position: 1
---

# 코딩 컨벤션

코드 표준화를 위한 정리

## 공통

1. 모든 애트리뷰트는 큰따옴표 <code>""</code> 사용
2. 들여쓰기는 <code>tab</code>(space 4) 사용
   - vscode 기준 -> preferences > setting > text editor > tab size
3. id 사용은 스타일이 아닌 coupling에만 사용

## import

> css 다음 js 선언 (랜더링 속도를 높일 수 있는 병렬 다운로드가 가능)

```html
<link rel="stylesheet" href="<?=SWIPER_CSS?>" />
<script src="<?=SWIPER_JS?>"></script>
```

## 주석

> 주석을 남겨야 하는 상황에서는 시작과 끝을 표시해 두어요.



```html
시작
<!-- 날짜, 내용, 이름 -->

종료
<!-- // 날짜, 내용, 이름 -->

<!-- 220719 vip 모듈 수정 hyj -->
<!-- // 220719 vip 모듈 수정 hyj -->
```

### 컨텐츠 영역에 주석 표기

```html
<!-- content -->
<div id="content">
  <!-- 네임카드 -->
  <div class="namecard">...</div>
  <!-- //네임카드 -->
</div>
<!-- //content -->
```

### 개발 적용 관련 주석 표기

```html
<!-- content -->
<!-- [D] 케이스별 클래스 변화 
의사 : my_doctor
변호사 : my_lawyer
-->

<!-- or -->

<!-- [D] 생성된 버튼 파일명은 _on 추가 -->
```

## input

### input,select,textarea의 경우 같은 form 요소는 for 어트리뷰트를 부여하여 coupling

```html
<input type="radio" name="alignment" id="align_left" />
<label for="align_lft">왼쪽 정렬</label>

<input type="checkbox" name="sports" id="soccer" />
<label for="soccer">축구</label>
```

### label 안에 input이 있는 경우는 for 어트리뷰트 사용 X

```html
<label><input type="checkbox" name="sports" />축구</label>
```

### 회원가입 폼의 입력 필드처럼 너비, 높이가 유동적이라면 인라인 스타일로 제어

```html
<!-- Bad -->
<input type="text" class="input input--width-120" />
<input type="text" class="input input--width-180" />

<!-- Good -->
<input type="text" class="input" style="width:120px" />
<input type="text" class="input" style="width:180px" />
```

### title 속성을 사용하면 접근성 향상 (image 경우 alt 사용)

```html
<input type="image" src="btn_confirm.png" alt="확인" />
<input type="text" id="num1" name="num1" title="지역번호" />
<input type="text" id="num2" name="num2" title="국번" />
<input type="text" id="num3" name="num3" title="전화번호" />
```

## button type을 명시

```html
<button type="button">버튼</button>
```

## 빈줄

> HTML 코드의 빈줄은 의미 있는 객체를 구분하기 위하여 사용 (1줄만 사용)

## self-closing

> html5는 self-closing이 선택사항이지만, 생략
> 하지만 xhtml에서는 xml 문법을 따라가니 <code>필수</code>

```html
<!-- html5 Recommend -->
<br>
<input>

<!-- xhtml Essential-->
<br />
<input />
```


> void-elements (슬러시 앞의 공백은 선택 사항)

```html

<area />
<base />
<col />
<command />
<embed />
<hr />
<img />
<input />
<keygen />
<link />
<menuitem />
<meta />
<param />
<source />
<track />
<wbr />

```

## tag
> id는 개발에서만 사용할 수 있게 남김<br />
> coupling 시만 예외적으로 사용

```html 
<!-- bad -->
<article id="mypage" class="sub_content"></article>


<!-- good-->
<article class="sub_content mypage_content"></article>

```


## name rule

> 비지니스 로직을 사용하는 속성은 camelCase로 네이밍을 작성

```html
<input class="input" type="text" name="myUserName">
```



## id: camel case

```html
<!-- Bad -->

<div id="error_Message"></div>
<div id="checkbox_3"></div>


<!-- Good -->
<div id="errorMessage"></div>
<div id="checkbox3"></div>

```


### class: snake case


> 형태_의미_순서_상태_child <br />
> child 속성은 단 한번만 사용해요


```html
<!-- Bad -->
<div class="error_Message"></div>
<div class="control-center"></div>

<!-- Good -->
<div class="error_message"></div>
<div class="control_center"></div>

<!-- child -->
<article class="card_ui">
  <div class="card_ui__thumbnail">...</div>
  <div class="title">....</div>
  <div class="desc">....</div>
</article>
```

### 예약어(약속어)

```html
*_content // 페이지 wrapper -> section
comp_* // 공통 사용되는 것
icon_ // 아이콘
header_ // 해더
footer_ // 푸터
layer_ // layer
divider // 구분선
lnb
```

### 종속 확장

> 몇 가지 소소한 변경

```html
<div class="grade_info grade_black"></div>
<div class="grade_info grade_red"></div>
<div class="grade_info grade_blue"></div>
<div class="grade_info grade_green"></div>
<div class="grade_info grade_friends"></div>
```


### 독립확장

> 완전히 다른 변경


```html

<div class="grade_info1"></div>
<div class="grade_info2"></div>
<div class="grade_info3"></div>

```

### icon
> 아이콘은 i 태그를 사용

```html
<!-- icon_기호_기호속성_기호속성_사이즈 -->
<i class="icon_arr_r_12"></i>
<i class="icon"><img src="icon.png"></i>
```


### File 네이밍
> 페이지이름_의미_상태로 표시 <br />
> php는 _v 라는 접미어를 사용

```html
<!-- as 신청 -->
as_apply_view_v
as_apply_list_v
```

### layer

> 페이지이름_의미_상태로 표시 <br />
> php는 _v 라는 접미어를 사용


```html
<!-- 구매취소 -->
buy_cancle_v
<!-- 구매취소 정보-->
buy_cancle_info_v
```


## 페이지안에 inline Style은 유지보수가 어려움(이벤트 페이지 제외)
> 유지보수가 어려워지므로 사용 금지

## 페이지엔 단 하나의 h1만 사용
> 예시) 상단 타이틀을 h1으로(없을 경우), 블록단위로 제목을 h2로 준다


## a tag안의 block tag
> html5안에서는 a 태그만 안에 블록태그 사용이 가능 <br />
다른 인라인 태그와 html5가 아니면 안됨


## table

> caption 사용<br />
table 제목이 필요 없거나 이미 제공되어 있다면 생략 가능


```html
  <table>
    <caption>table_title</caption>
  </table>

  <!-- Bad -->
  <h4>My Caption</h4>
  <table>
    <caption>
      <div class="blind">My Caption</div>
    </caption>
  </table>

  <!-- Not Bad -->
  <h4>My Caption</h4>
  <table></table>

  <!-- Good -->
  <h4 id="caption">My Caption</h4>
  <table aria-labelledby="caption"></table>

```

> caption view를 숨길 땐 새로운 tag로 감싸세요


```html
<!-- Bad -->
<table>
  <caption class="blind">My Caption</caption>
</table>

<!-- Good -->
<table>
  <caption>
    <div class="blind">My Caption</div>
  </caption>
</table>

```
> colgroup 사용

```html
  <table>
    <colgroup>
      <col style="width:200px" /><!-- good -->
      <col width="400px" /><!-- bad -->
    </colgroup>
  </table>

```
> table에 직접 클래스를 명시하기 보다는 tag로 감싸서 스타일을 선언한다

```html
<div class="size_table">
  <table>...</table>
</div>
```


> thead, tbody, tfoot은 내용이 구분 될 경우 사용

```html
<thead>
  <tr>
    <th>...</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>...</td>
  </tr>
</tbody>


<!-- 생략가능 -->
<tr>
  <th>...</th>
  <td>....</td>
</tr>
```

## 사용자 인터렉션

### 페이지 이동은 a , 나머지는 button을 사용

```html
<!-- 페이지 이동 -->
<a href="https://mustit.co.kr/" title="머스트잇으로 이동" target="_blank"></a>

<!-- 나머지 -->
<button type="button">탭1</button>
<button type="button">탭2</button>
<button type="button">탭3</button>

```


## video
> load 전 보여지는 poster 사용

```html
<video controls playsinline loop autoplay muted poster="<?=$eventImgPath?>video.png">
  <source src="<?=$eventImgPath?>video.mp4" type="video/mp4">
</video>

<video class="main_video" playsinline autoplay muted controlsList="nodownload" oncontextmenu="return false" poster="<?=$eventImgPath?>poster.png">
<source src="<?=$eventImgPath?>main.mp4" type="video/mp4">
</video>
```


## 애트리뷰트
> HTML5에서는 Boolean 애트리뷰트를 선언하는 것 만으로도 true 값을 가짐, 필요하지 않으면 값을 작성하지 마세요

```html
<!-- Not Bad -->
<button type="button" disabled="true"></button>

<!-- Good -->
<button type="button" disabled></button>

```

## 시멘틱 태그(html5 한정)
> div 대신 의미 있는 태그 사용

```html
<header>
  <nav></nav>
  <main>
    <section>
      <article></article>
    </section>
  </main>
  <footer></footer>
</header>
```

> 큰틀은 section을 사용(wrapper 개념)<br />
작은 틀은 article 사용(child로 article을 중복 사용 하지 않음)


```html
<section class="sub_content">
  <article>
    <div class="top"></div>
  </article>
</section>
```



MD 문법

**굵게**

[링크](https://mustit.co.kr/)
