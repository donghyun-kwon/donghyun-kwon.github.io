# donghyun-kwon.github.io

권동현 개인 홈페이지 소스. GitHub Pages로 <https://donghyun-kwon.github.io/> 에 배포된다.

단일 페이지(`index.html`) 구성이며, 빌드 과정이 없다. CSS와 스크립트가 파일 안에 모두 들어
있으므로 `index.html`을 고쳐 `main`에 푸시하면 1분 내에 반영된다.

```
index.html                 # 페이지 전체 (인라인 CSS + 이메일 조립 스크립트)
assets/donghyun-kwon.jpg   # 프로필 사진
assets/kwon-cv.pdf         # CV (원본: CV_dhkwon 저장소에서 빌드 후 복사)
```

## 구성 순서

Research → Openings → Publications → Teaching.

Publications는 **최근 3년(2024–2026)만 펼쳐진 상태로** 보이고, 그 이전 실적은
`<details class="more">` 안에 접혀 있다. 해를 넘길 때 최신 연도 그룹을 `<details>` 밖으로
꺼내고 가장 오래된 노출 연도를 안으로 넣으면 된다. 접힌 구간의 논문 수는 `<summary>` 문구에
직접 적혀 있으니 함께 고칠 것.

논문 제목에는 링크를 걸지 않고, 항목 아래 뱃지로 링크를 단다.

- `<a class="b">PDF</a>` — 직접 연결되는 PDF 파일
- `<a class="b">DOI</a>` — `https://doi.org/` 링크 (라벨에는 DOI 번호를 반복하지 않음)
- `<a class="b">Paper</a>` — 출판사 논문 페이지 또는 학회 발표 페이지
- `<a class="b code">Code</a>` — 공개 구현이 있는 경우 [`cslab-pnu`](https://github.com/cslab-pnu) 조직의
  저장소 (현재 XCFI, SMORE, ELK)

### 항목 표기 규칙

- 학회는 `전체 학회명 (약칭), 연도` 형식을 쓴다. 약칭이 없는 기존 명칭은 그대로 둔다.
- 저널은 `저널명 (약칭이 있으면 병기), 연도`를 기본으로 쓴다. 확인된 권·호·쪽·논문번호는 보조 줄에 표시할 수 있다.
- 게재가 확정됐지만 아직 출판되지 않은 항목에는 연도 뒤에 `(accepted)`를 붙인다.
- 온라인 공개연도와 정식 권호연도가 다르면 두 날짜를 구분해 표시한다. 온라인 공개연도로 묶은 항목에는 `(online publication)`을 명시하고 권호 정보는 별도 줄에 남긴다.
- 논문 제목과 저자 이름은 출판사 원문을 확인한 경우에만 변경한다. 대소문자나 이름 순서가 다르다는 이유만으로 일괄 치환하지 않는다.
- Teaching의 `S`는 Spring, `F`는 Fall이다. 두 자리 연도를 쓰며 페이지에 범례를 유지한다.
- 내용을 변경할 때 footer의 `Last updated` 날짜도 함께 갱신한다.

## 내용 출처

Publications · Teaching 항목은 `CV_dhkwon` 저장소의 LaTeX
소스(`cv/*.tex`)와 같은 내용이다. **CV를 고치면 이 페이지도 함께 고쳐야 한다**
(자동 동기화 없음). `assets/kwon-cv.pdf`도 CV 저장소에서 빌드한 결과물을 수동으로 복사한
것이다.

연구실 홈페이지는 별도 저장소인 [`cslab-pnu/cslab-pnu.github.io`](https://github.com/cslab-pnu/cslab-pnu.github.io)에
있다.

## 이메일 표기

크롤러가 주소를 그대로 긁지 못하도록, 마크업에는 아이디와 도메인을 나눠 두고
(`data-u` / `data-d`) 페이지 로드 시 스크립트가 합쳐 `mailto:` 링크를 만든다. 연구실 홈페이지와
같은 방식이다.
