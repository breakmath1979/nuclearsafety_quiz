Lecture 암기앱 v3 AI 완전분리형 확실표시판

데이터 포맷:
1. quiz_manifest.json
2. questions JSON
3. progress JSON

동작:
- index.html 안에는 문제 데이터가 없습니다.
- quiz_manifest.json을 읽습니다.
- manifest에 적힌 questions JSON을 읽습니다.
- manifest에 적힌 progress JSON이 있으면 읽습니다.
- progress JSON이 없으면 현재 강의 문제 수에 맞게 빈 진도를 자동 생성합니다.
- 학습 중 진도는 브라우저 localStorage에 자동 저장됩니다.

GitHub Pages:
- 이 폴더의 모든 파일을 저장소 루트에 올리세요.
- Settings -> Pages -> main / root로 설정하세요.

로컬 테스트:
- HTML 더블클릭은 브라우저 보안 때문에 JSON 읽기가 막힐 수 있습니다.
- 로컬테스트_실행.bat를 실행한 뒤 http://localhost:8000 으로 접속하세요.
