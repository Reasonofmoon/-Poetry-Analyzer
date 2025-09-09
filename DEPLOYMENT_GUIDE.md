# 🚀 GitHub Pages 배포 가이드

이 가이드는 Poetry Analyzer를 GitHub Pages에 배포하는 방법을 설명합니다.

## 📋 배포 전 체크리스트

### 1. 필수 파일 확인
- ✅ `index.html` - 메인 웹 애플리케이션
- ✅ `README.md` - 프로젝트 설명
- ✅ `_config.yml` - Jekyll 설정
- ✅ `LICENSE` - MIT 라이선스
- ✅ `.gitignore` - Git 제외 파일 목록

### 2. 설정 파일 수정
다음 파일들에서 `yourusername`을 실제 GitHub 사용자명으로 변경하세요:

- `README.md`
- `_config.yml`
- `index.html` (footer 부분)

## 🔧 배포 단계

### 1단계: GitHub 저장소 생성

1. GitHub에 로그인
2. 새 저장소 생성
3. 저장소 이름: `poetry-analyzer` (또는 원하는 이름)
4. Public으로 설정
5. README 파일 생성하지 않음 (이미 있음)

### 2단계: 코드 업로드

```bash
# 로컬에서 Git 초기화
git init

# 파일 추가
git add .

# 첫 번째 커밋
git commit -m "Initial commit: Poetry Analyzer web app"

# 원격 저장소 연결 (yourusername을 실제 사용자명으로 변경)
git remote add origin https://github.com/yourusername/poetry-analyzer.git

# 메인 브랜치로 푸시
git branch -M main
git push -u origin main
```

### 3단계: GitHub Pages 활성화

1. GitHub 저장소 페이지로 이동
2. **Settings** 탭 클릭
3. 왼쪽 메뉴에서 **Pages** 클릭
4. **Source** 섹션에서:
   - **Deploy from a branch** 선택
   - **Branch**: `main` 선택
   - **Folder**: `/ (root)` 선택
5. **Save** 버튼 클릭

### 4단계: 배포 확인

1. 몇 분 후 페이지 상단에 배포 URL 표시
2. URL 형태: `https://yourusername.github.io/poetry-analyzer`
3. 링크 클릭하여 사이트 확인

## 🌐 사용자 정의 도메인 (선택사항)

### 도메인 연결 방법

1. 도메인 구매 (예: `poetry-analyzer.com`)
2. DNS 설정에서 CNAME 레코드 추가:
   ```
   www.poetry-analyzer.com → yourusername.github.io
   ```
3. `CNAME` 파일 수정:
   ```
   www.poetry-analyzer.com
   ```
4. GitHub Pages 설정에서 Custom domain 입력

## 🔒 HTTPS 설정

GitHub Pages는 자동으로 HTTPS를 제공합니다:

1. Settings > Pages로 이동
2. **Enforce HTTPS** 체크박스 활성화
3. 사이트가 `https://`로 접속되는지 확인

## 📊 Google Analytics 연결 (선택사항)

### 1. Google Analytics 계정 생성
1. [Google Analytics](https://analytics.google.com/) 접속
2. 새 속성 생성
3. 측정 ID 복사 (예: `G-XXXXXXXXXX`)

### 2. 코드에 추가
`_config.yml` 파일에서 주석 해제:
```yaml
google_analytics: G-XXXXXXXXXX
```

## 🔄 업데이트 방법

코드 수정 후 배포:

```bash
# 변경사항 추가
git add .

# 커밋
git commit -m "Update: 새로운 기능 추가"

# 푸시 (자동으로 재배포됨)
git push origin main
```

## 🐛 문제 해결

### 일반적인 문제들

**1. 사이트가 로드되지 않음**
- GitHub Pages 활성화 확인
- `index.html` 파일 존재 확인
- 몇 분 후 다시 시도

**2. CSS/JS가 로드되지 않음**
- 파일 경로 확인
- 브라우저 캐시 삭제
- 개발자 도구에서 오류 확인

**3. API 키 관련 오류**
- CORS 정책 확인
- API 키 유효성 검증
- 브라우저 콘솔에서 오류 메시지 확인

**4. 모바일에서 레이아웃 깨짐**
- 반응형 CSS 확인
- 뷰포트 메타 태그 확인
- 다양한 기기에서 테스트

## 📈 성능 최적화

### 1. 이미지 최적화
- 이미지 압축
- WebP 형식 사용
- 적절한 크기 설정

### 2. 코드 최적화
- CSS/JS 압축
- 불필요한 코드 제거
- 캐싱 활용

### 3. SEO 최적화
- 메타 태그 설정
- 구조화된 데이터 추가
- 사이트맵 생성

## 📱 PWA 변환 (고급)

Progressive Web App으로 변환하려면:

1. `manifest.json` 파일 생성
2. Service Worker 추가
3. 오프라인 기능 구현

## 🔐 보안 고려사항

### API 키 보안
- 클라이언트 사이드에서만 사용
- 환경변수 사용 불가 (정적 사이트)
- 사용자에게 개인 API 키 사용 안내

### HTTPS 강제
- 모든 외부 리소스 HTTPS 사용
- Mixed Content 오류 방지

## 📞 지원

배포 중 문제가 발생하면:

1. [GitHub Pages 문서](https://docs.github.com/en/pages) 참조
2. [Jekyll 문서](https://jekyllrb.com/docs/) 확인
3. GitHub Issues에 문제 보고

## 🎉 배포 완료!

축하합니다! Poetry Analyzer가 성공적으로 배포되었습니다.

이제 전 세계 사용자들이 여러분의 AI 기반 시 분석 도구를 사용할 수 있습니다.

---

**📚 Happy Poetry Analysis! 🎭**