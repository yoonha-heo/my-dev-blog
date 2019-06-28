---
title: 'MarkDown 문법 정리'
date: 2019-6-26 16:32:10
category: 'TIL'
---

## 마크다운(MarkDown)이란?

- 텍스트 기반의 마크업언어
- 간단한 문법을 통해 가독성 좋은 컨텍츠를 작성 하는 데 유리
- HTML로 변환이 가능
- 깃헙의 README.md파일, Medium 블로그 글들, notions 등이 그 예
- 모든 HTML 마크업을 대신하진 못함
- 표준이 없음

## 마크다운 문법(Syntax)

- h1~h6는 #의 갯수로 표현 가능
- h1과 h2는 각각 ===, ---
- Bold ** (두껍게 하고 싶은 단어) **
- Italic _ (기울이고 싶은 단어) _

  - **BOLD**
  - _Italic_

- 링크는 [] 내에 링크제목, () 내에 url과 "" 링크설명 작성

  - [Google](https://google.com '구글검색을 원한다면 여기 클릭')

* 이미지는 앞에 !를 붙이는걸 제외하고 링크와 같음
  ![제목](https://travelblog.expedia.co.kr/wp-content/uploads/2016/12/08.jpg '비행기 사진')

* 이미지에 링크를 걸고 싶으다면 이미지 코드를 링크코드로 묶어줌 ![]() 를 []로 묶고 () 내에 url과 링크설명
  [![구글](https://littledeep.com/wp-content/uploads/2019/03/google_logo_download_thumbnail.png)](https://google.com '구글로 이동')
* 인라인 코드 강조 `로 감싸줌

  - `className`

    <br>

- 블록 코드 ` 세번 이상 적고 작성하는 코드 종류를 적어준다

```js
function doubleNum(num) {
  return num * 2
}
```

<br>

- 표 생성시 column은 |로, 헤더셀 구분은 ---로, 정렬은 :의 위치에 바꿔주므로서 가능

| 숫자 | 영어 |   한글 |
| ---- | ---: | -----: |
| `1`  |  one | `하나` |
| `2`  |  two |   `둘` |

<br>

- 인용문 > 기호로, > 갯수에 따라 nested 인용문도 가능
  > quote1
  >
  > > quote2
  > >
  > > > quote3

<br>
<br>
