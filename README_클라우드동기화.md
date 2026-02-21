# 광주대학교 총동문회 사이트 - 클라우드 동기화 가이드

## 🎯 문제 해결
**문제**: localStorage는 각 사용자의 브라우저에만 저장되어 다른 사람이 볼 수 없음
**해결**: GitHub를 무료 클라우드 데이터베이스로 사용

## 🚀 작동 방식

### 1. 자동 동기화 (모든 동문)
- 사이트 접속 시 GitHub에서 최신 데이터 자동 다운로드
- 회원가입, 행사, 회의록 등 모든 데이터 공유

### 2. 데이터 백업 (관리자만)
1. 관리자 로그인 (ID: office2024, PW: gjuniv!2024)
2. 화면 우측 하단에 "📦 클라우드 백업" 팝업 표시
3. "📥 백업 파일 다운로드" 버튼 클릭
4. alumni-data.json 파일 다운로드됨

### 3. GitHub에 업로드
1. https://github.com/sangwon4052/Gwangju-University-Alumni-Association 방문
2. "Add file" → "Upload files" 클릭
3. alumni-data.json 파일 업로드
4. "Commit changes" 클릭

## 📋 데이터 구조 (alumni-data.json)
```json
{
  "members": [...],        // 회원가입 동문 명단
  "events": [...],         // 행사 안내
  "greeting": "...",       // 인사말
  "orgChart": "...",       // 조직도
  "boardMembers": [...],   // 임원진 명단
  "minutes": [...],        // 회의록
  "expenses": [...],       // 업무추진비
  "suggestions": [...],    // 건의사항
  "donations": [...]       // 동문기부
}
```

## ⏰ 백업 권장 시점
- 새로운 회원 가입 후
- 행사 등록 후
- 회의록/업무추진비 업로드 후
- 하루 1회 (데이터 변경이 있는 경우)

## 🔧 기술 세부사항
- **localStorage**: 브라우저 임시 저장소 (빠름)
- **GitHub**: 클라우드 영구 저장소 (공유 가능)
- **동기화 흐름**: GitHub → localStorage → 화면 표시
- **백업 흐름**: 화면 입력 → localStorage → JSON 다운로드 → GitHub 업로드

## 📝 주의사항
1. alumni-data.json 파일은 **덮어쓰기**됩니다 (기존 파일 삭제 후 업로드)
2. 여러 관리자가 동시에 수정하면 마지막 업로드만 반영됩니다
3. GitHub 업로드 후 1-2분 뒤 다른 사용자들이 최신 데이터를 받을 수 있습니다

## ✅ 테스트 방법
1. PC에서 회원가입 → 백업 → GitHub 업로드
2. 스마트폰으로 사이트 접속
3. 방금 가입한 회원이 보이는지 확인
4. ✅ 보이면 성공!

## 🆘 문제 발생 시
- 콘솔 확인: F12 → Console 탭
- "✅ GitHub 클라우드 데이터 로드 완료!" 메시지 확인
- 없다면 alumni-data.json 파일이 GitHub에 없는 것

## 📞 지원
GitHub 저장소: https://github.com/sangwon4052/Gwangju-University-Alumni-Association
