# 기능

*Jekflix*는 콘텐츠 생성/편집/공유를 돕고 방문자에게 훌륭한 경험을 제공하기 위한 다양한 기능을 제공합니다.

- [실시간 검색](features.md#live-search)
- [예상 읽기 시간](features.md#estimated-reading-time)
- [읽기 진행 바](features.md#reading-progress-bar) *(선택사항)*
- ["새 게시물" 태그](features.md#new-post-tag)
- [요구 시 이미지 로드](features.md#load-images-on-demand)
- [푸시 메뉴](features.md#push-menu)
- [SVG 아이콘](features.md#svg-icons)
- [게시물 생성용 셸 스크립트](features.md#shell-script-to-create-posts)
- [태그 페이지](features.md#tags-page)
- [소개 페이지](features.md#about-page)
- [문의 페이지](features.md#contact-page)
- [404 오류 페이지](features.md#404-error-page)
- [RSS 피드](features.md#feed-rss)
- [Disqus](features.md#disqus) *(선택사항)*
- [추천 게시물](features.md#featured-post) *(선택사항)*
- [홈 페이지 페이지네이션](features.md#home-page-pagination) *(선택사항)*
- [게시물 사이드바](features.md#posts-sidebar) *(선택사항)*
- [페이지네이션된 게시물](features.md#paginated-posts) *(선택사항)*
- ["떠나기 전에" 모달](features.md#before-you-go-modal) *(선택사항)*
- [게시물 추천](features.md#post-recommendation)
- [Netlify CMS 준비됨](features.md#netlify-cms-ready)
- [번역](setup.md#translations)
- [수학 표현식](features.md#math-expressions) *(선택사항)*

## 실시간 검색

템플릿의 오른쪽 상단에 위치한 검색 컴포넌트는 게시물 제목, 카테고리, 태그를 검색합니다. 이는 정적 웹사이트에 적합한 간단한 검색 기능입니다.

![검색 상자 스크린샷](https://res.cloudinary.com/dm7h7e8xj/image/upload/v1566426001/search-screenshot_sc5edu.jpg)

## 예상 읽기 시간

각 게시물은 제목 위에 예상 읽기 시간을 표시합니다. 이는 평균 독서 속도를 기준으로 계산됩니다.

![예상 읽기 시간 스크린샷](https://res.cloudinary.com/dm7h7e8xj/image/upload/v1566426097/minutes-to-read-screenshot_akvu69.jpg)

## 읽기 진행 바

*(선택사항)*

페이지 내 읽기 시간과 스크롤 위치를 기준으로 읽기 진행 바를 표시합니다.

![읽기 진행 바 스크린샷](https://res.cloudinary.com/dm7h7e8xj/image/upload/v1566425470/progress-bar-screenshot_gem7xb.jpg)

읽기 진행 바를 표시하거나 숨기려면 [문서](settings.md#show_time_bar)를 참고하십시오.

## "새 게시물" 태그

현재 날짜로부터 최대 7일 이내에 게시된 게시물에는 홈 페이지에서 "새 게시물" 태그가 붙습니다.

![새 게시물 태그 스크린샷](https://res.cloudinary.com/dm7h7e8xj/image/upload/v1566425920/new-post-tag-screenshot_nyuycr.jpg)

## 요구 시 이미지 로드

홈 페이지 성능을 향상시키기 위해 초기에는 화면 상단의 게시물만 로드됩니다. 다음 게시물은 아래로 스크롤할 때 필요에 따라 로드됩니다.

![로드 중 스크린샷](https://res.cloudinary.com/dm7h7e8xj/image/upload/v1566426573/loading-screenshot_akchmx.jpg)

## 푸시 메뉴

템플릿 메뉴는 기본적으로 숨겨져 있으며, 열릴 때 콘텐츠를 오른쪽으로 밀어냅니다.

![메뉴 스크린샷](https://res.cloudinary.com/dm7h7e8xj/image/upload/v1566426941/menu-screenshot_qsoz1z.jpg)

## SVG 아이콘

템플릿에서 사용된 모든 아이콘은 SVG 형식으로, 모든 해상도에서 선명한 모습을 제공합니다.

![템플릿 아이콘](https://res.cloudinary.com/dm7h7e8xj/image/upload/v1566427250/icons-screenshot_uhk80e.jpg)

## 게시물 생성용 셸 스크립트

[initpost.sh](https://github.com/thiagorossener/jekflix-template/blob/master/initpost.sh)라는 스크립트가 제공되어 명령줄에서 게시물을 쉽게 생성할 수 있습니다.

프로젝트 디렉토리에서 다음 명령을 실행하세요:

```
$ ./initpost.sh -c "새 게시물 제목"
```

## 태그 페이지

모든 태그가 한 페이지에 모여 방문자가 태그별로 블로그 게시물을 찾을 수 있도록 합니다.

![태그 페이지 스크린샷](https://res.cloudinary.com/dm7h7e8xj/image/upload/v1566430436/tags-page-screenshot_eeyyt8.jpg)

[태그 페이지를 확인하세요](https://jekflix.rossener.com/tags/).

## 소개 페이지

소개 페이지가 기본으로 제공되며, 언제든 삭제할 수 있습니다.

![소개 페이지 스크린샷](https://res.cloudinary.com/dm7h7e8xj/image/upload/v1566430703/about-page-screenshot_rgchze.jpg)

[소개 페이지를 확인하세요](https://jekflix.rossener.com/about/).

## 문의 페이지

Vue로 작성된 문의 양식이 템플릿에 포함되어 있어 처음부터 작성할 필요가 없습니다.

![문의 페이지 스크린샷](https://res.cloudinary.com/dm7h7e8xj/image/upload/v1566476192/contact-page-screenshot_efux2y.jpg)

[문의 페이지를 확인하세요](https://jekflix.rossener.com/contact/).

## 404 오류 페이지

템플릿은 404 오류도 기본적으로 처리합니다.

![404 페이지 스크린샷](https://res.cloudinary.com/dm7h7e8xj/image/upload/v1566476323/404-page-screenshot_qiieyi.jpg)

[404 페이지를 확인하세요](https://jekflix.rossener.com/404/).

## RSS 피드

빌드 시마다 자동으로 피드 파일이 생성됩니다.

[RSS 피드 샘플을 확인하세요](https://jekflix.rossener.com/feed.xml).

## Disqus

*(선택사항)*

Jekflix 템플릿은 Disqus 플러그인을 구현하여 방문자가 게시물에 댓글을 남길 수 있습니다.

구성 방법은 [문서](settings.md#disqus_username)를 참고하세요.

## 추천 게시물

*(선택사항)*

이 버전 2.0에서는 넷플릭스가 영화와 함께 하는 것처럼 홈 페이지에 히어로 락업이 추가되었습니다.

이 기능을 켜거나 끄려면 [문서](settings.md#show_hero)를 참고하세요.

![히어로가 있는 페이지 스크린샷](https://res.cloudinary.com/dm7h7e8xj/image/upload/v1566477681/page-with-hero-screenshot_ixyjzp.jpg)

## 홈 페이지 페이지네이션

*(선택사항)*

홈 페이지에서 게시물을 표시하는 두 가지 옵션이 있습니다. 첫 번째는 스크롤할 때 새 게시물을 로드하는 것이고, 두 번째는 페이지네이션을 추가하는 것입니다.

페이지네이션을 추가하려면 [문서](settings.md#paginate)를 참고하세요.

## 게시물 사이드바

*(선택사항)*

많은 분들이 요청한 대로, Jekflix 템플릿 2.0에는 게시물에 선택적으로 사이드바를 추가할 수 있는 기능이 포함되었습니다.

사이드바를 표시하거나 숨기려면 [문서](settings.md#two_columns_layout)를 참고하세요.

![두 개의 열이 있는 게시물 스크린샷](https://res.cloudinary.com/dm7h7e8xj/image/upload/v1566476793/two-columns-screenshot_phumrl.jpg)

## 페이지네이션된 게시물

*(선택사항)*

게시물을 여러 페이지로 나눠 광고 조회수를 높일 수도 있습니다.

게시물을 여러 페이지로 나누는 방법은 [문서](post.md#paginate)를 참고하세요.

![페이지네이션된 페이지 스크린샷](https://res.cloudinary.com/dm7h7e8xj/image/upload/v1566430021/paginated-page-screenshot_zx4xjn.jpg)

## "떠나기 전에" 모달

*(선택사항)*

방문자가 페이지를 떠나기 전에 또는 게시물 끝에 도달했을 때 게시물 추천을 보여줌으로써 방문자가 콘텐츠에 관심을 계속 가질 수 있도록 할 수 있습니다.

자세한 내용은 [문서](settings.md#show_modal_on_exit)를 참고하세요.

![모달 스크린샷](https://res.cloudinary.com/dm7h7e8xj/image/upload/v1566478245/before-you-go-screenshot_prrplk.jpg)

## 게시물 추천

기본적으로 모든 게시물은 방문자가 글 끝에 도달하면 게시물 추천을 표시합니다.

![추천 스크린샷](https://res.cloudinary.com/dm7h7e8xj/image/upload/v1566478555/recommendation-screenshot_wzhchs.jpg)

이 기능은 넷플릭스에서 영화나 시리즈 에피소드를 마칠 때 나오는 추천과 유사한 것을 목표로 합니다.

## 수학 표현식

*(선택사항)*

*Jekflix 템플릿 3.1.0*은 이제 **[@XieGuochao](https://github.com/XieGuochao)** 덕분에 [MathJax](https://www.mathjax.org/) 라이브러리를 통해 수학 표현식을 지원합니다.

2단계만 필요합니다:

1. 게시물에 `math: true`를 설정합니다.
2. _MathJax_의 $\LaTeX$ 문법을 사용합니다.

예를 들어, `$\sum_{i=1}{10} = 55$`는 다음과 같이 렌더링됩니다: <img src="https://res.cloudinary.com/dm7h7e8xj/image/upload/c_scale,q_78,w_270/v1585835744/Screen_Shot_2020-04-02_at_10.55.24_uafb07.jpg" width="135">.

## Netlify CMS 준비됨

가장 최신 버전의 *Jekflix 템플릿 2.0.0*에는 Netlify CMS 통합이 추가되었습니다.

Netlify CMS를 사용하면 편집기를 통해 게시물을 생성/편집하고 워크플로우 패널에 접근하며 클릭 몇 번으로 블로그의 모든 측면을 변경할 수 있습니다.

Netlify CMS를 사용하려면 몇 가지 단계를 거쳐야 합니다. 자세한 내용은 [문서](netlify-cms.md#netlify-cms)를 참고하세요.

다음은 몇 가지 스크린샷입니다:

![Netlify CMS 게시물 목록 스크린샷](https://res.cloudinary.com/dm7h7e8xj/image/upload/v1566479287/netlify-page-1_a0qezm.jpg)

![Netlify CMS 게시물 편집 스크린샷](https://res.cloudinary.com/dm7h7e8xj/image/upload/v1566479287/netlify-page-2_aupygb.jpg)

![Netlify CMS 워크플로우 스크린샷](https://res.cloudinary.com/dm7h7e8xj/image/upload/v1566479287/netlify-page-3_bj5sks.jpg)

![Netlify CMS 사이트 설정 스크린샷](https://res.cloudinary.com/dm7h7e8xj/image/upload/v1566479287/netlify-page-4_ycfqdp.jpg)

![Netlify CMS 테마 설정 스크린샷](https://res.cloudinary.com/dm7h7e8xj/image/upload/v1566479287/netlify-page-5_k6dan9.jpg)
