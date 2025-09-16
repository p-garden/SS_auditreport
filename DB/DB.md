## DB 스키마 
감사보고서의 테이블들을 총 48개의 테이블을 만들고 7개의 주제에맞게 형식 정리

### **1. 관계사 및 투자 관련 테이블**

이 그룹은 삼성의 자회사 및 관계사에 대한 정보, 투자 변동 내역, 지배 관계를 다룹니다.

* **`종속기업_재무정보`**
    * `id` (`INTEGER PRIMARY KEY AUTOINCREMENT`)
    * `종속기업명` (`TEXT`)
    * `설립일` (`TEXT`)
    * `주요사업` (`TEXT`)
    * `소재지` (`TEXT`)
    * `지분율` (`REAL`)
    * `구분` (`TEXT`)
* **`관계기업_재무정보`**
    * `id` (`INTEGER PRIMARY KEY AUTOINCREMENT`)
    * `관계기업명` (`TEXT`)
    * `설립일` (`TEXT`)
    * `주요사업` (`TEXT`)
    * `소재지` (`TEXT`)
    * `지분율` (`REAL`)
    * `구분` (`TEXT`)
* **`지배관계_정보`**
    * `id` (`INTEGER PRIMARY KEY AUTOINCREMENT`)
    * `지역` (`TEXT`)
    * `기업명` (`TEXT`)
    * `업종` (`TEXT`)
    * `지분율_퍼센트` (`REAL`)
    * `연도` (`INTEGER`)
* **`종속기업_관계기업_공동기업_투자_변동내역`**
    * `id` (`INTEGER PRIMARY KEY AUTOINCREMENT`)
    * `연도` (`INTEGER`)
    * `구분` (`TEXT`)
    * `변동내역` (`REAL`)
    * `단위` (`TEXT`)
* **`관계기업_투자_현황`**
    * `id` (`INTEGER PRIMARY KEY AUTOINCREMENT`)
    * `관계기업명` (`TEXT`)
    * `설립일` (`TEXT`)
    * `주요사업` (`TEXT`)
    * `소재지` (`TEXT`)
    * `지분율` (`REAL`)
    * `취득원가` (`REAL`)
    * `장부가액` (`REAL`)
    * `단위` (`TEXT`)
* **`관계기업_투자주식_내역`**
    * `id` (`INTEGER PRIMARY KEY AUTOINCREMENT`)
    * `연도` (`INTEGER`)
    * `관계기업명` (`TEXT`)
    * `투자자산_유형` (`TEXT`)
    * `장부가액` (`REAL`)
    * `단위` (`TEXT`)

---

### **2. 자산 및 부채 변동 관련 테이블**

이 그룹은 유형/무형자산, 재고자산, 충당부채 등 주요 자산 및 부채의 상세 변동 내역을 포함합니다.

* **`재고자산_내역`**
    * `id` (`INTEGER PRIMARY KEY AUTOINCREMENT`)
    * `연도` (`INTEGER`)
    * `구분` (`TEXT`)
    * `자산명` (`TEXT`)
    * `단기순이익에_미치는_영향` (`REAL`)
    * `단기순이익에_미치는_영향_단위` (`TEXT`)
* **`유형자산_변동내역`**
    * `id` (`INTEGER PRIMARY KEY AUTOINCREMENT`)
    * `연도` (`INTEGER`)
    * `구분` (`TEXT`)
    * `변동내역` (`REAL`)
    * `단위` (`TEXT`)
* **`무형자산_변동내역`**
    * `id` (`INTEGER PRIMARY KEY AUTOINCREMENT`)
    * `연도` (`INTEGER`)
    * `구분` (`TEXT`)
    * `변동내역` (`REAL`)
    * `단위` (`TEXT`)
* **`매각예정분류_정보`**
    * `id` (`INTEGER PRIMARY KEY AUTOINCREMENT`)
    * `연도` (`INTEGER`)
    * `항목` (`TEXT`)
    * `변동내역` (`TEXT`)
    * `금액` (`REAL`)
    * `단위` (`TEXT`)
    * `값_유형` (`TEXT`)
* **`충당부채_정보`**
    * `id` (`INTEGER PRIMARY KEY AUTOINCREMENT`)
    * `연도` (`INTEGER`)
    * `항목` (`TEXT`)
    * `판매보증` (`REAL`)
    * `기술사용료` (`REAL`)
    * `장기성과급` (`REAL`)
    * `기타` (`REAL`)
    * `계` (`REAL`)
* **`채권채무_정보`**
    * `id` (`INTEGER PRIMARY KEY AUTOINCREMENT`)
    * `구분` (`TEXT`)
    * `기업명` (`TEXT`)
    * `채권_등` (`REAL`)
    * `채무_등` (`REAL`)
    * `단위` (`TEXT`)
    * `연도` (`INTEGER`)
* **`차입금내역_정보`**
    * `id` (`INTEGER PRIMARY KEY AUTOINCREMENT`)
    * `연도` (`INTEGER`)
    * `항목` (`TEXT`)
    * `변동내역` (`TEXT`)
    * `금액` (`REAL`)
    * `단위` (`TEXT`)
    * `단위_배수` (`REAL`)
    * `조정된_금액` (`REAL`)
* **`사채내역_정보`**
    * `id` (`INTEGER PRIMARY KEY AUTOINCREMENT`)
    * `연도` (`INTEGER`)
    * `항목` (`TEXT`)
    * `변동내역` (`TEXT`)
    * `금액` (`REAL`)
    * `단위` (`TEXT`)
    * `단위_배수` (`REAL`)
    * `조정된_금액` (`REAL`)
* **`사채상환내역_정보`**
    * `id` (`INTEGER PRIMARY KEY AUTOINCREMENT`)
    * `연도` (`INTEGER`)
    * `항목` (`TEXT`)
    * `변동내역` (`TEXT`)
    * `금액` (`REAL`)
    * `단위` (`TEXT`)
    * `단위_배수` (`REAL`)
    * `조정된_금액` (`REAL`)
* **`거래내역_정보`**
    * `id` (`INTEGER PRIMARY KEY AUTOINCREMENT`)
    * `구분` (`TEXT`)
    * `기업명` (`TEXT`)
    * `매출_등` (`REAL`)
    * `비유동자산_처분` (`REAL`)
    * `매입_등` (`REAL`)
    * `비유동자산_매입` (`REAL`)
    * `단위` (`TEXT`)
    * `연도` (`INTEGER`)

---

### **3. 금융 상품 관련 테이블**

이 그룹은 다양한 금융 상품의 변동 내역, 공정 가치 및 순손익 관련 정보를 정리합니다.

* **`Level3_금융상품_변동내역`**
    * `id` (`INTEGER PRIMARY KEY AUTOINCREMENT`)
    * `연도` (`INTEGER`)
    * `단위` (`TEXT`)
    * `구분` (`TEXT`)
    * `값` (`REAL`)
* **`매도가능금융자산_변동내역`**
    * `id` (`INTEGER PRIMARY KEY AUTOINCREMENT`)
    * `연도` (`INTEGER`)
    * `항목` (`TEXT`)
    * `변동내역` (`TEXT`)
    * `금액` (`REAL`)
    * `단위` (`TEXT`)
    * `단위_배수` (`REAL`)
    * `조정된_금액` (`REAL`)
* **`매도가능금융자산_상장주식`**
    * `id` (`INTEGER PRIMARY KEY AUTOINCREMENT`)
    * `연도` (`INTEGER`)
    * `항목` (`TEXT`)
    * `변동내역` (`TEXT`)
    * `금액` (`REAL`)
    * `단위` (`TEXT`)
    * `단위_배수` (`REAL`)
    * `조정된_금액` (`REAL`)
* **`매출채권_할인내역_정보`**
    * `id` (`INTEGER PRIMARY KEY AUTOINCREMENT`)
    * `연도` (`INTEGER`)
    * `항목` (`TEXT`)
    * `변동내역` (`TEXT`)
    * `금액` (`REAL`)
    * `단위` (`TEXT`)
    * `단위_배수` (`REAL`)
    * `조정된_금액` (`REAL`)
* **`매출채권과미수금_정보`**
    * `id` (`INTEGER PRIMARY KEY AUTOINCREMENT`)
    * `연도` (`INTEGER`)
    * `항목` (`TEXT`)
    * `변동내역` (`TEXT`)
    * `금액` (`REAL`)
    * `단위` (`TEXT`)
    * `단위_배수` (`REAL`)
    * `조정된_금액` (`REAL`)
* **`매출채권과미수금_연체일구분_정보`**
    * `id` (`INTEGER PRIMARY KEY AUTOINCREMENT`)
    * `연도` (`INTEGER`)
    * `항목` (`TEXT`)
    * `변동내역` (`TEXT`)
    * `금액` (`REAL`)
    * `단위` (`TEXT`)
    * `단위_배수` (`REAL`)
    * `조정된_금액` (`REAL`)
* **`매출채권과미수금_충당금변동내역_정보`**
    * `id` (`INTEGER PRIMARY KEY AUTOINCREMENT`)
    * `연도` (`INTEGER`)
    * `항목` (`TEXT`)
    * `변동내역` (`TEXT`)
    * `금액` (`REAL`)
    * `단위` (`TEXT`)
    * `단위_배수` (`REAL`)
    * `조정된_금액` (`REAL`)
* **`범주별금융상품_금융부채_정보`**
    * `id` (`INTEGER PRIMARY KEY AUTOINCREMENT`)
    * `연도` (`INTEGER`)
    * `항목` (`TEXT`)
    * `변동내역` (`TEXT`)
    * `금액` (`REAL`)
    * `단위` (`TEXT`)
    * `단위_배수` (`REAL`)
    * `조정된_금액` (`REAL`)
* **`범주별금융상품_금융자산_정보`**
    * `id` (`INTEGER PRIMARY KEY AUTOINCREMENT`)
    * `연도` (`INTEGER`)
    * `항목` (`TEXT`)
    * `변동내역` (`TEXT`)
    * `금액` (`REAL`)
    * `단위` (`TEXT`)
    * `단위_배수` (`REAL`)
    * `조정된_금액` (`REAL`)
* **`범주별순손익구분_금융부채_정보`**
    * `id` (`INTEGER PRIMARY KEY AUTOINCREMENT`)
    * `연도` (`INTEGER`)
    * `항목` (`TEXT`)
    * `변동내역` (`TEXT`)
    * `금액` (`REAL`)
    * `단위` (`TEXT`)
    * `단위_배수` (`REAL`)
    * `조정된_금액` (`REAL`)
* **`범주별순손익구분_금융자산_정보`**
    * `id` (`INTEGER PRIMARY KEY AUTOINCREMENT`)
    * `연도` (`INTEGER`)
    * `항목` (`TEXT`)
    * `변동내역` (`TEXT`)
    * `금액` (`REAL`)
    * `단위` (`TEXT`)
    * `단위_배수` (`REAL`)
    * `조정된_금액` (`REAL`)

---

### **4. 재무 성과 및 비용/수익 관련 테이블**

이 그룹은 법인세, 비용/수익, 자본금 등 기업의 재무 성과 관련 정보를 정리합니다.

* **`법인세_정보`**
    * `id` (`INTEGER PRIMARY KEY AUTOINCREMENT`)
    * `연도` (`INTEGER`)
    * `항목` (`TEXT`)
    * `금액` (`REAL`)
    * `단위` (`TEXT`)
* **`비용수익_정보`**
    * `id` (`INTEGER PRIMARY KEY AUTOINCREMENT`)
    * `연도` (`INTEGER`)
    * `항목` (`TEXT`)
    * `금액` (`REAL`)
    * `단위` (`TEXT`)
* **`자본금_이익잉여금_정보`**
    * `id` (`INTEGER PRIMARY KEY AUTOINCREMENT`)
    * `연도` (`INTEGER`)
    * `항목` (`TEXT`)
    * `금액` (`REAL`)
    * `단위` (`TEXT`)
* **`주당이익_배당_정보`**
    * `id` (`INTEGER PRIMARY KEY AUTOINCREMENT`)
    * `연도` (`INTEGER`)
    * `항목` (`TEXT`)
    * `금액` (`REAL`)
    * `단위` (`TEXT`)
* **`경영진보상_정보`**
    * `id` (`INTEGER PRIMARY KEY AUTOINCREMENT`)
    * `구분` (`TEXT`)
    * `당기` (`REAL`)
    * `전기` (`REAL`)
    * `단위` (`TEXT`)
    * `연도` (`INTEGER`)
* **`기타자본_정보`**
    * `id` (`INTEGER PRIMARY KEY AUTOINCREMENT`)
    * `연도` (`INTEGER`)
    * `항목` (`TEXT`)
    * `금액` (`REAL`)
    * `단위` (`TEXT`)

---

### **5. 위험 관리 및 평가 관련 테이블**

이 그룹은 환율, 유동성, 공정 가치 등 재무적 위험에 대한 상세 분석 정보를 포함합니다.

* **`환율변동위험_정보`**
    * `id` (`INTEGER PRIMARY KEY AUTOINCREMENT`)
    * `연도` (`INTEGER`)
    * `항목` (`TEXT`)
    * `변동내역` (`TEXT`)
    * `금액` (`REAL`)
    * `단위` (`TEXT`)
    * `단위_배수` (`REAL`)
* **`부채비율_정보`**
    * `id` (`INTEGER PRIMARY KEY AUTOINCREMENT`)
    * `연도` (`INTEGER`)
    * `항목` (`TEXT`)
    * `변동내역` (`TEXT`)
    * `금액` (`REAL`)
    * `단위` (`TEXT`)
    * `단위_배수` (`REAL`)
* **`공정가치_정보`**
    * `id` (`INTEGER PRIMARY KEY AUTOINCREMENT`)
    * `연도` (`INTEGER`)
    * `항목` (`TEXT`)
    * `변동내역` (`TEXT`)
    * `금액` (`REAL`)
    * `단위` (`TEXT`)
    * `단위_배수` (`REAL`)
* **`공정가치_민감도분석_정보`**
    * `id` (`INTEGER PRIMARY KEY AUTOINCREMENT`)
    * `연도` (`INTEGER`)
    * `항목` (`TEXT`)
    * `변동내역` (`TEXT`)
    * `금액` (`REAL`)
    * `단위` (`TEXT`)
    * `단위_배수` (`REAL`)
* **`부문별_보고_정보`**
    * `id` (`INTEGER PRIMARY KEY AUTOINCREMENT`)
    * `연도` (`INTEGER`)
    * `항목` (`TEXT`)
    * `변동내역` (`TEXT`)
    * `금액` (`REAL`)
    * `단위` (`TEXT`)
    * `단위_배수` (`REAL`)
* **`유동성위험_정보`**
    * `id` (`INTEGER PRIMARY KEY AUTOINCREMENT`)
    * `연도` (`INTEGER`)
    * `단위` (`TEXT`)
    * `구분` (`TEXT`)
    * `기간` (`TEXT`)
    * `값` (`REAL`)
* **`공정가치_수준별_정보`**
    * `id` (`INTEGER PRIMARY KEY AUTOINCREMENT`)
    * `연도` (`INTEGER`)
    * `자산부채` (`TEXT`)
    * `구분` (`TEXT`)
    * `수준` (`INTEGER`)
    * `값` (`REAL`)
    * `단위` (`TEXT`)
* **`무상할당_배출권`**
    * `id` (`INTEGER PRIMARY KEY AUTOINCREMENT`)
    * `연도` (`INTEGER`)
    * `변동내역` (`TEXT`)
    * `단위` (`TEXT`)
    * `무상할당_배출권` (`REAL`)
    * `배출량_추정치` (`REAL`)

---

### **6. 확정급여채무 및 연금 관련 테이블**

이 그룹은 퇴직금 및 연금과 관련된 상세한 재무적 가정, 비용, 변동 내역을 담고 있습니다.

* **`사외적립자산_정보`**
    * `id` (`INTEGER PRIMARY KEY AUTOINCREMENT`)
    * `연도` (`INTEGER`)
    * `변동내역` (`TEXT`)
    * `단위` (`TEXT`)
    * `급여지급액` (`REAL`)
    * `기말` (`REAL`)
    * `기초` (`REAL`)
    * `기타` (`REAL`)
    * `이자수익` (`REAL`)
    * `재측정요소` (`REAL`)
* **`확정급여채무_민감도분석_정보`**
    * `id` (`INTEGER PRIMARY KEY AUTOINCREMENT`)
    * `연도` (`INTEGER`)
    * `변동내역` (`TEXT`)
    * `단위` (`TEXT`)
    * `임금상승률_감소` (`REAL`)
    * `임금상승률_증가` (`REAL`)
    * `할인율_감소` (`REAL`)
    * `할인율_증가` (`REAL`)
* **`보험수리적_가정_정보`**
    * `id` (`INTEGER PRIMARY KEY AUTOINCREMENT`)
    * `연도` (`INTEGER`)
    * `변동내역` (`TEXT`)
    * `단위` (`TEXT`)
    * `미래임금상승률` (`REAL`)
    * `할인율` (`REAL`)
* **`확정급여제도_비용_정보`**
    * `id` (`INTEGER PRIMARY KEY AUTOINCREMENT`)
    * `연도` (`INTEGER`)
    * `변동내역` (`TEXT`)
    * `단위` (`TEXT`)
    * `매출원가` (`REAL`)
    * `판매비와관리비_등` (`REAL`)
* **`확정급여제도_관련_비용_정보`**
    * `id` (`INTEGER PRIMARY KEY AUTOINCREMENT`)
    * `연도` (`INTEGER`)
    * `변동내역` (`TEXT`)
    * `단위` (`TEXT`)
    * `과거근무원가` (`REAL`)
    * `당기근무원가` (`REAL`)
    * `순이자수익` (`REAL`)
    * `순이자원가` (`REAL`)
* **`확정급여채무_변동내역_정보`**
    * `id` (`INTEGER PRIMARY KEY AUTOINCREMENT`)
    * `연도` (`INTEGER`)
    * `항목` (`TEXT`)
    * `변동내역` (`TEXT`)
    * `금액` (`REAL`)
    * `단위` (`TEXT`)
    * `값_유형` (`TEXT`)
* **`확정급여채무_정보`**
    * `id` (`INTEGER PRIMARY KEY AUTOINCREMENT`)
    * `연도` (`INTEGER`)
    * `변동내역` (`TEXT`)
    * `단위` (`TEXT`)
    * `기금_미적립_현재가치` (`REAL`)
    * `기금_적립_현재가치` (`REAL`)
    * `사외적립자산_공정가치` (`REAL`)  