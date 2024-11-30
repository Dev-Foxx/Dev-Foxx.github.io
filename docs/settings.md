# 설정

웹사이트의 테마 색상, 레이아웃, 제목 등을 커스터마이징하십시오. 설정 파일은 `src/yml`에 있습니다.

## 사이트 설정

일반 설정은 [`src/yml/site.yml`](https://github.com/thiagorossener/jekflix-template/blob/master/src/yml/site.yml)에서 찾을 수 있습니다.

> **중요:** 리포를 클론한 경우에만 해당됩니다. `gem`을 사용하는 경우 이러한 속성을 `_config.yml`에서 수정하십시오.

#### `name`

타입: *문자열 (string)*

웹사이트 이름은 헤더를 포함한 여러 곳에 나타납니다.

예시:

```yaml
# site.yml
name: Jekflix
```

#### `title`

타입: *문자열 (string)*

웹사이트 제목은 SEO 목적으로 사용되며 홈페이지 제목을 설정합니다.

예시:

```yaml
# site.yml
title: Jekflix | Jekyll을 위한 블로그 테마
```

#### `description`

타입: *문자열 (string)*

웹사이트 설명은 SEO 목적으로만 사용됩니다.

예시:

```yaml
# site.yml
description: Jekflix는 Netflix에서 영감을 받아 Thiago Rossener가 만든 Jekyll 템플릿입니다.
```

#### `tags`

타입: *리스트 (list)*

웹사이트 태그는 SEO를 위한 키워드로 사용됩니다.

예시:

```yaml
# site.yml
tags:
  - 블로그
  - 템플릿
  - jekyll
  - 테마
  - netlify
```

#### `email`

타입: *문자열 (string)*

이메일은 레거시 [Formspree](https://formspree.io/) 폼을 사용하는 연락처 페이지에 사용됩니다.

이 항목과 `formspree_form_id`를 비워두면 연락처 페이지가 표시되지 않습니다.

> **경고:** v4에서는 이 기능이 더 이상 사용되지 않을 예정입니다.

예시:

```yaml
# site.yml
email: youremail@xyz.com
```

#### `formspree_form_id `

타입: *문자열 (string)*

[Formspree](https://formspree.io/) ID는 연락처 페이지에 사용됩니다.

이 항목과 `email`을 비워두면 연락처 페이지가 표시되지 않습니다.

예시:

```yaml
# site.yml
formspree_form_id: your_formspree_form_id
```

#### `disqus_username`

타입: *문자열 (string)*

[Disqus](https://disqus.com) 사용자 이름을 설정하여 게시물에 댓글을 추가할 수 있습니다. 댓글을 활성화하지 않으려면 비워 두십시오.

예시:

```yaml
# site.yml
disqus_username: disqus_username
```

#### `show_hero`

타입: *불리언 (boolean)*

홈페이지에 히어로 섹션을 표시하거나 숨깁니다. `true` 또는 `false` 값을 가집니다.

히어로가 있는 예시:

```yaml
# site.yml
show_hero: true
```

히어로가 없는 예시:

```yaml
# site.yml
show_hero: false
```

#### `paginate`

타입: *정수 (integer)*

홈페이지에 페이지네이션을 추가합니다.

페이지당 표시할 게시물 수를 설정합니다. 페이지네이션을 원하지 않으면 비워 두십시오.

```yaml
# site.yml
paginate: 12
```

## 소셜 설정

소셜 설정은 [`src/yml/social.yml`](https://github.com/thiagorossener/jekflix-template/blob/master/src/yml/social.yml)에서 찾을 수 있습니다. 소셜 미디어 아이콘은 모든 페이지의 푸터에 나타납니다.

> **중요:** 리포를 클론한 경우에만 해당됩니다. `gem`을 사용하는 경우 이러한 속성을 `_config.yml`에서 수정하십시오.

#### `github_username`

타입: *문자열 (string)*

웹사이트의 GitHub 사용자 이름을 설정합니다.

```yaml
# social.yml
github_username: github_username
```

#### `facebook_username`

타입: *문자열 (string)*

웹사이트의 Facebook 사용자 이름을 설정합니다.

```yaml
# social.yml
facebook_username: facebook_username
```

#### `twitter_username`

타입: *문자열 (string)*

웹사이트의 Twitter 사용자 이름을 설정합니다.

```yaml
# social.yml
twitter_username: twitter_username
```

#### `instagram_username`

타입: *문자열 (string)*

웹사이트의 Instagram 사용자 이름을 설정합니다.

```yaml
# social.yml
instagram_username: instagram_username
```

#### `linkedin_username`

타입: *문자열 (string)*

웹사이트의 LinkedIn 사용자 이름을 설정합니다.

```yaml
# social.yml
linkedin_username: linkedin_username
```

#### `medium_username`

타입: *문자열 (string)*

웹사이트의 Medium 사용자 이름을 설정합니다.

```yaml
# social.yml
medium_username: medium_username
```

## 테마 설정

테마 설정은 [`src/yml/theme.yml`](https://github.com/thiagorossener/jekflix-template/blob/master/src/yml/theme.yml)에 있습니다. 이 파일만 변경하고 `gulp build`를 실행하면 됩니다.

> **중요:** 리포를 클론한 경우에만 해당됩니다. `gem`을 사용하는 경우 [이 지침](https://github.com/thiagorossener/jekflix-template#theme-colors)을 따르십시오.

### GitHub 페이지

GitHub 페이지에 웹사이트를 배포할 때 Gulp를 실행할 수 없는 문제가 있습니다. 따라서 테마 색상을 변경한 후 `gulp build`를 로컬에서 실행한 다음 변경 사항을 저장소에 푸시해야 합니다. 다른 방법은 없습니다.

웹사이트가 배포되었을 때 어떻게 보일지 확인하려면 `bundle exec jekyll serve`를 실행하고 `http://127.0.0.1:4000/`에 접속하십시오.

#### `themeColor`

타입: *16진수 색상 코드 (hexadecimal)*

기본값: ![#ff0a16](https://placehold.it/15/ff0a16/000000?text=+) `#FF0A16`

링크, 아이콘 및 일부 사용자 정의 요소에 사용되는 색상입니다.

```yaml
# theme.yml
themeColor: "#ff0a16"
```

#### `primaryDark`

타입: *16진수 색상 코드 (hexadecimal)*

기본값: ![#141414](https://placehold.it/15/141414/000000?text=+) `#141414`

어두운 배경과 일부 텍스트에 사용되는 색상입니다.

```yaml
# theme.yml
primaryDark: "#141414"
```

#### `accentDark`

타입: *16진수 색상 코드 (hexadecimal)*

기본값: ![#ffffff](https://placehold.it/15/ffffff/000000?text=+) `#FFFFFF`

밝은 배경 및 어두운 배경과 대조되는 색상입니다.

```yaml
# theme.yml
accentDark: "#ffffff"
```

#### `lightGray`

타입: *16진수 색상 코드 (hexadecimal)*

기본값: ![#f2f2f2](https://placehold.it/15/f2f2f2/000000?text=+) `#F2F2F2`

테두리, 밝은 배경과의 대조, 일부 링크 및 부제목에 사용되는 색상입니다.

```yaml
# theme.yml
lightGray: "#f2f2f2"
```

#### `texts`

타입: *16진수 색상 코드 (hexadecimal)*

기본값: ![#333333](https://placehold.it/15/333333/000000?text=+) `#333333`

전체 텍스트에 사용되는 색상입니다.

```yaml
# theme.yml
texts: "#333333"
```

## 게시물 설정

게시물 설정은 [`src/yml/posts.yml`](https://github.com/thiagorossener/jekflix-template/blob/master/src/yml/posts.yml)에서 찾을 수 있습니다.

> **중요:** 리포를 클론한 경우에만 해당됩니다. `gem`을 사용하는 경우 이러한 속성을 `_config.yml`에서 수정하십시오.

#### `show_time_bar`

타입: *불리언 (boolean)*

읽기 진행률 표시줄을 표시하거나 숨깁니다. `true` 또는 `false` 값을 가집니다.

```yaml
# posts.yml
show_time_bar: true
```

#### `show_modal_on_exit`

타입: *불리언 (boolean)*

방문자가 페이지를 떠날 때 추천 모달을 표시하거나 숨깁니다. `true` 또는 `false` 값을 가집니다.

```yaml
# posts.yml
show_modal_on_exit: false
```

#### `show_modal_on_finish_post`

타입: *불리언 (boolean)*

방문자가 게시물 끝에 도달했을 때 추천 모달을 표시하거나 숨깁니다. `true` 또는 `false` 값을 가집니다.

```yaml
# posts.yml
show_modal_on_finish_post: false
```

#### `two_columns_layout`

타입: *불리언 (boolean)*

게시물 레이아웃을 한 열 또는 두 열로 전환합니다. `true` 또는 `false` 값을 가집니다.

두 열의 예시:

```yaml
# posts.yml
two_columns_layout: true
```

한 열의 예시:

```yaml
# posts.yml
two_columns_layout: false
```

## 고급 설정

고급 설정은 [`src/yml/advanced.yml`](https://github.com/thiagorossener/jekflix-template/blob/master/src/yml/advanced.yml)에서 찾을 수 있습니다.

> **중요:** 리포를 클론한 경우에만 해당됩니다. `gem`을 사용하는 경우 이러한 속성을 `_config.yml`에서 수정하십시오.

#### `baseurl`

타입: *문자열 (string)*

사이트의 하위 경로를 설정합니다. 예: `/blog`.

```yaml
# advanced.yml
baseurl: ""
```

#### `url`

타입: *문자열 (string)*

사이트의 기본 호스트 이름 및 프로토콜을 설정합니다. 예: `https://rossener.com`

```yaml
# advanced.yml
url: ""
```

#### `google_analytics`

타입: *문자열 (string)*

구글 애널리틱스 [추적 ID](https://www.youtube.com/watch?v=Mtzl4tkVdbI)를 설정합니다.

```yaml
# advanced.yml
google_analytics: "UA-XXXXXXXX-X"
```

#### `language`

타입: *문자열 (string)*

웹사이트 언어를 설정합니다. SEO 목적으로 사용됩니다 (예: `pt-BR`, `en`, `es`, `fr`)

```yaml
# advanced.yml
language: "en"
