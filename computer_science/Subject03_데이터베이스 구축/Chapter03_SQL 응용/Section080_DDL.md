## CS Study - Section080 DDL
### ✏️ Study
#### 💡 DDL(Data Definition Language, 데이터 정의어)의 개요
- DB 구조, 데이터 형식, 접근 방식 등 DB를 구축하거나 수정할 목적으로 사용하는 언어.
- 번역한 결과를 `데이터 사전(Data Dictionary)`에 여러 개의 테이블로서 저장.
<br>

#### 💡 CREATE SCHEMA
- `스키마를 정의`하는 명령문.
- **스키마 이름**과 **소유권자/허가권자**를 정의.
> **CREATE SCHEMA** 스키마명 **AUTHORIZATION** 사용자_id;
##### 🔖 스키마(Schema)
- 데이터베이스의 구조와 제약 조건에 관한 전반적인 명세(Specification)를 기술(Description)한 것.
- 데이터 개체, 속성, 관계 및 데이터 조작 시 데이터 값들이 가지는 제약 조건 등에 관해 전반적으로 정의.
<br>
<br>

#### 💡 CREATE DOMAIN
- `도메인을 정의`하는 명령문.
- 임의의 속성에서 취할 수 있는 값의 범위가 SQL에서 지원하는 전체 데이터 타입의 값이 아니고 일부분일 때, 그 값의 범위를 도메인으로 정의 가능.
- 정의된 도메인명은 일반적인 데이터 타입처럼 사용.
> **CREATE DOMAIN** 도메인명 [**AS**] 데이터_타입<br>
>> [**DEFAULT** 기본값]<br>
>> [**CONSTRAINT** 제약조건명 CHECK (범위값)];
##### 🔖 도메인(Domain)
- 하나의 속성이 취할 수 있는 동일한 유형의 원자값들의 집합.
##### 🔖 SQL에서 지원하는 기본 데이터 타입
- 정수(Integer) : `INTEGER(4byte 정수)`, `SMALLINT(2byte 정수)`
- 실수(Float) : `FLOAT`, `REAL`, `DOUBLE PRECISION`
- 형식화된 숫자 : `DEC(i, j) (i: 전체 자릿수, j: 소수부 자릿수)`
- 고정길이 문자 : `CHAR(n)`, `CHARACTER(n)` (n: 문자 수)
- 가변길이 문자 : `VARCHAR(n)`, `CHARACTER VARYING(n)` (n: 최대 문자 수)
- 고정길이 비트열(Bit String) : `BIT(n)`
- 가변길이 비트열 : `VARBIT(n)`
- 날짜 : `DATE`
- 시간 : `TIME`
##### ‼️ CHAR와 VARCHAR
- **CHAR** : 지정된 크기만큼 기억 장소가 확보됨.
- **VARCHAR** : 기억 장소의 크기가 지정되어도 필드에 저장된 데이터만큼만 기억 장소가 확보됨.
<br>

#### 💡 CREATE TABLE
- `테이블을 정의`하는 명령문.
- 기본 테이블에 포함될 모든 속성에 대해 속성명과 그 속성의 데이터 타입, 기본값, NOT NULL 여부 등을 지정.
> **CREATE TABLE** 테이블명<br>
>> (속성명 데이터_타입 [**DEFAULT** 기본값] [**NOT NULL**], ...<br>
>> [, **PRIMARY KEY**(기본키_속성명, ...)]<br>
>> [, **UNIQUE**(대체키_속성명, ...)]<br>
>> [, **FOREIGN KEY**(외래키_속성명, ...)]<br>
>>> [**REFERENCES** 참조 테이블(기본키_속성명, ...)]<br>
>>> [**ON DELETE** 옵션]<br>
>>> [**ON UPDATE** 옵션]<br>

>> [, **CONSTRAINT** 제약조건명] [**CHECK** (조건식)]);
<br>

#### 💡 CREATE VIEW
- `뷰를 정의`하는 명령문.
- SELECT문을 서브 쿼리로 사용하여 SELECT문의 결과로서 뷰를 생성함.
- 서브 쿼리인 SELECT문에는 UNION이나 ORDER BY절을 사용할 수 없음.
- 속성명을 기술하지 않을 경우, SELECT문의 속성명이 자동으로 사용됨.
> **CREATE VIEW** 뷰명[(속성명[, 속성명, ...])]<br>
> **AS SELECT**문;
##### 🔖 뷰(View)
- 하나 이상의 기본 테이블로부터 유도되는 이름을 갖는 가상 테이블(Virtual Table)
<br>

#### 💡 CREATE INDEX
- `인덱스를 정의`하는 명령문.
> **CREATE** [UNIQUE] **INDEX** 인덱스명<br>
> **ON** 테이블명(속성명 [ASC | DESC] [, 속성명 [ASC | DESC]])<br>
> [CLUSTER];
##### 🔖 클러스터드 인덱스(Clustered Index)
- 인덱스 키의 순서에 따라 데이터가 정렬되어 저장되는 방식.
- 실제 데이터가 순서대로 저장되어 있어, 인덱스 검색 없이도 원하는 데이터를 빠르게 찾을 수 있음.
##### 🔖 넌 클러스터드 인덱스(Non-Clustered Index)
- 인덱스의 키 값만 정렬되어 있을 뿐, 실제 데이터는 정렬되지 않은 방식.
- 데이터 검색을 위해서는 먼저 인덱스를 검색하여 실제 데이터의 위치를 확인해야 하므로, 클러스터드 인덱스에 비해 검색 속도가 떨어짐.
<br>

#### 💡 ALTER TABLE
- 테이블에 대한 `정의를 변경`하는 명령문.
> **ALTER TABLE** 테이블명 **ADD** 속성명 데이터_타입 [DEFAULT '기본값']; ➡️ 새로운 속성(열)을 추가할 때 사용.<br>
> **ALTER TABLE** 테이블명 **ALTER** 속성명 [SET DEFAULT '기본값']; ➡️ 특정 속성의 DEFAULT 값을 변경할 때 사용.<br>
> **ALTER TABLE** 테이블명 **DROP COLUMN** 속성명 [CASCADE]; ➡️ 특정 속성을 삭제할 때 사용.
<br>

#### 💡 DROP
- 스키마, 도메인, 기본 테이블, 뷰 테이블, 인덱스, 제약 조건 등을 제거하는 명령문.
> **DROP SCHEMA** 스키마명 [CASCADE | RESTRICT];<br>
> **DROP DOMAIN** 도메인명 [CASCADE | RESTRICT];<br>
> **DROP TABLE** 테이블명 [CASCADE | RESTRICT];<br>
> **DROP VIEW** 뷰명 [CASCADE | RESTRICT];<br>
> **DROP INDEX** 인덱스명 [CASCADE | RESTRICT];<br>
> **DROP CONSTRAINT** 제약조건명;
##### 🔖 CASCADE와 RESTRICT
- `CASCADE` : 제거할 요소를 참조하는 다른 모든 개체를 함께 제거. ➡️ 계단식, 연속형
- `RESTRICT` : 다른 개체가 제거할 요소를 참조 중일 때는 제거를 취소.
