Lecture 암기앱 v3 AI맞춤형 JSON/진도 분리형

파일 구성:
- index.html
- quiz_manifest.json
- lecture09_questions_v3_format.json
- lecture09_progress_v3.json
- lecture11_p1_54_questions_v3_format.json
- lecture11_p1_54_progress_v3.json

핵심:
- 문제 데이터는 questions JSON으로 분리
- 진도 데이터는 progress JSON으로 분리
- 새 강의에 progressFile이 없거나 progress JSON 파일을 읽지 못하면 앱이 자동으로 빈 진도를 생성
- 생성된 진도는 [진도JSON 내보내기]로 해당 강의 progress JSON 파일명으로 저장 가능
- [진도JSON 불러오기]로 기존 진도 JSON을 다시 적용 가능

새 강의 추가:
1. 새 문제 JSON 업로드
   예: lecture12_questions_v3_format.json

2. quiz_manifest.json에 추가
{
  "label": "Lecture12 우선순위 100문제",
  "datasetId": "lecture12",
  "file": "lecture12_questions_v3_format.json",
  "progressFile": "lecture12_progress_v3.json"
}

3. lecture12_progress_v3.json이 없어도 앱은 빈 진도를 자동 생성합니다.
4. 공부 후 [진도JSON 내보내기]를 누르면 lecture12_progress_v3.json으로 저장됩니다.
5. 그 파일을 GitHub에 업로드하면 진도 JSON도 파일로 관리됩니다.

진도 JSON 구조:
{
  "stats": {
    "1": {"right": 0, "wrong": 0}
  },
  "extraBlanks": {
    "1": []
  },
  "favorites": {},
  "mode": "all"
}

주의:
- GitHub Pages는 정적 사이트라 앱이 GitHub 저장소의 JSON 파일을 직접 수정할 수는 없습니다.
- 앱은 진도 JSON을 읽고, 없으면 빈 진도를 만들고, 내보내기/불러오기로 관리합니다.
- 내보낸 progress JSON을 GitHub에 다시 업로드하면 여러 기기에서도 같은 진도 파일을 기준으로 시작할 수 있습니다.
