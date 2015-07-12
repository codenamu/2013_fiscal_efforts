# 2013 회계년도 대한민국 재정 노력도 데이터 (Korean Fiscal Management Efforts FY2013)

2013 회계년도 대한민국 재정 종합 보고서에서 재정 노력도에 관련된 데이터만 추출해서 정리했습니다.
이 데이터는 [우리지역 채무탈출 프로젝트](http://getoutofdebt.kr)에 사용했습니다.

## 재정운용노력 분야 타뷸러 데이터 추출 및 가공

보고서에서 시, 군, 자치구별 타뷸러 데이터 페이지 추출
상용프로그램을 활용해서 pdf에 있는 타뷸러 데이터 엑셀 파일로 변환
엑셀 파일을 csv 파일(euckr, utf8)로 변환

si 시단위 - 151, 155, 160, 165 페이지
goon 군단위 - 170, 175, 180, 185 페이지
gu 자치구단위 - 189, 190, 192, 193, 196, 201 페이지

## 관련 기술

### dat
https://github.com/maxogden/dat
http://dat-data.com

Dat is a version-controlled, decentralized data sync tool designed to improve collaboration between data people and data systems.
관리용 데이터 입력, 수정, 이력 등

```
npm install dat -g
```

### data package manager (dpm)
https://github.com/okfn/dpm
배포용 데이터 패키지

```
npm install datapackage -g
npm install datapackage-init —save-dev
```

## dat 사용법
```
dat init
{
  "name": "FY2013-korean-fiscal-management-efforts",
  "description": "FY2013 korean fiscal management efforts report from korea research institute for local administration.",
  "publisher": "codenamu"
}

dat import city.csv -d city
dat import goon.csv -d goon
dat import gu.csv -d gu

dat serve
open http:localhost:6461
```

## 출처 source:

2013 회계년도 지방자치단체 재정분석 종합보고서
2014.12
한국지방행정연구원
korea research institute for local administration
http://www.krila.re.kr

source:
web:
http://lofin.mogaha.go.kr/lofin_finan/InfoDetail.jsp?idx=146&finan_idx=3&type=title&word=&pg=4

pdf:
http://lofin.mogaha.go.kr/lofin_finan/Download.jsp?mask=finan_3&fn=2013%B3%E2+%C0%E7%C1%A4%BA%D0%BC%AE+%C1%BE%C7%D5%BA%B8%B0%ED%BC%AD%28%C0%E7%C1%A4%B0%ED%29.pdf
Financial management efforts report FY2013, South Korea