Lecture 암기앱 v3 AI맞춤형 JSON분리형

목표:
- 앱 디자인과 기능은 index.html에 유지
- 문제 데이터는 별도 JSON 파일로 분리
- GitHub Pages에서 새 강의 문제를 쉽게 추가/수정

파일 구성:
- index.html
- quiz_manifest.json
- lecture09_questions_v3_format.json
- lecture11_p1_54_questions_v3_format.json

GitHub Pages 사용법:
1. 위 파일들을 GitHub repository 루트에 업로드합니다.
2. Settings -> Pages -> Deploy from branch -> main / root 선택
3. 생성된 GitHub Pages 주소로 접속합니다.
4. 앱이 quiz_manifest.json을 읽고 문제 JSON 목록을 자동으로 불러옵니다.

새 강의 추가 방법:
1. 새 문제 파일을 만듭니다.
   예: lecture12_questions_v3_format.json

2. JSON 구조는 아래 형식입니다.
{
  "title": "Lecture 12 우선순위 100문제 암기앱 v3",
  "datasetId": "lecture12",
  "questions": [
    {
      "id": 1,
      "page": "Page 1",
      "priority": "최상",
      "question": "문제 문장 (          ).",
      "answer": "정답",
      "explanation": "해설"
    }
  ]
}

3. quiz_manifest.json에 한 줄 추가합니다.
{
  "label": "Lecture12 우선순위 100문제",
  "datasetId": "lecture12",
  "file": "lecture12_questions_v3_format.json"
}

4. GitHub에 commit하면 앱의 문제데이터 선택에 Lecture12가 나타납니다.

진도 저장:
- progress는 GitHub에 저장되지 않고, 사용자의 브라우저 localStorage에 저장됩니다.
- 강의별 datasetId 기준으로 분리 저장됩니다.
- 맞음/틀림, 추가 괄호, 즐겨찾기, 학습모드가 유지됩니다.

주의:
- HTML 파일을 PC에서 직접 더블클릭하면 브라우저 보안 때문에 JSON fetch가 막힐 수 있습니다.
- GitHub Pages에서는 정상 동작합니다.
- 로컬에서 테스트하려면 폴더에서 `python -m http.server` 실행 후 http://localhost:8000 으로 접속하면 됩니다.
