# 미국의 가상자산 불공정거래 규율 체계

> Pump.fun 불공정거래 리스크 분석 프로젝트 — 법적 근거 정리
> 작성일: 2026-04-17 | 최종 검증: 2026-04-17

---

## 핵심 명제

**"가상자산이 증권이 아니라고 해서 불공정거래가 허용되는 것은 아니다."**

미국은 가상자산 불공정거래를 세 가지 독립적인 법적 경로로 규율한다. 각 경로는 서로 다른 법률, 관할기관, 적용 요건을 가지며, 대상 자산이 증권인지 여부와 무관하게 최소 하나의 경로가 적용될 수 있다.

```
가상자산 불공정거래
        │
        ├─ 증권인가? ── YES → SEC (Securities Act, Exchange Act)
        │             NO ↓
        ├─ 상품인가? ── YES → CFTC (Commodity Exchange Act)
        │             불확실 ↓
        └─ 기망인가? ── YES → DOJ (Wire Fraud, 18 U.S.C. §1343)
                              ↑ 자산 분류와 무관
```

---

## 경로 1: DOJ — Wire Fraud (자산 분류와 무관한 형사 처벌)

### 법적 근거

- **18 U.S.C. §1343 (Wire Fraud)**: "인터넷 등 통신수단을 이용하여, 기망(scheme to defraud)에 의해 금전 또는 재산을 취득"하는 행위를 처벌. 최대 20년 징역.
- **18 U.S.C. §1349 (Conspiracy)**: Wire fraud 공모. 본범과 동일한 형량.

### 핵심 특징

Wire fraud의 가장 중요한 특징은 **대상 자산의 법적 분류를 요건으로 하지 않는다**는 점이다. 해당 자산이 증권인지, 상품인지, 아니면 아무 분류에도 해당하지 않는지를 증명할 필요가 없다. 필요한 것은 (1) 기망의 계획(scheme to defraud), (2) 통신수단의 사용, (3) 금전 또는 재산(money or property)의 취득이다.

다만 이 세 번째 요건("재산")이 중요한 한계선을 형성한다. 단순히 "비윤리적 행위"나 "성실성(integrity)의 훼손"만으로는 부족하고, 피해자의 재산권에 대한 침해가 있어야 한다.

### 주요 사건

**Operation Token Mirrors (2024)**

FBI가 직접 가짜 토큰(NexFundAI)과 위장 회사를 만들어 워시 트레이딩 업체들을 함정 수사한 작전. 2024년 10월, DOJ는 GOTBIT, Vortex, Antier, Contrarian 등 4개 마켓메이킹 업체 소속 10명을 wire fraud + conspiracy to commit wire fraud로 기소했다. 이들은 60개 이상의 가상자산에 대해 워시 트레이딩과 펌프앤덤프를 수행한 혐의를 받으며, 2,500만 달러 이상의 자산이 압수되었다.

이 사건에서 기소의 근거는 wire fraud였다. 대상 토큰들이 증권인지 상품인지는 쟁점이 되지 않았고, "가짜 거래량을 만들어 투자자를 기망하고 금전을 취득했다"는 행위 자체가 기소의 핵심이었다.

> 출처: DOJ Northern District of California; TRM Labs 분석; Fortune 보도 (2024.10.9.)

**Chastain/OpenSea (기소 2023 → 유죄 2023 → 항소심 파기 2025)**

OpenSea 직원 Nathaniel Chastain이 NFT 홈페이지 피처링 정보를 이용해 선매수한 사건. DOJ는 wire fraud + money laundering으로 기소했고, 1심에서 유죄 판결을 받았다.

그러나 **Second Circuit(연방 제2순회항소법원)이 유죄를 vacate(파기)**했다. 핵심 논리는 wire fraud의 "재산(property)" 요건을 충족하지 못한다는 것이었다. 법원은 "사업 행위의 성실성(integrity)을 해친 것"만으로는 wire fraud가 성립하지 않고, "재산권(property rights)"에 대한 침해가 있어야 한다고 판시했다. 이후 DOJ는 기소를 취하했다.

이 판결은 **wire fraud의 한계**를 보여준다. 기망에 의한 금전 취득이 명확하지 않은 유형의 불공정거래(예: 내부정보 이용)에는 wire fraud만으로 충분하지 않을 수 있다.

> 출처: Second Circuit 판결문 (2025.7.31.); Mayer Brown 분석

**Eisenberg/Mango Markets (기소 2023 → 유죄 2024 → 파기 2025)**

솔라나 기반 DeFi 프로토콜 Mango Markets에서 1.1억 달러 규모의 시세조종을 한 사건. DOJ는 wire fraud + commodities fraud + commodities manipulation으로 기소했고, 2024년 4월 1심에서 유죄 판결을 받았다.

그러나 **2025년 5월, 연방지방법원 판사 Arun Subramanian이 전체 유죄 판결을 파기**했다. 주된 이유는 두 가지다:

1. **관할(venue) 문제**: Eisenberg는 푸에르토리코에서 모든 거래를 실행했으며, 뉴욕 남부지구에서 범죄의 "본질적 행위(essential conduct elements)"가 발생했다는 증명이 부족했다.
2. **Wire fraud 요건 불충족**: Mango Markets에는 이용약관(terms of service)이 없었고, 조작을 금지하는 규정도, 대출금 상환 의무도 없었다. 따라서 "중대한 기망적 표시(material misrepresentation)"가 존재하지 않는다고 판단했다.

이 판결은 **DeFi 프로토콜에서의 시세조종에 대한 wire fraud 적용의 어려움**을 보여준다. 규칙이 코드로만 정의되고 별도의 이용약관이 없는 환경에서는, "어떤 규칙을 위반한 기망인가"를 특정하기 어렵다.

> 출처: 판결문 (S.D.N.Y., 2025.5.23.); CoinDesk 보도; Venable LLP 분석

### Pump.fun 적용 시사점

- **러그풀, 워시 트레이딩**처럼 "가짜 정보로 투자자를 속여 금전을 취득"하는 행위는 wire fraud 적용 가능성이 높다. Operation Token Mirrors가 이를 실증했다.
- 반면 **DeFi 환경에서의 시세조종**(Eisenberg 유형)이나 **내부정보 이용**(Chastain 유형)은 wire fraud만으로 기소하기 어려울 수 있다. 두 사건 모두 유죄 판결이 파기되었다.
- 핵심 변수는 "이용약관이나 명시적 규칙의 존재 여부". Pump.fun에 이용약관이 있다면 wire fraud 적용이 더 용이해질 수 있다.

---

## 경로 2: CFTC — Commodity Exchange Act (상품으로 분류되는 경우)

### 법적 근거

- **CEA §6(c)(1)**: 상품 시장에서의 시세조종(manipulation) 금지
- **CFTC Rule 180.1**: 상품 거래에서의 사기(fraud) 금지 — SEC Rule 10b-5를 모델로 한 anti-fraud 규정

### 관할 범위의 변화

CFTC의 가상자산 관할은 2024~2026년에 걸쳐 크게 확대되었다.

**기존 (2024년 이전)**: CFTC의 가상자산 관할은 주로 파생상품(선물, 옵션)에 한정되었다. 현물(spot) 시장에 대해서는 사기·시세조종이 파생상품 시장에 영향을 미치는 경우에 한해 제한적 관할권만 행사했다. 그러나 이 제한적 관할로도 FY2024 기준 전체 enforcement 사건의 약 50%가 디지털 자산 관련이었다.

**2025년 12월 — 현물 시장 관할 확대**: 2025년 12월 4일, CFTC Acting Chairman Caroline D. Pham은 가상자산 현물 거래가 CFTC 등록 거래소에서 최초로 이루어질 것임을 발표했다(CFTC Press Release No. 9145-25). Bitnomial Exchange가 최초의 CFTC 규제 하 현물 가상자산 거래 플랫폼이 되었다. 이는 CFTC의 규제 범위가 파생상품에서 현물 시장으로 확대되는 전환점이다.

**2026년 3월 — Token Taxonomy에 의한 관할 정리**: 아래 "자산 분류 체계"에서 상술.

> 출처: CFTC Press Release No. 9145-25; CFTC FY2024 Enforcement Results; Baker McKenzie 분석

### Pump.fun 적용 시사점

- 밈코인이 "commodity"로 분류될 경우 CEA §6(c)(1)의 시세조종 금지가 직접 적용된다.
- 다만 밈코인이 commodity에 해당하는지는 자동적으로 결정되지 않으며, 아래 Token Taxonomy의 분류 기준에 따른 판단이 필요하다.
- CFTC가 현물 시장으로 관할을 확대한 것은 장기적으로 DEX 거래에 대한 규제 가능성을 높이지만, 현재 시점에서 Pump.fun 같은 해외 DeFi 프로토콜에 대한 직접 적용은 여전히 불확실하다.

---

## 경로 3: SEC — 연방 증권법 (증권으로 분류되는 경우)

### 법적 근거

- **Securities Act §17(a)**: 증권 발행·판매 시 사기 금지
- **Securities Exchange Act §10(b) + Rule 10b-5**: 증권 거래에 관한 사기·기만 금지
- **Securities Exchange Act §9(a)(2)**: 시세조종 금지

### 적용 전제: 해당 자산이 "증권"이어야 함

SEC 경로는 대상 자산이 증권(security)에 해당해야 적용된다. 2026년 Token Taxonomy 이전까지는 SEC가 Howey 테스트를 적극 적용하여 대부분의 토큰에 증권성을 주장했으나, Token Taxonomy 발표 이후 입장이 정리되었다(아래 참조).

### Pump.fun 적용 시사점

- Pump.fun 밈코인은 대부분의 경우 "발행자의 경영적 노력에 대한 수익 기대"가 없으므로, Howey 테스트를 충족하지 않을 가능성이 높다.
- Token Taxonomy 기준으로도 "Digital Securities"보다는 "Digital Collectibles" 등 비증권 카테고리에 해당할 가능성이 크다.
- 따라서 **Pump.fun 불공정거래에 대해서는 SEC 경로보다 DOJ(wire fraud) 또는 CFTC(commodity) 경로가 더 현실적인 규율 수단**일 수 있다.

---

## 자산 분류 체계: SEC/CFTC 공동 Token Taxonomy (2026. 3.)

### 배경

2026년 3월 17일, SEC와 CFTC는 가상자산의 연방 증권법 적용에 관한 공동 해석 지침(Joint Interpretive Release)을 발표했다. SEC Press Release No. 2026-30, Release Nos. 33-11412로 공개되었으며, SEC의 공식 행정행위(formal agency action)로서 양 기관에 구속력을 가진다.

### 5가지 카테고리

| 카테고리 | 설명 | 증권 해당 여부 | 주관 기관 |
|---------|------|-------------|---------|
| **Digital Commodities** | 프로그래밍적 기능 + 수급에 의해 가치 결정. BTC, ETH, SOL 등 16개 자산 명시 지정 | 비증권 | CFTC |
| **Digital Collectibles** | 수집 목적의 자산 (NFT, 디지털 아트, 밈 등) | 비증권 | 불명확 |
| **Digital Tools** | 특정 블록체인 기능에 연계된 유틸리티 토큰 | 비증권 | 불명확 |
| **Payment Stablecoins** | GENIUS Act(2025.7.)에 의해 별도 규율되는 지급형 스테이블코인 | 비증권 (법률상 명시) | 별도 |
| **Digital Securities** | 전통 증권(주식·채권 등)의 토큰화 | 증권 | SEC |

### 투자계약의 종료 가능성

이 해석 지침은 가상자산이 영구적으로 증권인 것은 아님을 인정했다. 처음에 투자계약(investment contract)에 기반하여 판매된 토큰이라도, 네트워크가 충분히 탈중앙화되거나 발행자의 경영적 노력이 중단되면 더 이상 증권에 해당하지 않을 수 있다.

### Pump.fun 밈코인의 분류

Pump.fun에서 생성되는 밈코인은 Token Taxonomy의 5가지 카테고리 중 어디에 해당하는가?

- **Digital Securities**: 해당 가능성 낮음. 발행자의 경영적 노력에 대한 수익 기대가 없음.
- **Digital Commodities**: 현재 명시 지정된 16개 자산에 포함되지 않음. 다만 분류 원칙("프로그래밍적 기능 + 수급 기반 가치 결정")에 비추어 commodity로 볼 여지는 존재.
- **Digital Collectibles**: "밈(meme)"에 기반한 토큰이라는 점에서 이 카테고리에 해당할 가능성이 있으나, 수집보다는 투기 목적 거래가 주된 용도.

결론적으로, Pump.fun 밈코인의 정확한 분류는 현 시점에서 확정되지 않으며, 이는 규율 경로의 불확실성으로 이어진다. 다만 이 불확실성이 규율 불가능을 의미하지는 않는다. 분류와 무관한 DOJ wire fraud 경로가 존재하기 때문이다.

> 출처: SEC Press Release 2026-30; Release Nos. 33-11412 전문 (PDF); Jenner & Block 분석; Sullivan & Cromwell 분석

---

## 세 경로의 종합 비교

| | DOJ (Wire Fraud) | CFTC (CEA) | SEC (Securities Act) |
|--|-----------------|-----------|---------------------|
| **법적 근거** | 18 U.S.C. §1343 | CEA §6(c)(1), Rule 180.1 | §17(a), §10(b), Rule 10b-5 |
| **관할 기관** | 연방검찰 (형사) | CFTC (행정/민사) | SEC (행정/민사) |
| **자산 분류 요건** | 없음 | Commodity여야 함 | Security여야 함 |
| **적용 범위** | 기망 + 재산 취득 | 사기 + 시세조종 | 사기 + 시세조종 + 내부자거래 |
| **Pump.fun 적용 가능성** | 높음 (러그풀, 워시 트레이딩) | 중간 (분류 불확실) | 낮음 (비증권 가능성) |
| **주요 선례** | Operation Token Mirrors (2024) | FY2024 enforcement 50% 디지털 자산 | Token Taxonomy (2026.3.) |
| **최근 한계 사례** | Eisenberg 파기, Chastain 파기 | — | — |

---

## 프로젝트에 대한 시사점

1. **"증권이 아니면 합법"이 아님**: Pump.fun 밈코인이 증권에 해당하지 않더라도, DOJ wire fraud 경로와 (commodity 분류 시) CFTC 경로가 존재한다. 이는 프로젝트의 "불공정거래 탐지"가 법적으로 무의미한 작업이 아님을 뒷받침한다.

2. **Wire fraud의 강점과 한계**: Operation Token Mirrors가 보여주듯, 러그풀·워시 트레이딩처럼 "기망 → 금전 취득"이 명확한 유형은 wire fraud로 규율 가능하다. 그러나 Eisenberg, Chastain 파기 판결이 보여주듯, 기망의 성격이 불분명한 유형(DeFi 시세조종, 내부정보 이용)은 wire fraud만으로 불충분할 수 있다.

3. **대시보드의 사후 증거 기능과의 연결**: wire fraud 기소에는 "기망의 계획"을 입증하는 증거가 필요하다. 온체인 데이터에서 추출한 행동 패턴(동시 매도, 시리얼 런칭, 봇 선점매수 등)은 이러한 "기망의 계획"의 존재를 뒷받침하는 정황 증거로 기능할 수 있다.

4. **한국 가상자산이용자보호법과의 비교**: 한국법은 자산 분류 논쟁 없이 "가상자산" 전체에 불공정거래 금지를 적용하므로, 미국의 세 경로 구조보다 적용 범위가 명확하다. 이 차이 자체가 비교법적으로 흥미로운 분석 포인트가 된다.

---

> **참고**: 이 문서는 2026년 4월 17일 시점의 정보를 기반으로 작성되었다. 가상자산 규제는 빠르게 변화하는 분야이므로, 구체적 법적 판단에는 최신 자료의 재확인이 필요하다.
