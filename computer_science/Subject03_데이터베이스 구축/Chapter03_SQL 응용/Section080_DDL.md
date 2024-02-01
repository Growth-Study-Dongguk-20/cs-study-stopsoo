## CS Study - Section080 DDL
### ✏️ Study
#### 💡 DDL(Data Definition Language, 데이터 정의어)의 개요
- DB 구조, 데이터 형식, 접근 방식 등 DB를 구축하거나 수정할 목적으로 사용하는 언어.
- 번역한 결과를 `데이터 사전(Data Dictionary)`에 여러 개의 테이블로서 저장.
<br>

#### 💡 CREATE SCHEMA
- `스키마를 정의`하는 명령문.
> **CREATE SCHEMA** 스키마명 **AUTHORIZATION** 사용자_id;
<br>

#### 💡 CREATE DOMAIN
- `도메인을 정의`하는 명령문.
> **CREATE DOMAIN** 도메인명 [**AS**] 데이터_타입<br>
>     [**DEFAULT** 기본값]<br>
>     [**CONSTRAINT** 제약조건명 CHECK (범위값)];
<br>

#### 💡 CREATE TABLE
- `테이블을 정의`하는 명령문.
> **CREATE TABLE** 테이블명<br>
>     (속성명 데이터_타입 [**DEFAULT** 기본값] [**NOT NULL**], ...<br>
>     [, **PRIMARY KEY**(기본키_속성명, ...)]<br>
>     [, **UNIQUE**(대체키_속성명, ...)]<br>
>     [, **FOREIGN KEY**(외래키_속성명, ...)]<br>
>         [**REFERENCES** 참조 테이블(기본키_속성명, ...)]<br>
>         [**ON DELETE** 옵션]<br>
>         [**ON UPDATE** 옵션]<br>
>     [, **CONSTRAINT** 제약조건명] [**CHECK** (조건식)]);
<br>

#### 💡 CREATE VIEW
- `뷰를 정의`하는 명령문.
> **CREATE VIEW** 뷰명[(속성명[, 속성명, ...])]<br>
> **AS SELECT**문;
<br>

#### 💡 CREATE INDEX
- `인덱스를 정의`하는 명령문.
> **CREATE** [UNIQUE] **INDEX** 인덱스명<br>
> **ON** 테이블명(속성명 [ASC | DESC] [, 속성명 [ASC | DESC]])<br>
> [CLUSTER];
<br>

#### 💡 ALTER TABLE
- 테이블에 대한 정의를 `변경`하는 명령문.
> **ALTER TABLE** 테이블명 **ADD** 속성명 데이터_타입 [DEFAULT '기본값'];<br>
> **ALTER TABLE** 테이블명 **ALTER** 속성명 [SET DEFAULT '기본값']; ➡️ 특정 속성의 DEFAULT 값을 변경할 때 사용.<br>
> **ALTER TABLE** 테이블명 **DROP COLUMN** 속성명 [CASCADE];
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
- `CASCADE` : 제거할 요소를 참조하는 다른 모든 개체를 함께 제거.
- `RESTRICT` : 다른 개체가 제거할 요소를 참조 중일 때는 제거를 취소.