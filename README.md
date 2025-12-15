# AI 코딩 교육 2일차 (12월 16일)

이 저장소는 사내 AI 코딩 교육 2일차 강의 자료 및 실습 가이드입니다.

## 1. 사전 준비 사항 (Prerequisites)
실습을 진행하기 위해 아래 환경이 구성되어 있어야 합니다.

- **Python 3.x** (3.14는 나온지 얼마 안되어 3.13 권장)
- **Node.js 18.0 이상** (MCP 서버 구동을 위해 필수)
  - 확인 방법: `node -v`

## 2. MCP 설정 (Playwright)
Cursor의 Composer 기능을 웹 브라우징과 연동하기 위해 Playwright MCP 서버를 설정합니다.

### 설치 명령어 (Terminal)
```bash
npx -y @modelcontextprotocol/server-playwright install
```

### Cursor 설정 (Settings > MCP)
- **Type**: `stdio`
- **Command**: `npx`
- **Args**: `-y @modelcontextprotocol/server-playwright run`

## 3. 실습 자료 제출
각 세션별 실습 결과물은 아래 경로 또는 형식에 맞춰 제출해 주세요.

### 3-1. MCP 실습
- [ ] Playwright 도구를 사용하여 웹사이트 정보를 요약하는 스크립트 작성
- **제출**: `day2/mcp_task.py` 파일로 저장

### 3-2. RAG (검색 증강 생성) 실습
- [ ] 사내 문서를 참조하여 답변하는 챗봇 프로토타입 구현
- **제출**: `day2/rag_demo.py` 및 참조한 문서 폴더

### 3-3. Agent (에이전트) 실습
- [ ] 도구(Tools)를 스스로 선택하여 문제를 해결하는 에이전트 구현
- **제출**: `day2/agent_workflow.py`

## 4. OpenAI SSL 인증서 오류 우회 (Corporate Proxy 이슈)
사내 보안 네트워크로 인해 OpenAI API 호출 시 `SSL: CERTIFICATE_VERIFY_FAILED` 오류가 발생하는 경우, 아래 코드를 상단에 추가하여 SSL 검증을 우회할 수 있습니다.

> ⚠️ **주의**: 이 방법은 교육 및 개발 목적으로만 사용하세요. 프로덕션 환경에서는 인증서를 올바르게 등록해야 합니다.

### Python (OpenAI SDK v1.0 이상)
```python
import httpx
from openai import OpenAI

# http_client에 verify=False 옵션을 전달
client = OpenAI(
    api_key="sk-...",
    http_client=httpx.Client(verify=False)
)

response = client.chat.completions.create(
    model="gpt-4o",
    messages=[{"role": "user", "content": "Hello!"}]
)
print(response.choices[0].message.content)
```

## 5. 기타 참고 자료 (References)
- [Cursor 공식 문서](https://docs.cursor.com/)
- [Model Context Protocol (MCP) 가이드](https://modelcontextprotocol.io/)
- [OpenAI API Reference](https://platform.openai.com/docs/api-reference)
- [LangChain 문서](https://python.langchain.com/docs/get_started/introduction)

