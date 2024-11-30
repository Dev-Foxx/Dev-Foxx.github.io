# 설정

## 환경 설정

시작하기 전에 [Ruby](https://www.ruby-lang.org/en/documentation/installation/)와 [NodeJS](https://nodejs.org/)가 설치되어 있는지 확인하십시오.

그런 다음 Jekyll을 설치하십시오:

```bash
$ gem install jekyll
```

그리고 Gulp 클라이언트를 설치하십시오:

```bash
$ npm install gulp-cli -g
```

## 템플릿 설치

1. [Jekflix 템플릿](https://github.com/thiagorossener/jekflix-template/fork)을 포크하십시오.
2. 방금 포크한 저장소를 클론합니다:
   ```bash
   $ git clone https://github.com/<your-github-username>/jekflix-template.git
   ```
3. 로컬 프로젝트에 접근합니다:
   ```bash
   $ cd path/to/jekyll-template
   ```
4. npm 패키지를 설치합니다:
   ```bash
   $ npm install
   ```
5. Ruby 종속성을 설치합니다:
   ```bash
   $ bundle install
   ```
6. Jekyll을 빌드합니다:
   ```bash
   $ bundle exec jekyll build
   ```
7. 그런 다음 Gulp를 실행합니다:
   ```bash
   $ gulp
   ```

## 로컬 실행

위의 단계를 완료한 후, Jekyll을 로컬에서 실행하려면 Gulp를 실행하십시오:

```bash
$ gulp
```

## 커스터마이징

*Jekflix 템플릿*은 여러 설정을 통해 사이트를 개인화할 수 있습니다. 자세한 내용은 [문서](settings.md#settings)를 참조하십시오.

고급 테마 커스터마이징을 위해 `_sass` 디렉토리에서 스타일 파일을 확인하십시오.

## 번역

테마 전체의 텍스트를 번역하려면 `src/yml` 디렉토리에 `translations.yml` 파일을 만들고 아래 설정을 추가하십시오.

> **참고:** `gem`을 사용하는 경우, 그냥 `_config.yml`에 추가하십시오.

```yaml
translations:
  text:
    new_post: "새 게시물"
    see_also: "또한 보세요"
    search: "검색"
    author: "작성자"
    share: "공유"
    comments: "댓글"
  button:
    read_now: "지금 읽기"
    share_on_twitter: "트위터에서 공유하기"
    share_on_facebook: "페이스북에서 공유하기"
  pagination:
    page: "페이지"
    of: "의"
    next_page: "다음 페이지"
    next_post: "이전 페이지"
  recommendation:
    text: "다음에 읽을 만한 것은 없을까요?"
    back_btn: "맨 위로 돌아가기"
  error_404:
    title: "페이지를 찾을 수 없습니다 :("
    message: "죄송합니다. 찾으시는 페이지를 찾을 수 없습니다."
    image_alt: "404 - 페이지를 찾을 수 없음"
  contact:
    title: "저에게 이야기하세요"
    subject: "새 연락!"
    submit_btn: "보내기"
    placeholders:
      name: "이름"
      email: "이메일"
      message: "메시지"
    errors:
      locale: "en"
      empty_name: "이름은 필수입니다"
      empty_email: "이메일은 필수입니다"
      invalid_email: "이메일이 잘못되었습니다"
      empty_message: "메시지는 필수입니다"
    after_send:
      title: "메시지가 전송되었습니다!"
      message: "메시지를 보내주셔서 감사합니다. 가능한 빨리 답변드리겠습니다."
