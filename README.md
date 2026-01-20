# AI 코딩 교육 (1월 20일)

이 저장소는 사내 AI 코딩 교육 2일차 강의 자료 및 실습 가이드입니다.

## 1. 사전 준비 사항 (Prerequisites)
실습을 진행하기 위해 아래 환경이 구성되어 있어야 합니다.

- **Python 3.x** (3.14는 나온지 얼마 안되어 3.13 권장)
- **Node.js 18.0 이상** (MCP 서버 구동을 위해 필수)
  - 확인 방법: `node -v`

## 2. MCP 설정 (Playwright)
Copilot의 Composer 기능을 웹 브라우징과 연동하기 위해 Playwright MCP 서버를 설정합니다.
```
{
  "servers": {
    "playwright": {
      "command": "npx",
      "args": [
        "@playwright/mcp@latest"
      ]
    }
  }
}
```

## 3. 실습 자료 제출
각 세션별 실습 결과물은 아래 경로 또는 형식에 맞춰 제출해 주세요.

### 3-1. MCP 실습
- [ ] Playwright 도구를 사용하여 웹사이트 정보를 수집하는 스크립트 작성
- [MCP 실습 결과 제출](https://form.jotform.com/252854368484066)

### 3-2. RAG (검색 증강 생성) 실습
- [ ] 사내 문서를 참조하여 답변하는 챗봇 프로토타입 구현
- [RAG 실습 결과 제출](https://form.jotform.com/253483667146466)

## 4. OpenAI SSL 인증서 오류 우회 (Corporate Proxy 이슈)
사내 보안 네트워크로 인해 OpenAI API 호출 시 `SSL: CERTIFICATE_VERIFY_FAILED` 오류가 발생하는 경우, 커서를 사용해 SSL 검증을 우회할 수 있습니다.
```
openai api를 사용하는데 회사 내부망이라 api 호출 시 ssl 인증 오류가 발생하고 있어. httpx를 사용하여 ssl인증을 우회하도록 수정해줘.
```


## 5. 기타 참고 자료 (References)
- [Cursor 공식 문서](https://docs.cursor.com/)
- [Model Context Protocol (MCP) 가이드](https://modelcontextprotocol.io/)
- [OpenAI API Reference](https://platform.openai.com/docs/api-reference)
