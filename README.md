# ISF_국제스포츠 정보 현안 분석

해당 프로그램은 [ ISF_국제스포츠 정보 현안 분석 ] 프로젝트의 연구를 위해 만들어졌습니다.<br>
(2021 도쿄 올림픽 관련 국내외 (한.중.미) 인식 조사 및 정서분석 관련하여 데이터 수집 및 데이터 분석)<br>

기술 스택 : Python, Selenium, Beautifulsoup, Mecab, Wordcloud

**1. 뉴스 기사 본문 및 댓글 크롤링**<br>
---
기간 : 6/23 ~ 8/21 (총 60일)
키워드 : "도쿄올림픽"
수집 데이터 : 1,395,654 (한국)
수집 데이터 필드 : 댓글, 닉네임, 날짜, 추천, URL
수집 사이트
      한국 - 네이버 뉴스<br>
      중국 - sina<br>
      미국 - 뉴욕 타임즈<br>

**2. 불용어 처리 및 본문 속 단어 빈도수 체크**<br>
---
Ⅰ. 형태소 분석 후 형용사, 명사만 추출<br>
nouns_of_daily.py -> 불용어 처리 및 top 10 추출<br>
   <img src= "https://user-images.githubusercontent.com/87688936/169702159-6ddd80be-289b-4828-82d2-95ce2d6c66ae.png" width="200" height="200"><br>
Ⅱ.한국어 형태소 분석기 Mecab 사용<br>
count_reply.c -> 날짜 별로 3국 각각 댓글 수 합계를 구하여, 어떤 날 제일 댓글이 활발했는지 체크<br>

**3. 데이터 그래프화**<br>
---
Ⅰ. 올림픽 개최 전후 10일간 일별 top1 키워드 빈도수 체크 -> 올림픽 전후 키워드 빈도수 그래프 추출<br>
<img src= "https://user-images.githubusercontent.com/87688936/169703367-45380860-8b6e-499f-8cd7-4c307a1898ad.png" width="300"><br>
Ⅱ. 올림픽 개최 전 후 30일간 top5 키워드에 대한 일별 키워드 빈도수 체크 -> top5 키워드에 대한 일별 키워드 빈도수 체크 그래프 추출<br>
<img src= "https://user-images.githubusercontent.com/87688936/169703385-65e39ad2-b770-491e-96be-6571a5ad3208.png" width="300"><br>
Ⅲ. 올림픽 개최 전 후 30일간 top5 키워드에 대한 주별 키워드 빈도수 체크 -> top5 키워드에 대한 주별 키워드 빈도수 체크 그래프 추출<br>
<img src= "https://user-images.githubusercontent.com/87688936/169703400-f2a2c0ac-a222-4212-bed9-052493423cee.png" width="300"><br>
Ⅳ. 본문 속 단어 빈도수 체크 -> 3국 키워드 wordcloud 추출<br>
<img src= "https://user-images.githubusercontent.com/87688936/169703414-4175ef0d-213f-41d8-9606-8aa1dd7ba2cb.png" width="300"><br>

**4. 감성 분석 (BERT, FASTTEXT)**
---
Ⅰ.댓글 데이터 긍.부정 감성분석
Accuary: 87.6%
레이블링 : 긍정 1, 부정 0 으로 분류하여 전체 약 130만개의 데이터 중 5만개의 데이터 레이블링 작업 진행<br>

Ⅱ. fastText, Bert를 활용하여 모델 형성<br>


※ 데이터 범위
 7/23일 올림픽 개최일 기준 한달 전/후 6/23~8/21일 <br>
※ 데이터 필드 목록<br>
<img src= "https://user-images.githubusercontent.com/87688936/169702096-172b50d6-1ac5-4df1-a3ff-d134b981f459.png" width="300"><br>
※ 수집 결과 <br>
한국 : 1,395,654개 <br>


**5. 프로젝트 결과 **<br>
---
[ISF] 2021 데이터로 본 국제스포츠 (https://sport-strategy.org/archive/30)
