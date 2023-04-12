# Generate, review and utilize synthetic data [[한글]](https://github.com/CTGAN-syntheticdata-generation/selection-of-criminals_with_syndata/tree/ko)
Data used in the field of customs administration has a lot of sensitive information, including personal information. Due to these characteristics of the domain, the barriers to research and education using data analysis in the customs field are very high. Accordingly, the Korea Customs Service, the Korea Institute of Science and Technology, and the Institute of Basic Science introduced a study on the creation of virtualized data from the Korea Customs Service through a paper called "Introduction to the Virtualized Customs Service Import Declaration Dataset." 이는 우범 화물 선별, 품목 분류 및 관계성 예측 등 관세 분야의 연구에 도움을 줄 수 있다. 이번 프로젝트는 위 논문을 바탕으로 함께 제공된 저자의 Github에서 샘플데이터와 코드를 받아 합성데이터를 생성하고, 합성데이터의 통계적 유사성을 판단하기 위해 상관도 분석, 커버리지 분석, 회귀분석을 시행하여 두 데이터의 결과 값을 비교 검토한다. 
 
## 데이터 구성
전체 데이터는 '가상화된 관세청 수입신고 데이터셋 소개'의 저자가 제공하는 Github에서 다운로드하여 사용한다. 이 데이터는 2020년 1월부터 2021년 6월 까지의 54,000건의 합성데이터이다. 각 건은 실제 수입신고 내용과 유사하게 작성되어 있다. 한국의 수입신고서에 기재하는 속성중 가장 중요한 20개의 속성과 물품의 우범여부를 나타내는 2개의 라벨을 포함한다. 해당 데이터의 속성명을 임의로 영문명으로 번역하여 사용하였다. 각 속성의 의미를 아래 표에 담았다.

|속성명|영문명|설명|
|------|---|---|
|신고번호|dec_num|신고서 번호|
|신고일자|dec_date|신고서가 제출된 날짜|
|신고세관부호|dec_custom_code|신고한 세관의 부호|
|수입신고구분코드|imp_dec_code|일반 및 간이 신고 등 수입 신고의종류에 대한 부호|
|수입거래구분코드|imp_trd_code|수입 거래의 종류 부호|
|수입종류코드|imp_typ_code|내수용,수출용원자재 등 수입 용도에 관한 부호|
|징수형태코드|collect_code|징수의 종류에 따른 부호|
|운송수단유형코드|typ_transport_code|운송수단 및 운송용기에 대한 부호|
|신고인부호|dec_mark|신고인 상호와 성명에 따른 부호|
|수입자|importer|수입자의 통관고유부호|
|해외거래처부호|ovs_cust_code|해외거래처의 상호 부호|
|특송업체부호|exps_carr_code|특송 방법 및 특송 업체의 부호|
|HS6단위부호|HS10|6자리 물품 분류 부호|
|적출국가코드|country_ship_code|신고물품의 해외선적국가 부호|
|원산지국가코드|country_orig_code|원산지 국가의 부하|
|관세율|trff_rate|해당 품목의 세율(%)|
|관세율구분코드|trff_class_code|해당 품목의 세율에 따른 구분 부호|
|원산지표시유무코드|country_orig_mark_code|원산지 표시 유무 및 표시면제사유에 따른 부호|
|신고중량|dec_weight|포장용기를 제외한 물품 중량(KG)|
|과세가격원화금액|taxabal_price_KRW|구마재가 실제로 지급한 금액(원)|
|우범여부|crime_yn|우범화물여부|
|핵심적발|key_exposure|우범 항목중 가중치가 높은 우범여부|

## 생성방법
제공되는 데이터 셋은 CTGAN(Conditional Tabular GAN)을 활용하여 생성되었다. 실제 데이터와 유사한 분포를 갖고 있다.모든 개인정보는 제외 또는 익명화 되었다. 수입신고 데이터의 특성을 가진 속성간 관계성이 존재하며 가상화를 시행할 때 관계성이 훼손되는 현상이 발견되어 참고했던 논문에서 제시한 관계성 보존에 도움이 되는 스킬을 사용하였다. 

## 참고논문 출처
https://github.com/Seondong/Customs-Declaration-Datasets/tree/ko
