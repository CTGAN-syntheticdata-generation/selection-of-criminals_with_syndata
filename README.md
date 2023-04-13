# Generate, review and utilize synthetic data [[한글]](https://github.com/CTGAN-syntheticdata-generation/selection-of-criminals_with_syndata/tree/ko)
Data used in the field of customs administration has a lot of sensitive information, including personal information. Due to these characteristics of the domain, the barriers to research and education using data analysis in the customs field are very high. Accordingly, the Korea Customs Service, the Korea Institute of Science and Technology, and the Institute of Basic Science introduced a study on the creation of virtualized data from the Korea Customs Service through a paper called "Introduction to the Virtualized Customs Service Import Declaration Dataset." This can help research in the field of tariffs, such as screening of superior cargo, classifying items, and predicting relationships. This project will be carried out by changing the author's sample data and code. To generate synthetic data and determine the statistical similarity of synthetic data, correlation analysis, coverage analysis, and regression analysis are performed to compare and review the result values of the two data.
 
## Data Configuration
The entire data is uploaded. This data is 54,000 synthetic data from January 2020 to June 2021. Each case is written similar to the actual import declaration. Among the attributes listed in Korea's import declaration, it includes 20 of the most important attributes and two labels indicating whether the goods are illegal. The attribute name of the data was arbitrarily translated into an English name and used. The meaning of each attribute is shown in the table below.

|attribute|Explanation|
|------|---|
|dec_num|import declaration num|
|dec_date|Date import declaration was submitted|
|dec_custom_code|Declared customs code|
|imp_dec_code|Type code of import declaration, such as general and simplified declaration|
|imp_trd_code|Type code of import transaction|
|imp_typ_code|Type code for import use, such as raw materials for domestic consumption and export|
|collect_code|Type code for collection|
|typ_transport_code|Type code for transport and container|
|dec_mark|Type code for reporter’s name and trade name|
|importer|Importer's customs code|
|ovs_cust_code|Overseas customer's business name code|
|exps_carr_code|Code of express method and express company|
|HS10|10-digit HS code|
|country_ship_code|Overseas shipping country code of declared goods|
|country_orig_code|Type Code of country of origin|
|trff_rate|Tax rate of the item (%)|
|trff_class_code|Dividing code according to the tax rate of the item|
|country_orig_mark_code|Code according to the presence or absence of country of origin indication and reasons for exemption from indication|
|dec_weight|Item weight excluding packaging (KG)|
|taxabal_price_KRW|Amount actually paid by the buyer (KRW)|
|crime_yn|Whether it is high crime cargo|
|key_exposure|Whether a high-weighted criminal among the high-crime items|

## Generated Data Features and Utilization Skills
The provided data set was created using CTGAN (Conditional Tabular GAN). It has a distribution similar to the actual data.All personal information is excluded or anonymized. It was found that there is a relationship between attributes with the characteristics of import declaration data, and the relationship is damaged when virtualization is implemented. To solve the phenomenon, the skills that help preserve the relationship presented in the above paper were used.

## Source of Reference
https://github.com/Seondong/Customs-Declaration-Datasets/tree/en
