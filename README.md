# <span style="color:#8B5CF6">온음</span> <img src="https://github.com/user-attachments/assets/42c66cd7-27d0-4246-909d-d96463410b7d" width="150" align="left" />

전화 상담원의 인권 보호를 위한 AI 음성 필터링 및 RAG 활용 법률 상담 챗봇 시스템  
<br /><br />


## 💜 프로젝트 개요 및 소개

**온음**은 전화 상담원들이 겪는 언어적 학대 문제와 미흡한 보호 시스템을 해결하고자 합니다.  
**AI 기반의 실시간 음성 필터링**, **통화 요약 및 분석**, **RAG 활용 법률 상담 챗봇**을 통해  
전화 상담원의 인권을 보호하고 건강한 근무 환경을 조성하는 것이 목표입니다.

<img alt="image" src="https://github.com/user-attachments/assets/5976d733-6dbc-4ff9-a2a1-3502829b3327" /></br>


## 💡 개발 배경 및 필요성

### 1) 프로젝트 제작 동기 및 목적
- 120다산콜재단의 설문조사 결과, **감정노동자보호법 시행 6년이 지났음**에도 여전히 **악·강성민원에 대한 보호조치가 강화되지 않거나**, 제도적으로 도입하였어도 **아직 정착되지 않았으며**, **보호조치가 충분치 않은 것**으로 나타납니다.
- 또한, 최근 챗봇과 AI 상담원의 도입으로 **단순 업무는 AI가 처리하는 반면**, **상담원**들은 **공감 및 설득의 강도가 높고 복잡한 업무를 담당**하는 **‘책임노동** 및 **‘추심노동**에 시달리게 되었습니다. 이 과정에서 **고객의 불만이 상담원에게 더 강한 언어적 폭력으로 표출되는 사례가 증가**하고 있습니다.
- 기존의 ‘감정노동'이라는 용어는 상담원의 고통을 개인의 노력 부족으로 오해하게 만들 수 있기에, **통제 불가능한 스트레스 속에서도 친절을 강요받아야 하는 ‘정동노동’의 본질**을 이해하고 전화 상담원을 보호할 수 있는 시스템을 만들고자 합니다.
<table>
  <tr>
    <td>
      <a href="https://www.youtube.com/watch?v=79oya3PjkFg">
        <img src="https://img.youtube.com/vi/79oya3PjkFg/0.jpg" width="600">
      </a>
    </td>
    <td>
      <img src="https://github.com/user-attachments/assets/39572b95-6e8d-480d-acee-7777ae230cbc" width="600">
    </td>
  </tr>
</table>


### 2) 프로젝트 특·장점

본 프로젝트는 신규 창작 프로젝트로, 기존의 소극적인 인권 보호 방식과 차별화되는 독창적인 기능과 기술적 특징을 가집니다.

- **AI의 능동적 음성 필터링, 자동 통화 제어 및 상담 요약 지원**: STT, NLP 등의 AI를 활용하여 부적절한 발언을 실시간으로 감지하고 자동 음소거 처리 등 능동적인 필터링을 적용
- **RAG 기반 챗봇을 통한 실질적·심층적 법률 자문**: 120다산콜센터의 「악·강성민원 감정노동자보호 가이드 문서」를 기반으로 학습하여, 악성민원뿐만 아니라 강성민원 유형까지 학습하여 심층적이고 실질적인 자문 수준의 답변을 제공
- **독창성**:  실시간 음성 필터링, 법률 상담 챗봇, 통화 내용 자동화를 유기적으로 결합하여, 단순한 기술 개선을 넘어 상담원의 정동노동을 이해하고 인권 보호와 업무 효율성을 동시에 달성하는 포괄적인 솔루션

---

## ⚙️ 주요 기능

- 📞 **웹 기반 통화 수신 및 실시간 STT**  
  고객이 전화를 걸면 **Twilio의 Media Streams 기능**을 활용하여 웹 브라우저에서 직접 통화를 수신하고 처리할 수 있습니다.
  수신된 음성은 **Google Cloud의 STT(Speech-to-Text) API**로 전달되어 실시간으로 텍스트로 변환됩니다.
  변환된 텍스트는 **WebSocket 통신**으로 실시간 브라우저에 전달됩니다.

- 🚫 **폭언 및 고함 감지 필터링**  
  통화 중 발생하는 **폭언과 고함**을 실시간으로 감지해 필터링합니다.
  음성은 텍스트로 변환된 뒤 AI 모델이 **욕설·성희롱·협박 여부**를 분석하며, 기준을 초과하면 폭언으로 판정합니다.
  고함은 **음성의 높이와 세기**를 분석하며, 두 판단 기준이 모두 임곗값을 초과할 경우 고함으로 판정하여  
  **비프음 처리(삐음)** 를 통해 즉시 필터링합니다.

<table>
<tr>
  <td style="text-align:center; font-weight:bold;">
    서비스 흐름도
  </td>
  <td style="text-align:center; font-weight:bold;">
    서비스 구성도
  </td>
</tr>
<tr>
  <td>
    <img src="https://github.com/user-attachments/assets/2f8a4fcf-2de9-4bc0-b0ec-1cc9d8dcf824" width="600">
  </td>
  <td>
    <img src="https://github.com/user-attachments/assets/2c33a9a4-763a-4a17-b81a-add7cdf02afe" width="600">
  </td>
</tr>
</table>


- 📜 **AI 상담내역 요약**  
  통화 종료 시 AI가 **STT 기반 텍스트와 폭언 감지 정보**를 바탕으로 상담 요약을 생성합니다.  
  핵심 흐름, 고객 요구, 상담원 발화, 폭언 유형 등이 포함되며,  
  **간단 요약**과 **상세 요약** 두 가지 버전으로 제공되어 상담원의 필요에 따라 선택할 수 있습니다.  
  이를 통해 상담원의 **후처리 업무 부담을 줄이고 효율성을 향상**시킵니다.

<table>
<tr>
  <td style="text-align:center; font-weight:bold;">
    서비스 흐름도
  </td>
  <td style="text-align:center; font-weight:bold;">
    서비스 구성도
  </td>
</tr>
<tr>
  <td>
    <img src="https://github.com/user-attachments/assets/b29792a6-de6f-4cbc-accb-3bdbeb95cd7f" width="600">
  </td>
  <td>
    <img src="https://github.com/user-attachments/assets/36a23a9a-a7b4-42b5-949b-27ab71275f63" width="600">
  </td>
</tr>
</table>


- ⚖️ **법률 상담 챗봇**  
  **120다산콜재단의 악·강성민원 감정노동자보호 가이드 문서**를 학습한 **RAG 기반 챗봇**이  
  **관련 법률 조항과 대응 방안**을 대화 형식으로 안내하며,  
  **벡터DB 검색(Pinecone)** 과 **AI 모델(OpenAI GPT)** 을 결합해 **신뢰도 높은 자문**을 제공합니다.

<table>
<tr>
  <td style="text-align:center; font-weight:bold;">
    서비스 흐름도
  </td>
  <td style="text-align:center; font-weight:bold;">
    서비스 구성도
  </td>
</tr>
<tr>
  <td>
    <img src="https://github.com/user-attachments/assets/8ee0a64b-b00c-464f-b496-904c16602c09" width="600">
  </td>
  <td>
    <img src="https://github.com/user-attachments/assets/03dccbb0-d590-4d12-a4df-fa0a48da90b8" width="600">
  </td>
</tr>
</table>

<br />

---

## ✨ 기대효과 및 활용분야

**실시간 폭언 차단**으로 상담원의 심리적 안전망을 마련하고,  
**자동 요약 기능**으로 상담 후처리 부담을 경감합니다.  
또한 **법률 상담 챗봇**을 통해 구체적인 대응 방안을 제공합니다.


이 시스템은 **상담원뿐만 아니라 교사·공직자 등 감정노동 직군**으로 확장 가능하며,  
**국가 차원의 소버린 AI 전략**과도 부합해 **사회적 파급 효과**를 창출할 수 있습니다.
<table>
  <tr>
    <td>
      <img src="https://github.com/user-attachments/assets/42798a83-9075-4db3-921f-ae37f32ae587" width="600">
    </td>
    <td>
      <img src="https://github.com/user-attachments/assets/1e75d20a-dd96-4ec2-9c09-bfb888f665a4" width="600">
    </td>
  </tr>
</table>

<table>
  <tr>
    <td>
      <img src="https://github.com/user-attachments/assets/8a10ced0-1fc3-4f10-9e8a-fff1c43409ee" width="600">
    </td>
    <td>
      <img src="https://github.com/user-attachments/assets/b94a1dfa-4a6c-444d-9adf-c75d2dec2b42" width="600">
    </td>
  </tr>
</table>

---

## <img src="https://github.com/user-attachments/assets/d279eded-37a1-4816-a04d-e5fee577b069" alt="YouTube" width="20"/> 작품 소개 영상

[![온음 시연영상](https://github.com/user-attachments/assets/039e13b2-02fb-4964-a10f-f846df709dd7)](https://youtu.be/4NJF_fCZPIM?si=C-7njz59XTcrmEes)

---

## 👥 팀원 소개

| <img src="https://avatars.githubusercontent.com/u/145523888?v=4" width="120px;" alt=""/> | <img src="https://avatars.githubusercontent.com/u/144589197?v=4" width="120px;" alt=""/> | <img src="https://avatars.githubusercontent.com/u/144600629?v=4" width="120px;" alt=""/> | <img src="https://avatars.githubusercontent.com/u/90364609?v=4" width="120px;" alt=""/> | <img src="https://avatars.githubusercontent.com/u/102063992?v=4" width="120px;" alt=""/> |
| :----------------------------------------------------------: | :----------------------------------------------------------: | :----------------------------------------------------------: | :----------------------------------------------------------: | :----------------------------------------------------------: |
| [**이송미**](https://github.com/soooong7) | [**전효민**](https://github.com/hyom1n) | [**조예영**](https://github.com/sylvia1213) | [**오세은**](https://github.com/ose0221) | [**최현지**](https://github.com/hyeonjichoi21) |
| • 팀장 <br> • 백엔드 · AI(폭언 필터링, 요약)<br>• CI/CD(AI) | • 프론트엔드 | • 프론트엔드 | • 백엔드 · AI(요약) | • 백엔드 · AI(챗봇)<br>• 서버 구축 <br>• CI/CD(백엔드)|


---

## 🛠 사용 기술 스택

| 구분               | 사용 기술 및 도구                                                    |
|:------------------|:-----------------------------------------------------------------|
| **Backend**       | SpringBoot, MySQL, MongoDB, Elasticsearch, FastAPI, WebSocket / SSE |
| **Frontend**      | React, WebSocket / SSE                                            |
| **AI & Data**     | 욕설/성희롱/협박 감지 - KoBERT,<br/>STT - Google Cloud Speech-to-Text,<br/>상담요약 - OpenAI gpt-4o, Gemini 2.5 flash,<br/>RAG 기반 챗봇 - OpenAI gpt3-small, Pinecone |
| **Infra & DevOps**| AWS EC2, RDS, Route53, Nginx, Docker, Docker Compose, GitHub Actions (CI/CD), Vercel |
| **Communication tools** | Github, Notion, Discord, Google sheet                              |
| **WebRTC Communication**        | Twilio                                                             |

---

## 🖥 시스템 구성도

### 🔹 **아키텍처 구조**
<img src="https://github.com/user-attachments/assets/f114a2c5-f2b3-439c-87ea-32802157fe92" style="width:100%; height:auto;" />

### 🔹 **ERD**
<img src="https://github.com/user-attachments/assets/c2abbc6b-91ff-4df5-b6f5-2b66a3fecf7a" style="width:100%; height:auto;" />

## 🖥 핵심 소스코드

<details>
  <summary><h3>WebSocketProvider를 통한 전역 상태 관리</h3></summary>

```tsx
// WebsocketContext.js 
useEffect(() => {
  ws.onmessage = (event) => {
    switch (event.type) {
      case "stt":
        // [STT] 수신됨
        console.log("🟪 [STT] 수신됨", event.data.payload);
        const { track, script, isFinal, isAbuse, abuseType } = event.data.payload;
        setCallLogs((prevLogs) => {
          const lastLogIndex = prevLogs.length - 1;
          const newLog = { track, script, isFinal, isAbuse, abuseType };

          // 마지막 로그가 현재 트랙의 중간 결과일 경우 덮어쓰기
          if (
            lastLogIndex >= 0 &&
            prevLogs[lastLogIndex].track === track &&
            !prevLogs[lastLogIndex].isFinal
          ) {
            // 중간 결과 업데이트 (React 불변성 유지)
            const updatedLogs = [...prevLogs];
            updatedLogs[lastLogIndex] = newLog;
            return updatedLogs;
          } else {
            // 새로운 로그로 추가
            return [...prevLogs, newLog];
          }
        });
        break;
      // ...
    }
  };
}, []);

export const WebSocketProvider = ({ children }) => {
  // Twilio + WS 소켓 종료
  // 통화 및 WebSocket 모두 종료
  const endCallAndDisconnect = () => {
    try {
      const conn = twilioConnectionRef.current;
      if (conn?.disconnect && conn.status?.() !== "closed") {
        conn.disconnect(); // 1: 일반 종료
      } else if (twilioDeviceRef.current?.disconnectAll) {
        twilioDeviceRef.current.disconnectAll(); // 2: 모든 연결 종료
      } else {
        console.warn("No Twilio refs, fallback to WS close");
        endConnectWebSocket();
      }
    } catch (e) {
      console.error("Twilio disconnect error:", e);
      twilioDeviceRef.current?.disconnectAll?.();
    }
    setIsCallEnded(true);

    // 안전망: Twilio 이벤트가 안 오면 일정 시간 뒤 강제 종료
    setTimeout(() => {
      if (wsRef.current?.readyState !== WebSocket.OPEN) {
        console.log("💣 Fallback closing ws");
        wsRef.current.close();
      }
    }, 1500);
  };
};
```
</details> 


<details> <summary><h3>SSE 기반 챗봇 응답 처리 구조</h3></summary>
  
```js
// Chatbot.js
// --- 공용 SSE 진입 ---
const openSseAndStream = ({ url, sessionId }) => {
  const which = activeTab === '일반' ? 'general' : 'consult';
  const eventSource = new EventSource(url);
  let buffer = '';

  const replaceLoadingWith = (text) => {
    setCurrentChatMap((prev) => {
      const msgs = prev[sessionId] || [];
      const idx = msgs.findIndex(m => m.loading);
      if (idx !== -1) {
        const updated = { ...msgs[idx], fromUser: false, text };
        const updatedMsgs = [...msgs];
        updatedMsgs[idx] = updated;
        return { ...prev, [sessionId]: updatedMsgs };
      }
      return prev;
    });
  };

  // 제목 이벤트 즉시 반영
  eventSource.addEventListener('title', (ev) => {
    try {
      const payload = JSON.parse(ev.data);
      const sid = payload?.sessionId ?? sessionId;
      const title = payload?.title;
      applySessionTitle(which, sid, title);
    } catch (e) {}
  });

  // 메시지 스트림 처리
  eventSource.addEventListener('message', (event) => {
    const chunk = event.data;

    if (chunk === '[END]') {
      buffer = buffer.trim();
      try {
        const jsonStart = buffer.indexOf('{');
        const jsonEnd = buffer.lastIndexOf('}') + 1;
        const parsed = JSON.parse(buffer.substring(jsonStart, jsonEnd).trim());
        if (parsed.answer) {
          replaceLoadingWith(formatBotMessage(parsed.answer, parsed.sourcePages));
        } else {
          replaceLoadingWith('❗️응답 형식 없음');
        }
      } catch (e) {
        replaceLoadingWith('❗️응답 파싱 실패');
      }
      eventSource.close();
      return;
    }

    if (chunk.startsWith('[JSON]')) {
      buffer = chunk.replace('[JSON]', '').trim();
    }
  });

  eventSource.onerror = () => {
    replaceLoadingWith('❗️연결 실패');
    eventSource.close();
  };
};
```

</details> 

<details>
  <summary><h3>WebRTC 기반 실시간 통화 구현</h3></summary>

```java
// TwilioVoiceTokenController.java
@Slf4j
@RestController
@RequiredArgsConstructor
@RequestMapping("/api/token")
@Tag(
        name = "TwilioVoiceToken",
        description = "Twilio 음성 통화를 위한 액세스 토큰 발급 API. 브라우저 클라이언트가 Twilio Voice SDK를 사용해 전화를 수·발신할 수 있도록 토큰을 발급합니다."
)
public class TwilioVoiceTokenController {
    @Value("${twilio.account.sid}")
    private String TWILIO_ACCOUNT_SID;

    @Value("${twilio.api.key}")
    private String TWILIO_API_KEY;

    @Value("${twilio.api.secret}")
    private String TWILIO_API_SECRET;

    @GetMapping
    public ApiResponse<TwilioTokenResponseDTO> getToken(
        @UserId Long userId
    ){
        String fixedIdentity = "browserUser"; // 고정 ID - 단일 사용자로 구현, 추후 상담사 분배 시에 다중 사용자로 확장 가능
        VoiceGrant grant = new VoiceGrant();
        grant.setIncomingAllow(true);

        AccessToken token = new AccessToken.Builder(
                TWILIO_ACCOUNT_SID,
                TWILIO_API_KEY,
                TWILIO_API_SECRET
        )
                .identity(fixedIdentity)
                .grant(grant)
                .ttl(3600)
                .build();

        log.info("access token: {}", token.toString());
        log.info("userId : {}", userId);

        TwilioTokenResponseDTO twilioTokenResponseDTO = TwilioTokenResponseDTO.of(token.toJwt(),  userId);
        return ApiResponse.onSuccess(twilioTokenResponseDTO);
    }
}

// TwilioWebhookController.java
@Slf4j
@RestController
@RequiredArgsConstructor
@RequestMapping("/twilio")
@Tag(
        name = "TwilioWebhook",
        description = "Twilio 음성 통화 Webhook API. 인바운드 콜 수신 시 브라우저 클라이언트와 WebSocket을 연결하고 통화 흐름(TwiML)을 제어합니다."
)
public class TwilioWebhookController {
    private static final String BROWSER_CLIENT_ID = "browserUser";
    private static final String WS_URL ="wss://callprotect.site/ws/audio";

    @PostMapping(value = "/voice", consumes = MediaType.APPLICATION_FORM_URLENCODED_VALUE, produces = MediaType.APPLICATION_XML_VALUE)
    public String onIncomingCall(@RequestParam Map<String, String> params) {
        log.info("params: {}", params);
        log.info("☆ Inbound Call - From: {}", params.get("From"));
        log.info("☆ Inbound Call - CallSid: {}", params.get("CallSid"));
        String callerNumber = params.get("From");
        String inboundCallSid = params.get("CallSid");

        Client clientVerb = new Client.Builder(BROWSER_CLIENT_ID) // 브라우저 Client ID - TwilioVoiceTokenController의 fixedIdentity와 일치해야 함
            .parameter(new Parameter.Builder()
                .name("initialCallSid")
                .value(inboundCallSid)
                .build())
            .build();

        VoiceResponse response = new VoiceResponse.Builder()
                .say(new Say.Builder("산업안전보건법에 따라 고객응대 근로자 보호 조치가 시행되고 있습니다." +
                        "세 번 이상 폭언이 감지되면 에이아이에 의해 통화가 자동 종료됩니다.")
                    .voice(Say.Voice.ALICE)
                    .language(Say.Language.KO_KR)
                    .build())
                .start(new Start.Builder()
                        .stream(new Stream.Builder()
                                .url(WS_URL)
                                .track(Stream.Track.BOTH_TRACKS)
                                .parameter(new com.twilio.twiml.voice.Parameter.Builder()
                                    .name("primaryCallSid")
                                    .value(inboundCallSid)
                                        .build())
                                .parameter(new com.twilio.twiml.voice.Parameter.Builder()
                                        .name("callerNumber")
                                        .value(callerNumber)
                                        .build())
                                .build())
                        .build())
                .dial(new Dial.Builder()
                        .timeout(30) // 30초 안에 응답 없으면 통화 불가 안내 멘트
                        .client(clientVerb)
                        .build())
                .say(new Say.Builder("지금은 통화가 불가능한 시간입니다. 나중에 다시 걸어주세요.") // 안내 멘트 수정 예정
                        .voice(Say.Voice.ALICE)
                        .language(Say.Language.KO_KR)
                        .build())

                .build();

        return response.toXml(); // TwiML 반환
    }
}
```
</details> 


<details>
  <summary><h3>상담 음성 STT</h3></summary>

```java
// ShoutingDetector.java
private ResponseObserver<StreamingRecognizeResponse> createResponseObserver(String sessionId){
		return new ResponseObserver<>() {
			public void onStart(StreamController controller) {
				log.info("🎤 STT 시작됨: {} [{}]", sessionId, track);
			}

			public void onResponse(StreamingRecognizeResponse response) {
				for (StreamingRecognitionResult result : response.getResultsList()) {
					if (result.getAlternativesCount() > 0) {
						String transcript = result.getAlternatives(0).getTranscript();
						boolean isFinal = result.getIsFinal();

						log.info("💬 [{}][{}] {}", isFinal ? "최종" : "중간",
							track == CallTrack.INBOUND ? "고객" : "상담원",
							transcript);

						try {
							if (isFinal) { // 최종 결과
								String trimmedTranscript = transcript.trim();

								// 중복 방지 - 이전 저장값과 동일한 경우 저장 생략 (INBOUND만 적용)
								if(isDuplicate(trimmedTranscript)) {
									log.debug("[중복 제거] 동일한 최종 텍스트는 무시됨: {}", trimmedTranscript);
									continue;
								}

								boolean isAbuse = NOT_ABUSIVE;
								String abuseType = ABUSIVE_TYPE_NORMAL;

								// INBOUND 트랙만 FastAPI를 통한 욕설 분석
								if(track == CallTrack.INBOUND) {
									var analysis = fastClient.sendTextToFastAPI(trimmedTranscript);
									isAbuse = analysis.isAbuse();
									abuseType = analysis.getType();
									if (isAbuse) {
										log.info("[{}] INBOUND 욕설 감지 결과 → isAbuse: {}, type: {}", CallTrack.INBOUND, isAbuse, abuseType);
									}
								} else { // // OUTBOUND 트랙은 욕설 분석 건너뜀
									log.info("[{}] 상담원 발화는 욕설 분석을 건너뜀", track);

								}

								// sttLog 최종 저장
								CallSttLog savedLog = callSttLogService.saveTranscriptLog(
									callSessionId,
									track,
									trimmedTranscript,
									true,
									isAbuse,
									abuseType
								);
								log.info("MongoDB에 CallSttLog 저장 완료: callSessionId={}, track={}, script={}", callSessionId, track, trimmedTranscript);



								// INBOUND (고객) 스크립트 누적 및 욕설 감지 후 처리
								if (track == CallTrack.INBOUND) {
									// transcriptBuilder 중복 누적 방지
									if (!trimmedTranscript.equals(lastSavedFinalTranscript)) {
										transcriptBuilder.append(trimmedTranscript).append(" ");
										lastSavedFinalTranscript = trimmedTranscript;
									}

									// 욕설 감지 시 total abuse cnt 업데이트
									if (isAbuse) {
										log.info("STT 결과 욕설 감지 - (isAbuse={}) / CallSession total_abuse_cnt 업데이트 시도 - CallSessionId={}", isAbuse, callSessionId);
										callSessionService.incrementTotalAbuseCnt(callSessionId);
										log.info("🍀 고객 발화 필터링됨");
										callLogService.updateAbuse(callSessionId, track);
										sendBeepIfAllowed(BEEP_DURATION_MS);
									}
								} else { // OUTBOUND (상담원) 스크립트 누적
									// 중복 누적 방지 없이 무조건 추가
									transcriptBuilder.append(trimmedTranscript).append(" ");
									lastSavedFinalTranscript = trimmedTranscript;
								}

								// 클라이언트에 최종 STT 결과 전송
								CallSttLogResponseDTO finalResponse = new CallSttLogResponseDTO(DATA_TYPE_STT, savedLog);

								if (userId != null) {
									sttWebSocketHandler.sendSttToClient(userId, finalResponse);
								}

								partialFinalTranscript = null; // 최종 처리 후 중간 텍스트 초기화

							} else { // 중간 결과는 DB 저장 없이 클라이언트 뷰에만 보여줌
								CallSttLog interimLog = CallSttLog.builder()
									.callSessionId(callSessionId)
									.track(track)
									.script(transcript)
									.isFinal(false)
									.isAbuse(false)
									.abuseType(ABUSIVE_TYPE_NORMAL)
									.abuseCnt(0)
									.build();

								// 클라이언트에 중간 STT 결과 전송
								CallSttLogResponseDTO interimResponse = new CallSttLogResponseDTO(DATA_TYPE_STT, interimLog);

								if (userId != null) {
									sttWebSocketHandler.sendSttToClient(userId, interimResponse);
								}

								partialFinalTranscript = transcript;
							}

						} catch (Exception e) {
							log.error("❌ FastAPI 전송 오류", e);
						}
					}
				}
			}

			public void onError(Throwable t) {
				log.error("[{}] STT 오류", track, t);
			}

			public void onComplete() {
				log.info("[{}] STT 완료", track);
			}
		};
	}
```
</details> 

<details>
  <summary><h3>고함 감지 및 필터링</h3></summary>

```java
// SttContext.java
private void calculateBaselineAndSetThreshold() {
		if (basePitches.isEmpty() || baseVolumes.isEmpty()) {
			log.warn("베이스라인 수집치 부족 → default 임계값 유지");
			setThresholdsFrom(provisionalBasePitchHz, provisionalBaseVolumeDb,false);
			return;
		}

		// 정렬
		Collections.sort(basePitches);
		Collections.sort(baseVolumes);

		// 중앙값 추출
		double medianBasePitch = basePitches.get(basePitches.size() / 2);
		double medianBaseVolume = baseVolumes.get(baseVolumes.size() / 2);

		setThresholdsFrom(medianBasePitch, medianBaseVolume,true);


		log.info("✅ 기준 피치 설정 완료: {}Hz, 고함 임계값: {}Hz", medianBasePitch, shoutingPitchThreshold);
		log.info("✅ 기준 볼륨 설정 완료: {}dB, 고함 임계값: {}dB", medianBaseVolume, shoutingVolumeThreshold);
	}
	
private void setThresholdsFrom(double basePitch, double baseVolume, boolean markBaselineSet) {
	this.isHighPitchUser = (basePitch > PITCH_BOUNDARY);
	double pitchIncreaseFactor = this.isHighPitchUser ? PITCH_INCREASE_FACTOR_HIGH : PITCH_INCREASE_FACTOR_LOW;

	this.shoutingPitchThreshold  = basePitch  * pitchIncreaseFactor;
	this.shoutingVolumeThreshold = baseVolume + DB_BOUNDARY;

	if (markBaselineSet) {
		isBaselineSet.set(true);
		log.info("✅ 개별 기준 임계값 적용: basePitch={}Hz, baseVol={}dB → thresPitch={}Hz, thresVol={}dB",
			basePitch, baseVolume, shoutingPitchThreshold, shoutingVolumeThreshold);
	} else {
		log.info("⏳ 임시 임계값 적용(default: basePitch={}Hz, baseVol={}dB → thresPitch={}Hz, thresVol={}dB",
			basePitch, baseVolume, shoutingPitchThreshold, shoutingVolumeThreshold);
	}
}
```
</details> 

<details>
  <summary><h3>폭언 감지 및 필터링</h3></summary>

```python
# detect.py
# 설정
LABEL_NAMES = ["욕설", "성희롱", "협박", "정상"]
MODEL_PATH = "./model/kobert_v12"
THRESHOLD = 0.9
DELTA_THRESHOLD = 0.2
NORMAL_CLASS_INDEX = 3

# 단어 사전 로딩
with open("data/badwords.json", encoding="utf-8") as f:
    BADWORDS = set(json.load(f)["badwords"])

with open("data/force_block.json", encoding="utf-8") as f:
    FORCE_BLOCK = set(json.load(f)["force_block"])

# 전처리
def normalize(text: str) -> str:
    return re.sub(r"[^가-힣a-zA-Z0-9\s]", "", text).lower().strip()

def contains_badword(norm_text: str):
    return [word for word in BADWORDS if word in norm_text]

# KoBERT 모델 정의
class KoBERTClassifier(BertPreTrainedModel):
    def __init__(self, config):
        super().__init__(config)
        self.bert = BertModel(config)
        self.dropout = nn.Dropout(0.2)
        self.classifier = nn.Linear(config.hidden_size, config.num_labels)

    def forward(self, input_ids=None, attention_mask=None, token_type_ids=None):
        outputs = self.bert(input_ids=input_ids, attention_mask=attention_mask, token_type_ids=token_type_ids)
        pooled_output = self.dropout(outputs.pooler_output)
        logits = self.classifier(pooled_output)
        return logits

# 모델 및 토크나이저 로딩
tokenizer = AutoTokenizer.from_pretrained("monologg/kobert", trust_remote_code=True)
config = AutoConfig.from_pretrained(MODEL_PATH)
model = KoBERTClassifier.from_pretrained(MODEL_PATH, config=config)
model.eval()

# 예측 함수
def predict(text: str):
    inputs = tokenizer(text, return_tensors="pt", padding="max_length", truncation=True, max_length=64)
    with torch.no_grad():
        logits = model(**inputs)
        probs = F.softmax(logits, dim=1)[0].tolist()
    pred_idx = int(torch.argmax(logits, dim=1).item())
    pred_label = LABEL_NAMES[pred_idx]
    return probs, pred_label, pred_idx

# 최종 판별 함수
def is_abuse(text: str):
    norm = normalize(text)
    detected = contains_badword(norm)

    # 강제 차단 단어 우선 감지
    if any(word in FORCE_BLOCK for word in detected):
        return True, detected, "욕설"

    # 모델 예측
    probs, pred_label, pred_idx = predict(text)
    max_prob = max(probs[:NORMAL_CLASS_INDEX])
    normal_prob = probs[NORMAL_CLASS_INDEX]
    delta = max_prob - normal_prob

    is_abusive = (
        pred_idx != NORMAL_CLASS_INDEX and
        max_prob > THRESHOLD and
        delta > DELTA_THRESHOLD and
        normal_prob < 0.3
    )

    # 오탐 보정 조건
    if is_abusive and not detected:
        if max_prob < 0.97 or normal_prob > 0.2:
            is_abusive = False

    # 정상 판단
    if not is_abusive and not detected:
        return False, [], "정상"

    return is_abusive, detected, pred_label

```
</details> 


<details>
  <summary><h3>AI 상담요약</h3></summary>

```java
// CallSessionServiceImpl.java
@Override
    public String generateSummaryByOpenAi(Long callSessionId, Long userId) {
        CallSession session = findCallSessionByIdAndUserId(callSessionId, userId);

        if (session.getSummarySimple() != null && !session.getSummarySimple().isBlank()) {
            log.info("✅ 기존 요약 반환 - CallSession ID: {}", callSessionId);
            return session.getSummarySimple();
        }

        try {
            List<CallSttLog> sttLogs = callSttLogService.getAllBySessionId(callSessionId);

            if (sttLogs.isEmpty()) {
                log.warn("⚠️ STT 로그 없음 - CallSession ID: {}", callSessionId);
                throw new CallSessionSummaryGenerationException(ErrorStatus.CANT_SUMMARY_CALL_STT_LOG);
            }

            boolean hasMeaningfulScript = sttLogs.stream()
                    .anyMatch(log -> log.getScript() != null && !log.getScript().trim().isEmpty());

            if (!hasMeaningfulScript) {
                log.warn("⚠️ 유효한 대화 내용 없음 - CallSession ID: {}", callSessionId);
                throw new CallSessionSummaryGenerationException(ErrorStatus.CALL_STT_LOG_NO_MEANINGFUL_CONTENT);
            }

            String fullConversation = sttLogs.stream()
                    .filter(log -> {
                        String script = log.getScript();
                        return script != null && !script.trim().isEmpty();
                    })
                    .map(log -> {
                        String script = log.getScript().trim();
                        String speaker = (log.getTrack() == CallTrack.INBOUND) ? "고객" : "상담원";
                        return String.format("[%s]: %s", speaker, script);
                    })
                    .collect(Collectors.joining("\n"));

            String summary = openAiSummaryService.summarize(fullConversation);
            log.info("✅ 요약 생성 완료 - CallSession ID: {}", callSessionId);

            session.updateSummarySimple(summary);
            callSessionRepository.save(session);

            return summary;

        } catch (Exception e) {
            log.error("❌ 요약 생성 중 오류 - CallSession ID: {}, 메시지: {}", callSessionId, e.getMessage(), e);
            throw new CallSessionSummaryGenerationException(ErrorStatus.SUMMARY_AI_OPENAI_API_ERROR);
        }
    }

    @Override
    public CallSessionResponseDTO.CallSessionSummaryResponseDTO createCallSessionSummaryByOpenAi(Long callSessionId, Long userId) {
        String summaryText = generateSummaryByOpenAi(callSessionId, userId);

        return CallSessionResponseDTO.CallSessionSummaryResponseDTO.builder()
                .callSessionId(callSessionId)
                .summaryText(summaryText)
                .build();
    }

    @Override
    @Transactional
    public String generateSummaryByGemini(Long callSessionId, Long userId) {
        CallSession session = findCallSessionByIdAndUserId(callSessionId, userId);

        // 중복 생성 방지
        if (session.getSummaryDetailed() != null && !session.getSummaryDetailed().isBlank()) {
            log.info("CallSession (ID: {})에 이미 요약 완료. Gemini api 호출 없이 기존 요약 내용 반환", callSessionId);
            return session.getSummaryDetailed();
        }

        String summaryText;

        try {
            // 전체 스크립트 조회
            List<CallSttLog> scriptLogs = callSttLogService.getAllBySessionId(callSessionId);

            if (scriptLogs.isEmpty()) {
                log.warn("CallSession (ID: {})에 최종 STT 로그가 없어 요약을 생성할 수 없습니다.", callSessionId);
                throw new CallSessionSummaryGenerationException(ErrorStatus.CANT_SUMMARY_CALL_STT_LOG);
            }

            // 하나의 전체 스크립트로 가공
            String fullConversation = scriptLogs.stream()
                .map(log -> {
                    String speaker = log.getTrack().toString().equals("INBOUND") ? "고객" : "상담원";
                    return String.format("[%s]: %s", speaker, log.getScript());
                })
                .collect(Collectors.joining("\n"));

            boolean hasMeaningfulScript = scriptLogs.stream()
                .anyMatch(log -> log.getScript() != null && !log.getScript().trim().isEmpty());

            if (!hasMeaningfulScript) {
                log.warn("CallSession (ID: {})에 의미 있는 대화 내용이 없어 요약을 생성할 수 없습니다.", callSessionId);
                throw new CallSessionSummaryGenerationException(ErrorStatus.CALL_STT_LOG_NO_MEANINGFUL_CONTENT);
            }

            summaryText = geminiService.summarizeCallScript(fullConversation);
            log.info("CallSession (ID: {}) 요약 생성 완료.", callSessionId);

            session.updateSummaryDetailed(summaryText);
            log.info("summaryGemini: {}", summaryText);
            callSessionRepository.save(session);
            return summaryText;

        } catch (Exception e) {
            log.error("CallSession (ID: {}) 요약 생성 중 오류 발생: {}", callSessionId, e.getMessage(), e);
            throw new CallSessionSummaryGenerationException(ErrorStatus.SUMMARY_AI_GEMINI_API_ERROR);
        }
    }
```
</details> 


<details>
  <summary><h3>일반 채팅 & 상담별 채팅</h3></summary>

```java
// (Call)ChatStreamController.java
@Slf4j
@RestController
@RequiredArgsConstructor
@RequestMapping("/api/call-chat")
@Tag(name = "CallChatStream", description = "상담별 채팅 질문 전송 관련 API")
public class CallChatStreamController {

    private final ChatbotClient chatbotClient;

    private final CallChatLogService callChatLogService;
    private final CallChatSessionService callChatSessionService;
    private final TokenProvider tokenProvider;

    // 08/13 추가: STT 로그 조회용
    private final CallSttLogService callSttLogService;

    @Operation(
            summary = "상담별 채팅 질문 전송 API",
            description ="상담원이 입력한 법률 질문을, 문맥을 유지하고 있는 챗봇에게 전송하고 응답을 받아옵니다."
    )
    @GetMapping(value = "/stream", produces = MediaType.TEXT_EVENT_STREAM_VALUE)
    public Flux<String> streamCallChat(
            @Parameter(description = "대화가 기록될 CallChatSession ID", required = true)
            @RequestParam Long callChatSessionId,

            @Parameter(description = "질문 내용", required = true)
            @RequestParam String question,

            @Parameter(description = "JWT 토큰", required = true)
            @RequestParam String token
    ) {
        // 1) JWT → userId
        Long userId = tokenProvider.validateAndGetUserId(token);

        // 2) 세션 소유권 검증
        CallChatSession session = callChatSessionService.getSessionById(callChatSessionId);
        if (!session.getUser().getId().equals(userId)) {
            throw new CallChatGeneralException(ErrorStatus.CALLCHAT_SESSION_FORBIDDEN);
        }

        // Scripts 구성 (callchatbot 서비스 로직 재사용)
        List<Map<String, String>> contextScripts = List.of(); // 기본 빈 리스트
        if (session.getCallSession() != null) {
            Long callSessionId = session.getCallSession().getId();
            List<CallSttLog> logs = callSttLogService.getAllBySessionId(callSessionId);

            // (A) 전부 전송 (2번과 동일)
            List<Map<String, String>> scripts = new ArrayList<>(logs.size());
            for (CallSttLog log : logs) {
                scripts.add(Map.of(
                        "speaker", log.getTrack().name(),  // INBOUND / OUTBOUND
                        "text", log.getScript()
                ));
            }

            // (옵션) 페이로드 최적화: abuse 구간 ±2턴 + 총 6000자 컷
            // scripts = trimByAbuseWindowAndLength(logs, 2, 6000);

            contextScripts = scripts;
        }

        StringBuilder jsonBuffer = new StringBuilder();

        // 3) FastAPI 호출
        return chatbotClient.sendChatRequest(
                        "/ai/callchat/stream",
                        Map.of(
                                "session_id", callChatSessionId,   // 백엔드 메모리 키로 쓰고 싶으면 이 값 활용
                                "question", question,
                                "context_scripts", contextScripts
                        )
                )
                .map(raw -> {                                            // data: 조건부 제거
                    String s = raw == null ? "" : raw.trim();
                    if (s.startsWith("data:")) s = s.substring(5).trim();
                    return s;
                })
                .filter(s -> !s.isEmpty())
                .doOnNext(chunk -> {
                    if ("[END]".equals(chunk)) return;                  // 그대로 프론트로
                    if (chunk.startsWith("[ERROR]")) {                  // 에러 로그
                        log.error("SSE ERROR from FastAPI: {}", chunk);
                        return;
                    }
                    if (chunk.startsWith("[JSON]")) {                   // 버퍼 초기화 후 저장
                        jsonBuffer.setLength(0);
                        jsonBuffer.append(chunk.substring("[JSON]".length()).trim());
                    }
                })
                .doOnError(e -> log.error("SSE proxy error", e))        // 에러 핸들링
                .doOnComplete(() -> {
                    try {
                        if (jsonBuffer.length() == 0) return;           // JSON 없으면 스킵
                        ObjectMapper mapper = new ObjectMapper();
                        JsonNode node = mapper.readTree(jsonBuffer.toString());

                        String answer = node.has("answer") ? node.get("answer").asText() : "";
                        String sourcePages = (node.has("sourcePages") && !node.get("sourcePages").isNull())
                                ? node.get("sourcePages").toString()
                                : "[]";

                        callChatLogService.saveCallChatLog(
                                callChatSessionId,
                                question,
                                answer,
                                sourcePages
                        );
                    } catch (Exception e) {
                        log.error("❌ 상담별 채팅 저장 실패", e);
                        throw new CallChatGeneralException(ErrorStatus.CALLCHAT_LOG_SAVE_FAILED);
                    }
                })
                .delayElements(Duration.ofMillis(5));
    }
}
```

```python
# rag_chatbotstream.py (해당 코드는 일반 채팅코드. 상담별 채팅코드도 이와 유사함)
# Pinecone에서 query와 유사 문단 검색 후 context와 sourcePages 반환
def retrieve_context(query: str, top_k: int = 2):
    embedding = client.embeddings.create(
        input=[query],
        model="text-embedding-3-small"
    ).data[0].embedding

    results = index.query(vector=embedding, top_k=top_k, include_metadata=True)

    context_blocks = []
    source_pages = []
    for match in results.get("matches", []):
        meta = match.get("metadata", {}) or {}
        typ = (meta.get("유형") or "").strip() or "없음"
        law = (meta.get("관련 법률") or "").strip() or "없음"

        context_blocks.append(
            f"📌 **유형:** {typ}\n"
            f"📖 본문: {meta.get('본문', '')}\n"
            f"⚖ **관련 법률**: {law}\n"
            f"📝 요약: {meta.get('요약', '')}\n"
        )
        # 최종 JSON에서는 '관련법률'(띄어쓰기 없음)
        # '없음'은 제외해 sourcePages 정합성 보장
        if law and law != "없음":
            law_norm = _normalize_law_name(law)  # 추가: 괄호·주석 제거
            source_pages.append({"유형": typ, "관련법률": law_norm})

    return "\n---\n".join(context_blocks), source_pages

# 6. GPT 스트리밍 + JSON 응답 (키워드 기반 법률을 sourcePages 1차 반영)
@router.post("/stream")
async def stream_chat(query: Query):
    # 0) 일상 대화면 즉시 SSE로 응답하고 종료 (모델/RAG 호출 없이)
    if is_smalltalk(query.question):
        async def smalltalk_events():
            payload = {"answer": smalltalk_reply(query.question), "sourcePages": []}
            yield f"data: [JSON]{json.dumps(payload, ensure_ascii=False)}\n\n"
            yield "data: [END]\n\n"
        return EventSourceResponse(smalltalk_events())
    
    # RAG
    context, source_pages_rag = retrieve_context(query.question)
    
   
# 관련법률 중복 제거해주는 함수  
# 법률명 정규화 (괄호·주석 제거)
def _normalize_law_name(law: str) -> str:
    """
    법률명 + 조문번호만 남기고 괄호/주석은 제거
    예: '민원처리법 제23조 (3회 이상 반복 시 종결)' → '민원처리법 제23조'
    """
    if not law:
        return ""
    return re.sub(r"\s*\(.*?\)", "", law).strip()

# 유형, 법률 중복 항목을 제거 
# sourcePages 후처리 (중복 제거, 최대 3개 유지)
def _post_filter_sources(sources, limit=3):
    """
    - 법률명만 기준으로 중복 제거 (유형이 달라도 같은 법률이면 1개만)
    - 지침/가이드 등 비법률도 허용 (요구사항 반영)
    - 괄호 설명 제거(normalize) + ; , 로 묶인 항목 분할
    - 최대 limit개 유지
    """
    out = []
    seen_laws = set()

    for e in sources or []:
        typ = (e.get("유형") or "").strip()
        raw_law = (e.get("관련법률") or "").strip()
        if not typ or not raw_law or raw_law == "없음":
            continue

        # 여러 개 한 줄일 수 있으니 분할
        for lw in [x.strip() for x in re.split(r"[;,]", raw_law) if x.strip()]:
            norm = _normalize_law_name(lw)  # 괄호/주석 제거
            key = norm.lower()
            if not norm:
                continue
            # 법률 기준으로 dedup (유형은 달라도 같은 법률이면 skip)
            if key in seen_laws:
                continue
            seen_laws.add(key)
            out.append({"유형": typ, "관련법률": norm})
            if len(out) >= limit:
                return out

    return out
```
</details> 
