# Hadoop HDFS 실습 프로젝트

**태그**: #hands-on #hadoop #hdfs #실습 #프로젝트
**난이도**: 중급
**예상 소요 시간**: 8-12시간 (환경 구축 포함)

## 프로젝트 목표

이 프로젝트는 Hadoop HDFS를 실제로 구축하고, 운영하며, 테스트하는 hands-on 실습 프로젝트입니다. 이론적 지식이 아닌 **실제로 동작하는 Hadoop 클러스터**를 구축하고 다양한 시나리오를 테스트하면서 분산 파일 시스템에 대한 실무 경험을 쌓는 것이 목표입니다.

## 학습 로드맵

```
01-환경구축.md
    ↓
02-기본명령어실습.md
    ↓
03-실전시나리오.md
    ↓
04-성능장애테스트.md
```

### 단계별 설명

| 단계 | 파일명 | 내용 | 체크포인트 |
|------|--------|------|-----------|
| 1 | `01-환경구축.md` | Docker/로컬 환경에서 Hadoop 클러스터 구축 | ✅ HDFS 웹 UI 접속 성공 |
| 2 | `02-기본명령어실습.md` | HDFS 기본 명령어 실습 | ✅ 파일 업로드/다운로드 성공 |
| 3 | `03-실전시나리오.md` | RDS 백업, 로그 분석 등 실무 시나리오 | ✅ 실전 시나리오 1개 이상 완료 |
| 4 | `04-성능장애테스트.md` | 성능 벤치마크, 장애 시뮬레이션 | ✅ DataNode 장애 복구 확인 |

## 필요 사전 지식

- **필수**:
  - Linux 기본 명령어 (ls, cd, chmod 등)
  - Docker 기본 사용법
  - 분산 시스템 기본 개념

- **권장**:
  - Java 기초
  - 네트워크 기본 지식 (포트, IP 등)
  - 파일 시스템 개념

## 필요 도구

- **개발 환경**:
  - Docker Desktop (최소 4GB 메모리 할당)
  - 터미널 (macOS: Terminal/iTerm2, Windows: WSL2)
  - 텍스트 에디터 (VS Code, Vim 등)

- **선택 사항**:
  - Postman (API 테스트용)
  - htop/glances (시스템 모니터링)

## 시작하기 전에

### 시스템 요구사항 체크리스트

- [ ] Docker Desktop 설치 및 실행 확인
- [ ] 최소 10GB 이상의 디스크 여유 공간
- [ ] Docker에 최소 4GB 메모리 할당
- [ ] 포트 9870, 8088, 9000 사용 가능 (충돌 확인)

### 디버깅 팁

1. **Docker 컨테이너 로그 확인**:
   ```bash
   docker logs <container_name>
   ```

2. **HDFS 상태 확인**:
   - 웹 UI: http://localhost:9870
   - CLI: `hdfs dfsadmin -report`

3. **일반적인 문제 해결**:
   - 포트 충돌 → `lsof -i :<port>` 로 확인 후 종료
   - 메모리 부족 → Docker Desktop 메모리 할당 증가
   - 권한 문제 → `chmod 777` 또는 `sudo` 사용

## 프로젝트 완료 기준

아래 항목을 모두 달성하면 프로젝트 완료:

- [ ] Hadoop 클러스터 구축 및 정상 동작 확인
- [ ] HDFS 기본 명령어 10개 이상 실습 완료
- [ ] 실전 시나리오 2개 이상 구현
- [ ] DataNode 장애 시뮬레이션 및 복구 성공
- [ ] 성능 벤치마크 1회 이상 수행

## 참고 자료

- [Apache Hadoop 공식 문서](https://hadoop.apache.org/docs/stable/)
- [HDFS Architecture Guide](https://hadoop.apache.org/docs/stable/hadoop-project-dist/hadoop-hdfs/HdfsDesign.html)
- [Hadoop Docker Hub](https://hub.docker.com/r/apache/hadoop)

## 다음 단계

환경 구축부터 시작하세요:
→ **[01-환경구축.md](./01-환경구축.md)**

---

**작성일**: 2025-11-17
**최종 수정**: 2025-11-17
**버전**: 1.0
