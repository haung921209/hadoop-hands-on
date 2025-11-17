# Claude Code 작업 지침

이 문서는 Claude Code가 이 프로젝트에서 작업할 때 따라야 할 지침을 정의합니다.

## 저장소 보안 정책

### Public GitHub 저장소
이 프로젝트는 **public GitHub 저장소**로 운영됩니다. 모든 커밋과 파일이 공개되므로, 민감한 정보가 포함되지 않도록 주의해야 합니다.

### 필터링해야 할 정보
다음 정보들은 **절대로** 커밋하거나 문서에 포함하지 마세요:

- **Credentials**: 비밀번호, API 키, 액세스 토큰
- **인증 정보**: SSH 키, 인증서, Secret keys
- **개인 민감 정보**: 주민등록번호, 신용카드 정보, 전화번호
- **환경 변수**: `.env` 파일의 실제 값들
- **데이터베이스 연결 정보**: 실제 DB 호스트, 포트, 사용자명, 비밀번호
- **내부 IP 주소**: 실제 운영 서버의 IP 주소나 도메인
- **회사/조직의 민감한 정보**: 내부 시스템 구조, 보안 설정 등

### 허용되는 정보
다음 정보들은 공개해도 괜찮습니다:

- **이름**: 작성자 이름 (예: hyungminoh)
- **프로젝트 설명**: 기술적인 내용, 사용 방법
- **예시 데이터**: 실습용 더미 데이터
- **로컬 개발 환경 설정**: localhost, 127.0.0.1 등
- **공개 문서 링크**: 공식 문서, 튜토리얼 링크
- **오픈소스 라이선스**: 라이선스 정보

### 작업 시 확인 사항

#### 커밋 전 체크리스트
- [ ] `.env` 파일이나 credentials 파일이 포함되지 않았는지 확인
- [ ] 문서에 실제 비밀번호나 API 키가 노출되지 않았는지 확인
- [ ] 실행 결과 출력에 민감한 정보가 포함되지 않았는지 확인
- [ ] 설정 파일에 실제 운영 환경의 정보가 포함되지 않았는지 확인

#### .gitignore 활용
민감한 정보가 포함될 수 있는 파일들은 `.gitignore`에 추가:
```
.env
.env.local
*.pem
*.key
credentials.json
secrets/
```

#### 문서화 시 주의사항
- 실행 결과를 문서에 추가할 때, 출력에 credentials가 포함되어 있다면 `***` 또는 `[REDACTED]`로 대체
- 예시 코드에는 항상 placeholder 값 사용 (예: `YOUR_API_KEY`, `example.com`, `user@example.com`)
- 실제 사용한 값이 아닌, 예시 값으로 문서 작성

## 작업 원칙

### 문서 검증 및 업데이트
1. 가이드 문서의 명령어를 실제로 실행
2. 실행 결과를 캡처하여 문서에 추가
3. 결과를 코드 블록(`\`\`\`output`)으로 추가
4. 민감한 정보는 필터링 후 추가

### 예시: 필터링 적용
```bash
# 원본 출력
Database connection: postgresql://admin:secret123@db.example.com:5432/mydb

# 필터링 후 문서에 추가
Database connection: postgresql://[USERNAME]:[PASSWORD]@[HOST]:[PORT]/[DATABASE]
```

## 프로젝트 구조

이 프로젝트는 Hadoop HDFS hands-on 실습 프로젝트입니다:
- `docs/`: 실습 가이드 문서
- `config/`: Hadoop 설정 파일
- `docker-compose.yml`: Docker Compose 설정

모든 설정은 **로컬 개발 환경**을 위한 것이며, 실제 운영 환경의 정보를 포함하지 않습니다.
