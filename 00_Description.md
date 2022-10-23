# 디렉토리
```bash
├── custom_data
│   ├── active_closed_all.csv : 액티브 중소법인, 휴폐업 중소법인의 기업개요와 휴폐업 이력 데이터(정제x)
│   ├── base_data.csv : 재무데이터와 비재무데이터(active_closed_all.csv)를 합친 데이터(정제x)
│   ├── feature_engineering_idurstry_code.csv : 산업코드1을 통해 업종중분류, 업종대분류를 추가한 데이터
│   ├── feature_engineering_address.csv : 크롤링한 주소 데이터를 추가한 데이터
│   ├── basic_finance_data.csv : base_data.csv를 정제한 데이터(결측치와 이상치 제거, 2022년 데이터 삭제, 윈저라이징 적용, 재무비율을 산출하기 위한 변수 생성)
│   ├── basic_finance_ratio_data.csv : basic_finance_data.csv를 통해 성장성, 수익성, 생산성, 안정성, 활동성으로 구분하여 산출한 기본재무비율 데이터
│   ├── financial_position_volatility.csv : basic_finance_ratio_data.csv를 통해 재무상태변동성을 산출한 데이터
│   ├── variability_indurstrial_level.csv : basic_finance_ratio_data.csv와 feture_engineering_idurstry_code.csv, mean_top10_per_year.csv을 통해 
│   │                                       업종대분류별 산업수준상태변동성을 산출한 데이터
│   ├── mean_top10_per_year.csv : feture_engineering_idurstry_code.csv을 통해 연도별 업종대분류(산업)에 따른 총자산순이익률 상위 10개 기업의 평균을 산출한 
│   │                             데이터
│   ├── mean_total_assets_per_indurstry.csv : 산업수준상태변동성을 산출하는 과정에서 산업별 평균총자산이익률을 산출한 데이터
│   ├── all_finance_data.csv : basic_finance_ratio_data.csv, financial_position_volatility.csv, variability_indurstrial_level.csv을 합치고, 2018년은 
│   │                          제거한 데이터
│   ├── use_finance_data.csv : all_finance_data.csv에서 정보이득 결과 분석에 따라 사용할 재무 변수만 남겨둔 데이터
│   ├── address_json : 사업자등록번호로 크롤링한 주소 데이터(1차)
│   │   └── file_{number}.json
│   ├── address_json_no : 누락되어 사업자등록번호로 다시 크롤링한 주소 데이터(1차)
│   │   └── file_{number}.json
│   ├── address_json_name : 기업명으로 크롤링한 주소 데이터(2차)
│   │   └── file_{number}.json
│   ├── address_json_name_non : 누락되어 기업명으로 다시 크롤링한 주소 데이터(2차)
│   │   └── file_{number}.json
│   ├── indurstry_code_missing_value.json : 사업자등록번호, 기업명으로 산업코드1의 결측치를 크롤링한 데이터 
│   ├── search_address.json : 사업자등록번호, 기업명으로 크롤링한 주소 데이터(2018년 포함, 윈저라이징 적용x)
│   ├── finance_information_gain.json : basic_finance_ratio_data.csv을 통해 산출한 정보이득 데이터(2018년 포함, 윈저라이징 적용x)
│   ├── finance_information_gain_new.json : basic_finance_ratio_data.csv을 통해 산출한 정보이득 데이터(2018년 제거, 윈저라이징 적용o)
│   └── 한국표준산업분류10차_표.xlsx : 산업코드1 결측치 처리 및 업종중분류, 업종대분류 피처엔지니어링 시 기준으로 사용한 데이터
├── origin_data
│   ├── 넘블 챌린지 개방데이터 레이아웃.xlsx
│   ├── 넘블 챌린지 개방데이터 코드집.xlsx
│   ├── 액티브 중소법인 재무보유.xlsx
│   ├── 휴폐업 중소법인 재무보유.xlsx
│   └── 재무데이터.txt
├── 00_Description.md
├── 01_Data_Merge.ipynb
├── 02_EDA&Base_Line.ipynb
├── 03_Feature_Engineering_Indurstry_Code.ipynb
├── 03_Indursty_Code_Crawling.ipynb
├── 04_Top10_Corporation.ipynb
├── 05_Finance_Data_Preprocessing.ipynb
├── 06_Calculate_Information_Gain_Multiprocessing.py
├── 07_Analysis_Infromation_Gain.ipynb
└── 08_Feature_Engineering_Address.ipynb
```