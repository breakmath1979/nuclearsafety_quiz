Lecture 암기앱 v3 AI맞춤형 JSON/진도 자동생성형

파일 구성:
- index.html
- quiz_manifest.json
- lecture09_questions_v3_format.json
- lecture09_progress_v3.json
- lecture11_p1_54_questions_v3_format.json
- lecture11_p1_54_progress_v3.json

수정 내용:
- [진도JSON 내보내기] 버튼 삭제
- [진도JSON 불러오기] 버튼 삭제
- 문제 JSON은 quiz_manifest.json에 등록된 파일을 자동으로 읽음
- progress JSON이 있으면 자동으로 읽음
- progress JSON이 없으면 현재 강의 문제 개수에 맞춰 빈 진도를 자동 생성
- 생성된 진도는 브라우저 내부 localStorage에 자동 저장
- v3 AI맞춤형 디자인 유지
- 괄호 추가, 맞음/틀림, 즐겨찾기, AI 추천, 시험지TXT 유지

새 강의 추가:
1. 새 문제 JSON을 업로드합니다.
   예: lecture12_questions_v3_format.json

2. quiz_manifest.json에 추가합니다.
{
  "label": "Lecture12 우선순위 100문제",
  "datasetId": "lecture12",
  "file": "lecture12_questions_v3_format.json",
  "progressFile": "lecture12_progress_v3.json"
}

3. lecture12_progress_v3.json 파일이 있으면 앱이 읽습니다.
4. lecture12_progress_v3.json 파일이 없어도 앱이 빈 진도를 자동 생성합니다.

주의:
- GitHub Pages는 정적 사이트라 브라우저가 GitHub 저장소의 JSON 파일 자체를 직접 생성/수정하지는 못합니다.
- progress JSON 파일이 없을 때의 “자동 생성”은 앱 내부 진도 상태 생성이며, 공부 중 진도는 브라우저 localStorage에 자동 저장됩니다.
- 여러 기기에서 같은 진도를 공유하려면 별도 동기화 방식이 필요합니다.
