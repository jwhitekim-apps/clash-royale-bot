# Clash Royale 클랜전 듀얼 봇

클랜전 상대가 최근 쓴 덱을 조회하는 텔레그램 봇입니다. 닉네임이나 클랜으로 상대를 찾아 듀얼은 라운드별로, 1v1은 전투별로 덱을 보여 줍니다.

- 카드 이미지에 레벨과 챔피언·히어로·진화 표시
- 직접 등록한 내 덱을 상대 덱 다음에 별도 메시지로 표시

## 시작하기

Python 3.9 이상과 pip, `@BotFather`에서 발급받은 텔레그램 봇 토큰, [Clash Royale API 키](https://developer.clashroyale.com)가 필요합니다. API 키는 요청에 사용하는 `https://proxy.royaleapi.dev/v1` 프록시의 허용 IP 설정에 맞춰 준비합니다.

저장소 루트에서 아래 값을 발급받은 값으로 바꿔 실행합니다.

```bash
python -m pip install -r requirements.txt
export TELEGRAM_BOT_TOKEN='발급받은 봇 토큰'
export CR_API_KEY='발급받은 API 키'
python main.py
```

텔레그램에서 만든 봇에게 `/start`를 보내 사용법을 확인합니다. 상대 닉네임을 보내고 검색 결과의 번호를 선택하면 최근 클랜전 덱을 조회합니다.

## 라이선스

LICENSE 파일이 없습니다. 라이선스는 확인이 필요합니다.
