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

## 내용 수정하기

| 바꿀 내용              | 파일                                                      |
| ---------------------- | --------------------------------------------------------- |
| 첫 화면 (Welcome)      | `_pages/about.md`                                         |
| 멤버 추가/수정         | `_data/members.yml` (사진은 `assets/img/smcc/members/`)   |
| 교수님 소개            | `_pages/bong-june.md`                                     |
| 연구 소개              | `_pages/research.md` (그림은 `assets/img/smcc/research/`) |
| 논문 추가              | `_bibliography/papers.bib` 맨 위에 항목 추가              |
| 단체사진               | `_pages/pictures.md` (사진은 `assets/img/smcc/pictures/`) |
| 사이트 제목, 기능 설정 | `_config.yml`                                             |

- 사진 파일 이름은 `_`(밑줄)로 시작하면 안 됩니다. Jekyll이 빌드에서 제외합니다.
- 대표 논문(Welcome, 교수님 페이지에 표시)은 BibTeX 항목에 `selected = {true}`를 넣습니다.
- 논문 표기: 공동 1저자는 성 뒤에 `†`, 교신저자는 `*` (예: `Sung*, B. J.`).

### 예시: 새 멤버 추가

`assets/img/smcc/members/`에 사진(예: `hgd.jpg`)을 넣고, `_data/members.yml`의 해당 그룹 `people` 목록에 한 줄을 추가합니다.

```yaml
- { name: 홍길동, email: hgd@sogang.ac.kr, photo: hgd.jpg }
```

졸업생으로 옮길 때는 그 줄을 `alumni` 아래로 옮기고 현재 소속을 `info`에 적습니다.

```yaml
- { name: 홍길동, email: hgd@sogang.ac.kr, photo: hgd.jpg, info: [삼성 SDI] }
```

### 사진·그림 넣기

| 용도         | 넣을 폴더                    | 연결할 파일          |
| ------------ | ---------------------------- | -------------------- |
| 멤버 사진    | `assets/img/smcc/members/`   | `_data/members.yml`  |
| 단체사진     | `assets/img/smcc/pictures/`  | `_pages/pictures.md` |
| 연구 그림    | `assets/img/smcc/research/`  | `_pages/research.md` |
| 첫 화면 사진 | `assets/img/smcc/campus.jpg` | `_pages/about.md`    |

공통 규칙:

- 파일 이름은 영문 소문자, 숫자, `-`만 쓰는 것을 권장합니다 (예: `2027-spring-01.jpg`). `_`로 시작하면 사이트에 나오지 않습니다.
- 휴대폰 원본 사진은 크기가 크므로 긴 변 1600px 정도로 줄여서 올립니다. 멤버 사진은 세로 사진(3:4)이 가장 잘 맞습니다.
- 사진은 업로드할 때 위치정보(EXIF)를 지우는 것이 좋습니다. 줄이는 예시 (ImageMagick):

```bash
convert 원본.jpg -auto-orient -strip -resize '1600x1600>' -quality 85 assets/img/smcc/pictures/2027-spring-01.jpg
```

**단체사진 앨범 추가**: `_pages/pictures.md` 맨 위 `albums:` 목록의 첫 번째 자리에 추가합니다. 위에 있는 앨범부터 표시됩니다. `rows`의 한 줄이 화면의 한 줄이고, 사진이 한 장뿐인 줄은 크게 가운데에, 여러 장인 줄은 높이를 맞춰 나란히 놓입니다. `r`은 사진의 가로÷세로 비율입니다 (`identify 파일.jpg`로 크기 확인).

```yaml
albums:
  - title: 2027 Spring @Sogang
    rows:
      - [{ f: 2027-spring-01.jpg, r: 1.5 }] # 단체사진 (크게)
      - [{ f: 2027-spring-02.jpg, r: 1.33 }, { f: 2027-spring-03.jpg, r: 0.75 }]
```

**연구 그림 추가**: `_pages/research.md`의 그림 목록(`<div class="row">` 안)에 블록을 하나 추가합니다. 한 줄에 두 장씩 배치됩니다.

```liquid
<div class="col-sm-6 mt-3">
  {% include figure.liquid path="assets/img/smcc/research/새그림.jpg" class="img-fluid rounded z-depth-1" alt="그림 설명" zoomable=true %}
</div>
```

### 예시: 새 논문 추가

`_bibliography/papers.bib` 맨 위(`---` 두 줄 아래)에 추가합니다. 같은 해 안에서는 파일에 적힌 순서대로 표시됩니다.

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

Publications 페이지는 이 파일에서 자동으로 만들어지고, 연도별로 묶여 표시됩니다.

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
| `selected`     | `{true}`이면 Welcome과 교수님 페이지의 대표 논문에 표시                                       |
| `award`        | 표지 선정 등 특기 사항. 연도 뒤에 ` - 내용` 형식으로 표시                                     |
| `doi`, `html`  | DOI 또는 논문 링크를 넣으면 끝에 `[DOI]`, `[Link]` 링크가 생김 (선택)                         |

- 첫 줄의 키(`hong2027example`)는 겹치지 않게 `첫저자성+연도+제목첫단어`로 만듭니다.
- 출판 전 논문은 `journal`, `volume`, `pages` 없이 `note`만 적습니다. 게재되면 `note`를 지우고 저널 정보를 채웁니다.
- 표시 형식은 `_layouts/bib.liquid`(구조)와 `_includes/smcc_style.liquid`(굵기·색)에서 바꿀 수 있습니다.

## 배포

`main` 브랜치에 push하면 GitHub Actions(`.github/workflows/deploy.yml`)가 사이트를 빌드해 `gh-pages` 브랜치로 배포합니다. 몇 분 뒤 사이트에 반영됩니다.

## 로컬에서 미리 보기

Ruby 3.3 이상이 필요합니다.

```bash
bundle install
bundle exec jekyll serve   # http://localhost:4000/smcc_lab/
```
