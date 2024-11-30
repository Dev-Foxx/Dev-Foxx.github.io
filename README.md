# Jekflix 템플릿

![Jekflix 템플릿 커버 이미지](https://res.cloudinary.com/dm7h7e8xj/image/upload/v1505354182/jekflix-logo_mfngps.png)

[데모 보기](https://jekflix.rossener.com/).

## 이게 뭐야?

영화와 시리즈를 좋아하는 사람들을 위해 Netflix 패널에서 영감을 받아 만들어진 Jekyll 테마입니다. 멋진 외관의 블로그를 만들고 싶다면 이 테마가 적합합니다.

![Jekflix 스크린샷 이미지](https://res.cloudinary.com/dm7h7e8xj/image/upload/v1566390829/jekflix-screenshot-2_zfiog2.jpg)

## 기능

- [실시간 검색](docs/features.md#live-search)
- [예상 읽기 시간](docs/features.md#estimated-reading-time)
- [읽기 진행률 표시줄](docs/features.md#reading-progress-bar) *(옵션)*
- ["새 게시물" 태그](docs/features.md#new-post-tag)
- [수요에 따른 이미지 로드](docs/features.md#load-images-on-demand)
- [푸시 메뉴](docs/features.md#push-menu)
- [SVG 아이콘](docs/features.md#svg-icons)
- [게시물 생성 쉘 스크립트](docs/features.md#shell-script-to-create-posts)
- [태그 페이지](docs/features.md#tags-page)
- [소개 페이지](docs/features.md#about-page)
- [연락처 페이지](docs/features.md#contact-page)
- [404 오류 페이지](docs/features.md#404-error-page)
- [RSS 피드](docs/features.md#feed-rss)
- [Disqus](docs/features.md#disqus) *(옵션)*
- [추천 게시물](docs/features.md#featured-post) *(옵션)*
- [홈 페이지 페이지네이션](docs/features.md#home-page-pagination) *(옵션)*
- [게시물 사이드바](docs/features.md#posts-sidebar) *(옵션)*
- [페이지네이션된 게시물](docs/features.md#paginated-posts) *(옵션)*
- ["떠나기 전" 모달](docs/features.md#before-you-go-modal) *(옵션)*
- [게시물 추천](docs/features.md#post-recommendation)
- [Netlify CMS 지원](docs/features.md#netlify-cms-ready)
- [번역](docs/setup.md#translations) **새로 추가됨!**
- [수학 표현](docs/features.md#math-expressions) *(옵션)* **새로 추가됨!**

## SEO

- 구글 애널리틱스
- 메타 태그
- JSON-LD
- Sitemap.xml
- 소셜 미디어 준비 완료

## 빠른 설치

기존 Jekyll 프로젝트에 설치하는 경우, 프로젝트의 `Gemfile`에 다음 줄을 추가하십시오:

```ruby
gem "jekflix"
```

프로젝트의 `_config.yml`에 다음 줄을 추가하십시오:

```yaml
theme: jekflix
```

그런 다음 다음 명령어를 실행하십시오:

```bash
$ bundle
```

또는 직접 설치하려면 다음을 실행하십시오:

```bash
$ gem install jekflix
```

### 테마 색상

파일 `/assets/css/styles.scss`를 만들고 다음을 추가하십시오:

```scss
---
---

$themeColor: #ff0a16; # 테마의 기본 색상 설정
$primaryDark: #141414; # 기본 어두운 색상 설정
$accentDark: #ffffff; # 강조 어두운 색상 설정
$lightGray: #f2f2f2; # 밝은 회색 설정
$texts: #333333; # 텍스트 색상 설정

@import "jekflix"; # jekflix 스타일 가져오기
```

위의 변수를 수정하여 테마 색상을 변경하십시오.

### 사이트 구성

아래는 프로젝트 `_config.yml`에서 변경할 수 있는 몇 가지 속성입니다. 자세한 내용은 [문서](docs/settings.md#settings)를 참조하십시오.

```yaml
# 사이트 설정
name: Jekflix # 사이트 이름
title: Jekflix | Jekyll을 위한 블로그 테마 # 사이트 제목
description: Jekflix는 Netflix에서 영감을 받아 Thiago Rossener가 만든 Jekyll 템플릿입니다. # 사이트 설명
tags:
  - 블로그
  - 템플릿
  - jekyll
  - 테마
  - netlify
email: youremail@xyz.com # 연락처 이메일 주소
disqus_username: disqus_username # Disqus 사용자 이름 설정
show_hero: true # 히어로 섹션 표시 여부
menu:
  - title: 홈 # 메뉴 항목 이름
    url: / # 메뉴 항목 URL
  - title: 소개 # 메뉴 항목 이름
    url: /about # 메뉴 항목 URL
  - title: 연락처 # 메뉴 항목 이름
    url: /contact # 메뉴 항목 URL
  - title: 피드 # 메뉴 항목 이름
    url: /feed.xml # 메뉴 항목 URL

# 소셜 미디어 설정
# 필요하지 않은 항목은 제거하십시오
github_username: github_username # GitHub 사용자 이름 설정
facebook_username: facebook_username # Facebook 사용자 이름 설정
twitter_username: twitter_username # Twitter 사용자 이름 설정
instagram_username: instagram_username # Instagram 사용자 이름 설정
linkedin_username: linkedin_username # LinkedIn 사용자 이름 설정
medium_username: medium_username # Medium 사용자 이름 설정

# 게시물 설정
show_time_bar: true # 읽기 진행률 표시줄 표시 여부
show_modal_on_exit: false # 페이지 종료 시 모달 표시 여부
show_modal_on_finish_post: true # 게시물 끝날 때 모달 표시 여부
two_columns_layout: true # 두 개의 열 레이아웃 사용 여부

# 고급 설정
baseurl: "" # 사이트의 하위 경로, 예: /blog
url: "" # 사이트의 기본 호스트 이름 및 프로토콜
google_analytics: "UA-XXXXXXXX-X" # 구글 애널리틱스 코드 설정
language: "en" # 사이트 언어 설정
categories_folder: category # 카테고리 폴더 이름 설정
sent_message_url: "/contact/message-sent/" # 메시지 전송 후 리디렉션 URL

# 빌드 설정
markdown: kramdown # Markdown 파서 설정
highlighter: rouge # 코드 하이라이터 설정
permalink: /:title/ # 게시물의 고유 경로 설정
collections:
  authors:
    output: true # 작성자 정보 출력 여부
paginate_path: "/page/:num/" # 페이지네이션 경로 설정
show_get_theme_btn: true # 테마 받기 버튼 표시 여부
use_logo: false # 로고 사용 여부

# 콘텐츠 페이지네이터
paginate_content:
  enabled: true # 콘텐츠 페이지네이션 활성화 여부
  debug: false # 디버그 모드 설정
  collections:
    - posts # 페이지네이션할 컬렉션 목록
  auto: false # 자동 페이지네이션 사용 여부
  separator: "--page-break--" # 페이지 나누기 구분자 설정
  permalink: "/:num/" # 페이지 고유 경로 설정
  seo_canonical: true # SEO 캐노니컬 설정
  properties:
    part:
      is_generated: true
    last:
      is_generated: true
    single:
      is_generated: true

# SASS
sass:
  style: compressed # SASS 스타일 설정

# 플러그인
plugins:
  - jekyll-paginate # 페이지네이션 플러그인
  - jekyll-paginate-content # 콘텐츠 페이지네이션 플러그인
```

## 설정

이 저장소를 클론하는 경우, 다음 지침을 따르십시오:

- [환경 설정](docs/setup.md#environment)
- [템플릿 설치](docs/setup.md#installing-template)
- [로컬 실행](docs/setup.md#running-local)

### 커스터마이징

레이아웃, 제목, 소셜 미디어 등을 커스터마이징하려면 [설정 문서](docs/settings.md#settings)를 참조하십시오.

### 테마

테마 색상은 `src/yml/theme.yml` 파일을 수정한 후 터미널에서 `gulp build`를 실행하여 쉽게 변경할 수 있습니다.

#### GitHub 페이지

GitHub 페이지에 웹사이트를 배포할 때 Gulp를 실행할 수 없는 문제가 있습니다. 따라서 테마 색상을 변경한 후 `gulp build`를 로컬에서 실행한 다음 변경 사항을 저장소에 푸시해야 합니다. 다른 방법은 없습니다.

웹사이트가 배포되었을 때 어떻게 보일지 확인하려면 `bundle exec jekyll serve`를 로컬에서 실행하고 `http://127.0.0.1:4000/`에 접속하십시오.

## 게시물

게시물을 작성하려면 [Front Matter 속성](docs/post.md#front-matter-properties)을 사용하십시오.

> **참고:** 이 저장소를 클론하는 경우, 게시물을 자동으로 생성하는 [스크립트](docs/post.md#creating-a-post)를 사용할 수 있습니다.

## 질문이 있으신가요?

[GitHub 이슈](https://github.com/thiagorossener/jekflix-template/issues/new)를 등록해 주세요.

## 작성자

[Thiago Rossener](https://rossener.com/)

제 작업이 마음에 드시나요? 커피 한 잔 사 주세요!

<a href="https://www.buymeacoffee.com/thiagorossener" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" alt="Buy Me A Coffee" style="height: 60px !important;width: 217px !important;" ></a>

## 라이선스

*Jekflix 템플릿*은 MIT 라이선스 하에 제공됩니다. 자세한 내용은 [LICENSE](https://github.com/thiagorossener/jekflix-template/blob/master/LICENSE) 파일을 참조하십시오.
