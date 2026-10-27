# Clash Royale 클랜전 듀얼 봇

클랜전 상대가 최근 쓴 덱을 빠르게 조회하는 텔레그램 봇입니다. 닉네임이나 클랜으로 상대를 찾아 최근 클랜전 덱을 보여 줍니다. 듀얼은 라운드별로, 1v1은 전투별로 나옵니다.

- 카드 이미지에 레벨과 챔피언·히어로·진화 표시
- 직접 등록한 내 덱을 상대 덱 다음에 별도 메시지로 표시

## 시작하기

텔레그램 봇 토큰(`@BotFather`의 `/newbot`)과 [Clash Royale API 키](https://developer.clashroyale.com)가 필요합니다.

```bash
pip install -r requirements.txt
```

저장소 루트의 `.env`에 발급받은 값을 넣습니다.

```dotenv
TELEGRAM_BOT_TOKEN=
CR_API_KEY=
```

```bash
python main.py   # 폴링으로 메시지 수신
```

API 요청은 `https://proxy.royaleapi.dev/v1`을 거칩니다. API 키의 허용 IP 설정은 따로 확인이 필요합니다.

## 사용법

봇에게 `/start`를 보내면 사용법이 나옵니다. 검색 결과 목록에서 번호를 보내면 그 플레이어의 최근 클랜전 덱을 조회합니다.

| 입력 | 동작 |
| --- | --- |
| `닉네임` 또는 `/search 닉네임` | 플레이어 검색 |
| `닉네임 클랜이름` | 클랜명으로 결과 좁히기 |
| `clan 클랜이름` | 클랜 검색 → 멤버 선택 |
| `/register #태그` | 내 플레이어 태그 저장 |
| `/setdecks`, `/mydecks` | 내 덱 3개 등록 안내, 확인 |

덱은 카드 이름 8개를 쉼표로, 덱 사이는 `|`로 구분합니다. 등록 정보는 `bot/data/my_decks.json` 한 파일에 저장되며 사용자별로 나뉘지 않습니다.

## Railway 배포

Railway에 저장소를 연결하고 Variables에 `TELEGRAM_BOT_TOKEN`, `CR_API_KEY`를 넣습니다. [`railway.toml`](railway.toml)이 `python main.py`를 복제본 1개로 실행합니다. 덱 데이터용 영속 저장소는 설정돼 있지 않아 재배포하면 사라질 수 있습니다.

## 라이선스

LICENSE 파일이 없습니다. 라이선스는 확인이 필요합니다.
