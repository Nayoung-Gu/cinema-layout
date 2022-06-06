# 🎞 Cinema Layout

## 👀 개요

[프론트엔드 스쿨] Sass를 활용하여 영화 목록 화면 구현하기
<br>
<br>

## 📌 주요 속성

- Sass : 변수 리스트에 폰트와 색상 값 저장 및 Nesting(중첩) 기능을 활용하여 CSS 코드 구조화
- 예고편 옆의 재생 아이콘, 평점 옆의 별 아이콘 등 큰 의미를 지니지 않는 반복적인 아이콘은 가상요소로 구현
- 태블릿, 데스크탑에 적용되는 반응형 페이지 (모바일은 일부 불가, 추후 구현 예정)
- `movie-box:hover`일 때의 `ease-in-out` 애니메이션 추가
- scss의 list, map 변수 저장 및 활용
- 영화 제목과 출연진 길이가 넓이를 초과할 것을 대비해 `%ellipsis extend` 사용
<br>

## ⚙ 개선할 부분
1. 모바일에서 footer가 잘리는 현상 <br>
  👉 이슈: responsive viewer로 확인해봤을 때 `width:420px` 이하부터 footer가 잘리는 현상 <br>
  👉 해결: 모바일 환경 전용 미디어 쿼리를 설정했고, `.footer-wrapper` 너비에 `max-width`를 지정했다. 너비가 줄어들었을 때 `footer`의 컨텐츠들이 기존의 같은 행이 아닌 다른 행에 여유롭게 배치될 수 있도록 `flex-direction: column`으로 변경했다.
      
      <br>
      
2. Sass 코드 정리 <br>
  👉 font-family, 색상(bg, border) 외에 `font-weight`, `font-size` 등을 포함하여 Maps로 키와 값을 정리하여 적용할 예정이다. <br>
  👉 movie-box의 중첩이 길어져, 가독성 확보를 위해서 컴파일된 css 파일과 비교해 코드를 정리할 예정이다. <br>
  👉 진행 상황(5.4): HTML, Scss 2차 코드 정리 완료 / 추후 기타 변수 분류 예정
  <br>
  
3. 영화 정보의 개요, 평점 부분 <br>
  👉 이슈: dt, dd로 넣은 정보들 중 개요, 평점만 일렬로 정렬해야 하는 부분을 구현하기 위한 최선의 코드를 찾지 못했다. <br>
  👉 진행 상황(5.1): float, grid로 각각 구현해보려고 했는데 원래 의도대로 결과가 나오지 않아 flex로 처리를 해놓은 상황 <br>
  👉 해결(5.2): 스타일링 목적이므로 각각의 dt, dd마다 div로 감싸 평점(`div class="rating"`)에 float을 적용하고, 개봉(`div class="release"`에 `"clear:both"` 처리)
<br>

## 🔎 실제 구현 화면
![image](https://user-images.githubusercontent.com/80025366/166187742-73980208-5e2f-41b5-8847-4e4694e9bdd3.png)
