# 게시물 설정

## 게시물 생성하기

리포를 클론한 경우 `initpost.sh` 스크립트를 사용하여 새 게시물을 생성할 수 있습니다 (`gem`에서는 사용할 수 없습니다).

프로젝트 디렉토리에서 다음 명령어를 실행하십시오:

```
./initpost.sh -c "Your Post Title"
```

새 파일은 `_posts`에 `YYYY-MM-DD-your-post-title.md` 형식으로 생성됩니다.

## Front Matter 속성

Front Matter가 무엇인지 모른다면 Jekyll [문서](https://jekyllrb.com/docs/front-matter/)를 참고하십시오.

*Jekflix* 게시물 파일은 다음과 같습니다:

```yaml
# _posts/2010-01-01-welcome-to-the-desert-of-the-real.md
---
date: 2019-05-16 23:48:05
layout: post
title: Welcome to the desert of the real
subtitle: Lorem ipsum dolor sit amet, consectetur adipisicing elit.
description: >-
  Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
  tempor incididunt ut labore et dolore magna aliqua.
image: https://res.cloudinary.com/dm7h7e8xj/image/upload/v1559821647/theme6_qeeojf.jpg
optimized_image: https://res.cloudinary.com/dm7h7e8xj/image/upload/c_scale,w_380/v1559821647/theme6_qeeojf.jpg
category: blog
tags:
  - welcome
  - blog
author: thiagorossener
paginate: true
---

bla bla bla
```

아래는 템플릿의 모든 Front Matter 속성을 설명한 목록입니다:

#### `date`

타입: *날짜 시간 (datetime)*

게시물 게시 날짜입니다. 형식: `YYYY-MM-DD hh:mm:ss`

예시:

```yaml
# _posts/2019-08-22-example.md
---
...
date: 2019-05-16 23:48:05
...
---
```

#### `layout`

타입: *문자열 (string)*

사용할 레이아웃 파일입니다. 템플릿에는 게시물에 대해 유효한 레이아웃이 `post` 하나뿐입니다.

```yaml
# _posts/2019-08-22-example.md
---
...
layout: post
...
---
```

#### `title`

타입: *문자열 (string)*

게시물 제목입니다.

예시:

```yaml
# _posts/2019-08-22-example.md
---
...
title: Welcome to the desert of the real
...
---
```

#### `subtitle`

*(선택사항)*

타입: *문자열 (string)*

게시물 부제목입니다. 제목 아래에 표시됩니다.

예시:

```yaml
# _posts/2019-08-22-example.md
---
...
subtitle: Lorem ipsum dolor sit amet, consectetur adipisicing elit.
...
---
```

#### `description`

타입: *문자열 (string)*

게시물 설명입니다. 홈 및 카테고리 페이지에서, SEO를 위한 메타 설명 태그 및 소셜 미디어 공유에 사용됩니다.

예시:

```yaml
# _posts/2019-08-22-example.md
---
...
description: >-
  Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
  tempor incididunt ut labore et dolore magna aliqua.
...
---
```

#### `image`

타입: *URL*

추천 이미지입니다. 홈 및 카테고리 페이지와 소셜 미디어 공유에 사용됩니다.

**팁:** [Cloudinary](https://cloudinary.com)와 같은 미디어 서버를 사용하여 웹사이트에 이미지를 제공하세요.

*참고: 추천 이미지 해상도는 760x399입니다*

예시:

```yaml
# _posts/2019-08-22-example.md
---
...
image: https://res.cloudinary.com/dm7h7e8xj/image/upload/v1559821647/theme6_qeeojf.jpg
...
---
```

#### `optimized_image`

*(선택사항)*

타입: *URL*

최적화된 추천 이미지입니다. 홈 및 카테고리 페이지에서 더 빠르게 로드되도록 작은 이미지를 설정합니다.

`optimized_image`가 설정되지 않은 경우, 페이지는 `image` 속성에 있는 이미지를 표시합니다.

*참고: 최적화된 이미지 해상도는 380x200입니다*

예시:

```yaml
# _posts/2019-08-22-example.md
---
...
optimized_image: https://res.cloudinary.com/dm7h7e8xj/image/upload/c_scale,w_380/v1559821647/theme6_qeeojf.jpg
...
---
```

#### `category`

타입: *문자열 (string)*

하나의 카테고리만 허용됩니다. 새로운 카테고리인 경우 `category` 디렉토리에 `<category>.md` 파일을 생성하십시오.

예시:

```yaml
# _posts/2019-08-22-example.md
---
...
category: blog
...
---
```

#### `tags`

타입: *리스트 (list)*

게시물 키워드 목록입니다. 홈, 카테고리 및 태그 페이지에서 사용되며, SEO 목적으로 메타 키워드로 사용됩니다.

예시:

```yaml
# _posts/2019-08-22-example.md
---
...
tags:
  - welcome
  - blog
...
---
```

#### `author`

*(선택사항)*

타입: *문자열 (string)*

게시물 작성자입니다. `_authors` 폴더에 있는 작성자 파일 이름을 설정하십시오.

새로운 작성자를 생성할 때마다 해당 폴더에 파일을 생성해야 합니다.

작성자가 없을 경우 비워 두십시오.

예시:

```yaml
# _posts/2019-08-22-example.md
---
...
author: thiagorossener
...
---
```

#### `paginate`

*(선택사항)*

타입: *불리언 (boolean)*

게시물을 페이지로 나누려면 `paginate` 속성을 `true`로 설정하고 나누고자 하는 위치에 구분 기호 `--page-break--`를 사용하십시오.

**참고:** 템플릿은 `jekyll-paginate-content`를 사용하며, 이는 [GitHub Pages에서 지원되지 않습니다](https://pages.github.com/versions/). 이 기능이 필요하다면 Netlify와 같은 다른 곳에 배포하십시오.

예시:

```yaml
# 2019-08-20-ten-skills-you-need-to-have-to-become-a-good-developer.md
---
...
paginate: true
...
---

Skill 1

--page-break--

Skill 2
```

다음과 같이 표시됩니다:

![페이지네이션된 페이지 스크린샷](https://res.cloudinary.com/dm7h7e8xj/image/upload/v1566430021/paginated-page-screenshot_zx4xjn.jpg)
