---
slug: welcome
title: 커머스 용어 정리
authors: [slorber, yangshun]
tags: [facebook, hello, docusaurus]
---


머스트잇 커머스 용어 정리

| 용어 | 풀이 | 의미 |
|---|:---:|---:|
| `PRD` | Product Request Document | `스토리보드, 기획서, 요청서` |
| `LTS` | Launch To Service | `서비스를 시작하는 날 (오픈일)` |
| `VIP` | View Item Page | `상품 상세 페이지` |
| `Mini VIP` | Mini View Item Page | `리스트 페이지내 상품 미리보기` |
| `CPP` | Category Portal Page | `카테고리 페이지` |
| `LP` | List Page | `리스트 페이지` |
| `BLP` | Brand List Page | `브랜드 리스트 페이지` |
| `SRP` | Search Result Page | `검색 결과 페이지` |
| `DR` | Daily Request | `간단하고 단순한 작업` |
| `Dev2QA` | | `개발환경 (Release or Dev) 에서 QA/Test 진행` |
| `OMD` | Online MD |  |




| 값 | 의미 | 기본값 |
|---|:---:|---:|
| `static` | 유형(기준) 없음 / 배치 불가능 | `static` |
| `relative` | 요소 자신을 기준으로 배치 |  |
| `absolute` | 위치 상 부모(조상)요소를 기준으로 배치 |  |
| `fixed` | 브라우저 창을 기준으로 배치 |  |




| 값 | 의미 | 기본값 |
|---|:---:|---:|
| `static` | 유형(기준) 없음 / 배치 불가능 | `static` |
| `relative` | 요소 자신을 기준으로 배치 |  |
| `absolute` | 위치 상 부모(조상)요소를 기준으로 배치 |  |
| `fixed` | 브라우저 창을 기준으로 배치 |  |


[Docusaurus blogging features](https://docusaurus.io/docs/blog) are powered by the [blog plugin](https://docusaurus.io/docs/api/plugins/@docusaurus/plugin-content-blog).

Simply add Markdown files (or folders) to the `blog` directory.

Regular blog authors can be added to `authors.yml`.

The blog post date can be extracted from filenames, such as:

- `2019-05-30-welcome.md`
- `2019-05-30-welcome/index.md`

A blog post folder can be convenient to co-locate blog post images:

![Docusaurus Plushie](./docusaurus-plushie-banner.jpeg)

The blog supports tags as well!

**And if you don't want a blog**: just delete this directory, and use `blog: false` in your Docusaurus config.
