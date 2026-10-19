# may-policy 공개 준비 및 배포 가이드

작성일: 2026-10-19. 기존 mayclient의 한국어 초안을 HTML로 옮긴 것이며 법률 검토를 마친 최종 약관이 아니다.
기존 홈페이지, 기존 privacy 폴더, Jekyll 설정은 변경하지 않는다.
이 가이드는 Jekyll 기본 규칙상 배포에서 제외되는 밑줄 폴더에 둔다. 단, 공개 Git 저장소에서는 누구나 읽을 수 있으므로 비밀정보를 쓰지 않는다.

## 1. 파일과 최종 주소

저장소: https://github.com/kaoraswoo/kaoraswoo.github.io

| 파일 | 역할 | 배포 후 주소 |
|---|---|---|
| may-policy/index.html | 문서 안내 | https://kaoraswoo.github.io/may-policy/ |
| may-policy/terms.html | 이용약관 | https://kaoraswoo.github.io/may-policy/terms.html |
| may-policy/privacy.html | 개인정보처리방침 | https://kaoraswoo.github.io/may-policy/privacy.html |
| may-policy/policy.css | 위 세 페이지 전용 스타일 | 문서에서 상대 경로로 사용 |

새로운 저장소/서버/Cloudflare/CloudFront/DNS 설정은 필요 없다.
네 파일을 같은 폴더에 유지한다. 기존 루트 index.html이나 css 폴더에 덮어쓰지 않는다.
HTML에는 YAML front matter(맨 앞의 --- 구간)가 없으므로 Jekyll의 정적 파일로 복사된다.
기존 테마의 메뉴/분석 스크립트를 가져오지 않으며 별도 JavaScript, 외부 폰트, 광고, 입력 폼을 추가하지 않았다.
기존 홈페이지 메뉴에 링크를 추가하지 않아도 URL로 직접 접근할 수 있다.

**루트에 .nojekyll을 추가하면 안 된다. 기존 Jekyll 홈페이지 빌드를 꺼버릴 수 있다.**
현재 확인된 기본 브랜치는 master이고 _config.yml의 baseurl은 비어 있다.
GitHub Pages 실제 배포 설정은 로그인한 저장소 Settings에서 직접 확인해야 한다.

## 2. 공개 전 채울 항목

VS Code 등에서 may-policy 폴더를 열고 대괄호([ ])를 검색한다.
초안 배너와 노란 강조는 제거했다. 아직 대괄호로 남은 항목은 미확정 내용이므로 배포 전에 해결해야 한다.
민감한 실제 정보는 공개가 필요한 범위만 넣는다. 업무용 이메일을 권장한다.

다음 정보는 사용자 확인에 따라 이미 반영했다.

- 게임명: 시편섬광자
- 운영사: Again Studio (각 문서 첫 부분에서 이하 "회사"로 정의)
- 고객센터: admin@mapleagain.net (클릭하면 메일 작성)
- 시행일: 2026년 10월 19일
- 개인정보 문의 담당: Again Studio. 운영사 이름을 책임자 개인의 성명이라고 표시하지 않았다. 개인정보 보호책임자 또는 실제 고충 처리 부서의 적절한 공개 정보는 별도로 확정해야 한다.
- 공식 홈페이지 없음: 해당 표현을 제거하고 변경 공지 수단을 게임 내 공지로 정리. 실제 공지 운영 방식은 출시 전에 확인.
- 본문에서는 처음 정의한 "회사", "서비스"를 사용한다. 문서 제목/헤더/문의 하단은 식별을 위해 이름을 표시한다.

| 항목 | 채울 내용 / 판단 |
|---|---|
| [삭제 유예 기간 정책 확정 후 기재] | 실제 계정 삭제/유예/복구 가능 여부와 일치하도록 해당 문장 수정 |
| [이용 연령 기준 확정 후 기재] | 출시 연령 정책 및 아동 이용/법정대리인 동의 처리 확인 |
| [연동 기능 제공 시 기재] | 실제 제공 로그인 방식과 게임이 수신·저장하는 식별자만 명시 |
| [서버 호스팅, 분석 도구, 결제 대행 등 위탁처와 국외 이전 여부 확정 후 기재] | AWS, Unity, 스토어 등 실제 사용 내역 조사. 수탁자/제3자/독립 처리 주체를 임의로 동일하게 취급하지 말 것. 해당되는 처리 업무·항목·국가·보유기간·이전 조건 등 검토 |
| [광고 식별자, 분석 도구 사용 여부 확정 후 기재] | 실제 활성 SDK와 수집 설정 확인. 설치 여부와 실제 수집 여부를 구분 |

공개 항목의 기준은 개인정보 보호법 제30조 제1항 제7호의 책임자 성명 또는 고충 처리 부서 명칭과 연락처 등을 확인한다. 운영사명+이메일만으로 충족된다고 확정한 것은 아니다.
HTML 태그는 유지하고 텍스트만 고친다. 본문에 & 또는 <를 쓰려면 각각 &amp; 또는 &lt;로 작성한다.

### 원문을 유지했지만 별도 검토가 필요한 내용

단순히 대괄호만 채웠다고 완성되는 문서는 아니다. 원문의 단정적인 설명도 실제 구현/정책과 맞는지 확인한다.

- 약관: 게스트 복구 불가, 묵시적 변경 동의, 서비스 종료 공지, 유료 콘텐츠 사용 기간, 청약철회 제한, 미성년 결제, 계정 삭제와 면책 범위.
- 개인정보: 수집 항목, 보유 기간의 법적 근거/적용 대상, 탈퇴 직후 삭제와 별도 보관, 파기 시 백업/감사 로그 처리, 국외 이전, 아동 동의, 암호화 등 보호조치.
- 실제 저장하는 Unity 식별자와 Unity가 자체 수집하는 이메일을 구분한다. 게임이 이메일을 받는지 확인하지 않고 게임 수집 항목에 넣지 않는다.
- 서버가 계정을 삭제해도 Unity Player Account 자체가 삭제되는 것으로 안내하지 않는다. 반대로 Unity 계정을 삭제한다고 게임 데이터까지 자동 삭제되는 것도 아니다.
- GitHub Pages는 보안 목적으로 방문자 IP를 기록한다. 이 문서에 자체 추적 스크립트는 없지만 호스팅 사업자의 처리까지 없다는 뜻은 아니다.
- 국제 서비스/추가 언어가 필요하면 번역과 대상 국가에 대한 검토를 따로 진행한다.

공개 전 실제 정책에 맞춰 내용을 확정하고 적절한 법률/개인정보 검토를 받는다.

## 3. 원본 대비 변경 범위

원본:

- D:/project/mayclient/Assets/PatchResources/Text/Setting/Terms_ko.txt
- D:/project/mayclient/Assets/PatchResources/Text/Setting/Privacy_ko.txt

기존 조항과 문구를 기반으로 Unity 리치텍스트 제목/색상을 HTML 제목/안내상자로 변환했다.
사용자가 확정한 게임명/운영사/이메일을 반영하고, 개인정보 문서에도 서비스 명칭을 처음 정의했다.
없는 공식 홈페이지를 공지 수단으로 적은 부분은 게임 내 공지로 정리했으며 약관의 관련 웹사이트 표현도 제거했다.
시행일, 문서 간 이동 링크, 운영사/문의 하단, 모바일/인쇄 스타일을 추가했다.
개인정보처리방침 마지막에는 Unity 정책 링크 및 Unity 계정 삭제와 게임 데이터 삭제의 구분 안내를 추가했다.
추가 문단은 운영사의 수집/위탁/국외 이전 고지를 대신하지 않는다.
원본 TXT와 클라이언트 로케일은 수정하지 않았다.

## 4. 공개 전 남은 확인

1. 위 항목과 모든 문장을 검토하고 세 HTML의 대괄호를 해결한다.
2. 초안 안내·노란 강조·noindex는 사용자 요청에 따라 제거 완료했다.
3. 그와 별개로 미확정 본문이 남아 있어 공개 가능한 최종 내용이라고 확인한 상태는 아니다. push하면 문서가 공개되고 검색될 수 있다.
4. 로컬 index.html을 브라우저로 열고 링크/모바일 표시/문장을 확인한다.
5. 실제 공개본 확인 후에만 Unity 대시보드와 게임 설정에 연결한다.

## 5. 기존 GitHub Pages에 배포

### 저장소에서 할 일

1. 로컬 D:/project/kaoraswoo.github.io의 변경을 확인한다. 추가 대상은 may-policy/와 이 가이드뿐이다.
2. 완성된 문서를 커밋하고 기존 배포 브랜치에 push한다. 현재 기본 브랜치는 master지만 실제 Pages 설정을 우선한다.
3. GitHub 저장소 → Settings → Pages로 이동한다.

### Pages가 이미 정상 배포 중이라면

Source/브랜치/폴더 설정을 바꾸지 않는다. 기존 배포가 새 폴더도 포함하는지 확인한다.
Deploy from a branch로 master / (root)를 배포하고 있다면 그대로 동작한다.
만약 /docs를 소스로 쓴다면 해당 배포 소스 안에 may-policy 폴더가 있어야 한다.
GitHub Actions 방식이라면 기존 워크플로의 산출물에 이 폴더가 포함되어야 한다. 새 워크플로로 기존 것을 교체하지 않는다.

### Pages가 꺼져 있고 루트의 현재 Jekyll 사이트를 활성화하려면

Settings → Pages → Build and deployment:

- Source: Deploy from a branch
- Branch: master
- Folder: /(root)
- Save

이 설정은 약관만 아니라 저장소 루트의 기존 홈페이지 전체를 공개한다는 점을 확인한다.
Custom domain은 비워둬도 된다. 기존 사용자 도메인이 설정되어 있다면 삭제하지 말고 실제 제공 주소를 확인한다.
Enforce HTTPS가 선택 가능하면 켠다. 기본 github.io 주소를 HTTPS로 접근한다.

### 배포 확인

- Actions에서 pages build and deployment(또는 기존 배포 워크플로) 성공 확인.
- 위 두 문서 URL을 로그아웃/시크릿 창과 휴대폰에서 직접 열어 본다.
- GitHub blob/raw 파일 주소가 아니라 github.io의 실제 HTML 주소를 사용한다.
- 404라면 배포 성공 여부, 배포 브랜치/소스 폴더, may-policy가 이중으로 중첩되지 않았는지 확인한다.
- CSS가 안 보이면 policy.css 포함 여부와 대소문자를 확인한다.
- 기존 Jekyll 빌드 오류가 있다면 약관과 무관한 기존 오류일 수 있다. .nojekyll로 우회하지 않는다.
- 이후 문서 변경은 같은 파일을 수정/커밋/push한다. URL과 파일명은 유지하고 시행일/필요한 사전 공지도 관리한다.
- 이 폴더는 기존 사이트와 내용/스타일이 분리되지만 저장소와 배포 파이프라인은 공유한다.

## 6. Unity Player Accounts 연결

현재 열었던 Unity 대시보드의 해당 프로젝트 → Authentication → Identity Providers에서
Unity Player Accounts 추가/수정 화면으로 이동한다. UI 명칭이 바뀌면 해당 제공자 설정을 찾는다.

| 입력란 | 값 |
|---|---|
| OAuth client name | 시편섬광자 (실제 로그인 화면에 표시할 이름으로 확인) |
| Platform | 실제 제공할 iOS/Android, PC만 선택 |
| Terms of Service link | https://kaoraswoo.github.io/may-policy/terms.html |
| Privacy Policy link | https://kaoraswoo.github.io/may-policy/privacy.html |

완성된 두 URL이 로그인 없이 열리는지 확인 후 Add provider / Save 한다.
여기에 링크를 입력하는 것만으로 게임의 약관 동의 기록이나 개인정보 삭제 기능이 구현되는 것은 아니다.

## 7. mayclient 연결

UIPopupUserSetting.OpenSupportDocument는 URL 로케일 키가 http로 시작하면 외부 링크를 연다.
로케일 원본에서 다음 키를 설정하고 프로젝트의 기존 시트/로케일 배포 절차로 반영한다.

| 로케일 키 | 값 |
|---|---|
| Setting_TermsUrl | https://kaoraswoo.github.io/may-policy/terms.html |
| Setting_PrivacyUrl | https://kaoraswoo.github.io/may-policy/privacy.html |

여러 언어가 같은 한국어 페이지를 사용할지, 번역 페이지를 제공할지는 출시 정책으로 결정한다.
실제 URL이 아직 배포되지 않았으므로 이번 작업에서는 클라이언트 값을 변경하지 않았다.
URL이 없는 경우 내부 본문으로 돌아가므로 Setting_TermsBody / Setting_PrivacyBody 및 TXT 초안과
공개 약관이 서로 달라지지 않도록 정리한다. 웹을 정본으로 쓸 경우 해당 언어의 URL 설정 누락을 검사한다.

## 8. 출처 및 사용 제한

- [GitHub Pages 배포 설정](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)
- [Jekyll 정적 파일](https://jekyllrb.com/docs/static-files/)
- [GitHub Pages 설명 및 IP 기록 안내](https://docs.github.com/en/pages/getting-started-with-github-pages/what-is-github-pages)
- [GitHub Pages 사용 제한](https://docs.github.com/en/pages/getting-started-with-github-pages/github-pages-limits)
- [Unity Player Accounts 개인정보 안내](https://docs.unity.com/en-us/authentication/privacy-and-consent/data-privacy-unity-player-accounts)
- [Unity 게임 플레이어 개인정보처리방침](https://unity.com/legal/game-player-and-app-user-privacy-policy)

GitHub Pages는 상거래/상용 SaaS 운영 등의 사용 제한이 있다. 이번 파일은 안내 문서만 제공한다.
향후 결제/로그인/운영툴 API를 이 사이트에 붙이는 용도로 확장하지 않는다.
서비스와 연관된 문서 호스팅의 허용 여부가 불명확하면 GitHub에 확인한다.
