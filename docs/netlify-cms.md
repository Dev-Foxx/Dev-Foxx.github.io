# Netlify CMS

*Jekflix*는 Netlify CMS 통합을 지원하므로, 코드를 전혀 건드리지 않고도 게시물, 작성자, 카테고리, 테마 등을 생성/편집할 수 있습니다!

하지만, **이 기능은 저장소를 복제한 경우에만 사용할 수 있습니다**. 만약 `gem`을 사용 중이라면, Netlify CMS를 직접 설정해야 합니다.

## Netlify로 배포하기

Netlify [문서](https://www.netlify.com/docs/continuous-deployment/)를 사용하여 *지속적 배포(Continuous Deployment)*를 설정하세요.

**Build command(빌드 명령어)**를 설정할 때, `gulp build`로 변경합니다. 사이트를 이미 배포했으나 이 작업을 잊었다면 아래 단계를 따라 수정하세요:

1. 상단 메뉴에서 **Deploys**를 선택합니다.
2. **Continuous Deployment > Build Settings**에서 **Edit settings**를 클릭합니다.
3. **Build command**를 `gulp build`로 변경합니다.

이제 매번 새 커밋을 푸시할 때마다 프로젝트가 빌드되고 배포됩니다.

## Netlify CMS 통합하기

Netlify를 통해 웹사이트 배포를 성공적으로 마쳤다면, [Enable Identity and Git Gateway](https://www.netlifycms.org/docs/add-to-your-site/#enable-identity-and-git-gateway) 가이드를 따라 CMS에 접근할 수 있도록 설정하세요.

몇 가지 중요한 사항:

1. 로컬에서 `localhost:3000/admin` 또는 `yourdomain.com/admin`을 통해 CMS에 접근할 수 있습니다.
2. CMS에서 사용 가능한 데이터는 **항상** 저장소에서 가져옵니다. 즉, 로컬에서 작업 중이더라도, 로컬 변경 사항은 GitHub에 푸시될 때까지 CMS에서 반영되지 않습니다.
3. CMS를 통해 *게시(publish)*된 모든 변경 사항은 자동으로 프로덕션에 배포되므로, 게시할 때 주의해야 합니다.
4. CMS는 데이터를 *초안(draft)*으로 저장할 수도 있으므로, 게시하기 전까지는 프로덕션에 반영되지 않습니다. 🙂

다음은 CMS의 스크린샷들입니다:

![Netlify CMS 게시물 목록 스크린샷](https://res.cloudinary.com/dm7h7e8xj/image/upload/v1566479287/netlify-page-1_a0qezm.jpg)

![Netlify CMS 게시물 편집 스크린샷](https://res.cloudinary.com/dm7h7e8xj/image/upload/v1566479287/netlify-page-2_aupygb.jpg)

![Netlify CMS 워크플로우 스크린샷](https://res.cloudinary.com/dm7h7e8xj/image/upload/v1566479287/netlify-page-3_bj5sks.jpg)

![Netlify CMS 사이트 설정 스크린샷](https://res.cloudinary.com/dm7h7e8xj/image/upload/v1566479287/netlify-page-4_ycfqdp.jpg)

![Netlify CMS 테마 설정 스크린샷](https://res.cloudinary.com/dm7h7e8xj/image/upload/v1566479287/netlify-page-5_k6dan9.jpg)

