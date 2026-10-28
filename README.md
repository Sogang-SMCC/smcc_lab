# Soft Matter Computational Chemistry Lab

서강대학교 화학과 연성 소재 전산화학 연구실 (성봉준 교수) 홈페이지 저장소입니다.

- Site: https://sogang-smcc.github.io/smcc_lab/
- Built with [Jekyll](https://jekyllrb.com/) and the [al-folio](https://github.com/alshedivat/al-folio) theme (MIT License)

## 연구실 소개

"연성 소재 전산화학 연구실"은 컴퓨터 시뮬레이션, 인공지능, 통계열역학, 양자화학을 포함한 여러가지 이론적 방법을 이용하여 재료물리화학, 생물물리화학 등 다양한 분야를 연구합니다.
(Molecular Simulations at multiscales)

- 주소: 서울특별시 마포구 백범로 35, 서강대학교 화학과 리치과학관 1217호, 1215호
- 전화: 02-716-8889
- 이메일: bjsung@sogang.ac.kr

## 업데이트 흐름 한눈에 보기

1. 파일을 고친다 (GitHub 웹 또는 내 컴퓨터)
2. `main` 브랜치에 commit/push 한다
3. GitHub Actions가 자동으로 사이트를 빌드·배포한다 (보통 3~5분)
4. 사이트에서 확인한다 (예전 화면이 보이면 `Ctrl+Shift+R`, Mac은 `Cmd+Shift+R`)

`main`에 올라간 내용은 곧바로 공개 사이트에 반영됩니다. 저장소도 공개(public)이므로 공개하면 안 되는 자료는 올리지 않습니다.

### 방법 A: GitHub 웹에서 바로 고치기 (간단한 수정)

설치할 것이 없어 멤버 추가, 논문 추가, 오타 수정에 가장 편합니다.

- **글 수정**: 저장소에서 파일을 열고 연필 아이콘(Edit) → 수정 → **Commit changes** → "Commit directly to the main branch" 선택 → Commit
- **사진 올리기**: 사진을 넣을 폴더(예: `assets/img/smcc/members/`)로 이동 → **Add file → Upload files** → 파일 끌어놓기 → Commit
- 사진을 올린 뒤 그 사진을 쓰는 파일(`_data/members.yml` 등)도 고쳐야 화면에 나옵니다.

### 방법 B: 내 컴퓨터에서 고치기 (여러 파일을 한꺼번에, 미리 보기가 필요할 때)

```bash
git clone git@github.com:Sogang-SMCC/smcc_lab.git   # 처음 한 번
cd smcc_lab
git pull                                             # 작업 전 항상 최신으로
# ... 파일 수정 ...
git add -A
git commit -m "Add 2027 spring group photos"
git push origin main
```

다른 사람이 웹에서 먼저 고쳤다면 push가 거절됩니다. 그때는 `git pull` 후 다시 push 합니다.

### 배포 확인과 실패했을 때

- 저장소의 **Actions** 탭에서 "Deploy site"가 초록색 체크면 성공입니다. 이어서 "pages build and deployment"가 끝나면 사이트에 반영됩니다.
- 빨간색 X면 빌드가 실패한 것이고 사이트는 **이전 상태 그대로** 유지됩니다. 실패한 항목을 눌러 로그를 보면 원인이 나옵니다. 흔한 원인:
  - `.yml` 파일의 들여쓰기·괄호·쉼표 오류 (`_data/members.yml`, `_pages/pictures.md` 맨 위 부분)
  - `papers.bib`의 중괄호 `{ }` 짝이 맞지 않음, 키 중복
- "Prettier code formatter"가 실패해도 사이트 배포에는 영향이 없습니다 (코드 줄맞춤 검사일 뿐입니다).
- 고친 내용을 되돌리려면 GitHub에서 해당 commit을 열어 이전 내용으로 다시 고치거나, `git revert <commit>` 후 push 합니다.

## 무엇을 어디서 고치나

| 바꿀 내용                    | 파일                                                     |
| ---------------------------- | -------------------------------------------------------- |
| 첫 화면 (Welcome)            | `_pages/about.md` (사진: `assets/img/smcc/campus.png`)   |
| 멤버 추가/수정/졸업          | `_data/members.yml` (사진: `assets/img/smcc/members/`)   |
| 교수님 소개                  | `_pages/bong-june.md`                                    |
| 연구 소개                    | `_pages/research.md` (그림: `assets/img/smcc/research/`) |
| 논문 추가                    | `_bibliography/papers.bib` 맨 위                         |
| 단체사진                     | `_pages/pictures.md` (사진: `assets/img/smcc/pictures/`) |
| 메뉴 순서                    | 각 페이지 맨 위의 `nav_order:` (Welcome은 항상 맨 앞)    |
| 사이트 제목, 기능 켜고 끄기  | `_config.yml`                                            |
| 글자 굵기·색, 사진 배치 규칙 | `_includes/smcc_style.liquid`                            |
| 메뉴 왼쪽 이름 ("SMCC Lab")  | `_includes/header.liquid`                                |

## 자주 하는 작업

### 새 멤버 추가 / 졸업 처리

1. `assets/img/smcc/members/`에 사진을 올립니다 (예: `hgd.jpg`). 세로 사진(3:4)이 가장 잘 맞습니다.
2. `_data/members.yml`의 해당 그룹(`Ph. D. Students`, `Master Students`) `people` 목록에 한 줄을 추가합니다. 적힌 순서대로 화면에 나옵니다.

```yaml
- { name: 홍길동, email: hgd@sogang.ac.kr, photo: hgd.jpg }
```

졸업하면 그 줄을 `alumni`의 `Ph. D. Graduates` 또는 `Master Graduates` 아래로 옮기고 현재 소속을 `info`에 적습니다. `info`의 항목 하나가 한 줄로 표시됩니다.

```yaml
- { name: 홍길동, email: hgd@gmail.com, photo: hgd.jpg, info: [삼성 SDI] }
- { name: 김철수, email: cskim@gmail.com, photo: cskim.jpg, info: [OO대학교, 화학과, 교수] }
```

### 새 논문 추가

`_bibliography/papers.bib` 맨 위(`---` 두 줄 아래)에 추가합니다. 연도별로 묶이고, 같은 해 안에서는 파일에 적힌 순서대로 표시됩니다.

```bibtex
@article{hong2027example,
  title        = {Paper Title},
  author       = {Hong†, G. D. and Kim†, C. S. and Lee, Y. and Sung*, B. J.},
  journal      = {J. Chem. Phys.},
  volume       = {166},
  pages        = {123456},
  year         = {2027},
  bold_authors = {1 2},
  smcc_no      = {125},
}
```

위 항목은 이렇게 표시됩니다 (굵은 글씨 = 연구실 멤버, 교수님은 굵은 파랑색, 저널명은 굵은 기울임).

> 125\. “Paper Title”, **G. D. Hong**†, **C. S. Kim**†, Y. Lee, and **B. J. Sung\***, **_J. Chem. Phys._** 166, 123456 (2027)

| 항목           | 설명                                                                                          |
| -------------- | --------------------------------------------------------------------------------------------- |
| `title`        | 논문 제목                                                                                     |
| `author`       | `성, 이니셜` 형식, 저자 사이는 `and`. 공동 1저자는 성 뒤에 `†`, 교신저자는 `*`                |
| `journal`      | 저널명                                                                                        |
| `volume`       | 권                                                                                            |
| `pages`        | 페이지 또는 논문 번호 (범위는 `2000--2008`처럼 하이픈 두 개)                                  |
| `year`         | 연도 (이 값으로 연도별로 묶임)                                                                |
| `bold_authors` | 굵게 표시할 연구실 멤버의 저자 순번 (1부터, 공백으로 구분). 교수님은 자동으로 강조되므로 제외 |
| `smcc_no`      | 논문 번호 (현재 마지막 번호 + 1)                                                              |
| `note`         | 출판 전 상태: `submitted`, `accepted`, `to be submitted` (기울임꼴로 표시)                    |
| `selected`     | `{true}`이면 Welcome과 교수님 페이지의 대표 논문(Selected Publications)에 표시                |
| `award`        | 표지 선정 등 특기 사항. 연도 뒤에 ` - 내용` 형식으로 표시                                     |
| `doi`, `html`  | DOI 또는 논문 링크를 넣으면 끝에 `[DOI]`, `[Link]` 링크가 생김 (선택)                         |

- 논문 표기: 공동 1저자는 성 뒤에 `†`, 교신저자는 `*` (예: `Sung*, B. J.`).
- 첫 줄의 키(`hong2027example`)는 겹치지 않게 `첫저자성+연도+제목첫단어`로 만듭니다.
- 출판 전 논문은 `journal`, `volume`, `pages` 없이 `note`만 적습니다. 게재되면 `note`를 지우고 저널 정보를 채웁니다.

### 단체사진 앨범 추가

1. `assets/img/smcc/pictures/`에 사진을 올립니다.
2. `_pages/pictures.md` 맨 위 `albums:` 목록의 **첫 번째 자리**에 추가합니다. 위에 있는 앨범부터 표시됩니다.

```yaml
albums:
  - title: 2027 Spring @Sogang
    rows:
      - [{ f: 2027-spring-01.jpg, r: 1.5 }] # 단체사진 (크게)
      - [{ f: 2027-spring-02.jpg, r: 1.33 }, { f: 2027-spring-03.jpg, r: 0.75 }]
```

- `rows`의 한 줄이 화면의 한 줄입니다. 사진이 한 장뿐인 줄은 크게 가운데에, 여러 장인 줄은 높이를 맞춰 나란히 놓입니다.
- `r`은 사진의 **가로÷세로** 비율입니다 (가로 1200, 세로 800이면 `1.5`). 파일 속성이나 `identify 파일.jpg`로 크기를 확인합니다.
- 작은 사진 줄이 단체사진보다 넓어 보이면 앨범에 `row_width: 70%`를 추가해 그 앨범의 여러 장짜리 줄만 좁힐 수 있습니다.

### 연구 그림 추가

`_pages/research.md`의 그림 목록(`<div class="row">` 안)에 블록을 하나 추가합니다. 한 줄에 두 장씩 배치됩니다.

```liquid
<div class="col-sm-6 mt-3">
  {% include figure.liquid path="assets/img/smcc/research/새그림.png" class="img-fluid rounded z-depth-1" alt="그림 설명" zoomable=true %}
</div>
```

## 사진 파일 규칙

- **원본을 그대로 올립니다.** 사이트는 올린 파일을 다시 압축하지 않고 그대로 보여줍니다. 화질을 위해 따로 줄이거나 다시 저장하지 않는 것이 좋습니다. 다만 휴대폰 원본처럼 아주 큰 사진(가로 3000px 이상, 수 MB)은 긴 변 2000px 정도로 줄이면 페이지가 빨리 열립니다.
- 형식은 `.jpg`, `.png`를 씁니다. 아이폰 `.heic`는 웹에서 보이지 않으므로 jpg로 바꿔서 올립니다.
- 파일 이름은 영문 소문자, 숫자, `-`만 씁니다 (예: `2027-spring-01.jpg`). **`_`(밑줄)로 시작하면 사이트에 나오지 않습니다.**
- 사진 속 위치정보(GPS)는 공개 저장소에 그대로 남으므로, 휴대폰으로 찍은 사진은 위치정보를 지우고 올립니다 (휴대폰 공유 옵션의 "위치 정보 제거", 또는 `convert 원본.jpg -auto-orient -strip -quality 95 새파일.jpg`).

## 건드리지 않아도 되는 것

- `Gemfile`, `Gemfile.lock`, `package.json`, `package-lock.json`, `purgecss.config.js`, `.github/workflows/deploy.yml`: 빌드·배포에 필요한 설정입니다. 고치면 배포가 깨질 수 있습니다.
- `_layouts/bib.liquid`(논문 서식), `_includes/header.liquid`(메뉴): al-folio 테마 파일을 이 사이트에 맞게 덮어쓴 것입니다. 테마를 업데이트해도 이 두 파일은 자동으로 바뀌지 않습니다. 테마 업데이트는 하지 않아도 사이트 운영에 문제가 없습니다.
- `vendor/`, `node_modules/`, `_site/`: 내 컴퓨터에서 빌드할 때 생기는 폴더로, git에 올라가지 않습니다.

## 내 컴퓨터에서 미리 보기 (선택)

push 전에 화면을 확인하고 싶을 때만 필요합니다. Ruby 3.3 이상이 필요합니다.

```bash
bundle install
bundle exec jekyll serve   # http://localhost:4000/smcc_lab/
```

planck1 서버에서는 시스템 Ruby(3.0)가 오래되어, 사용자 영역에 설치해 둔 Ruby 3.3 환경을 씁니다.

```bash
export MAMBA_ROOT_PREFIX=~/.local/micromamba
~/.local/micromamba/bin/micromamba run -n jekyll bundle exec jekyll serve
```
