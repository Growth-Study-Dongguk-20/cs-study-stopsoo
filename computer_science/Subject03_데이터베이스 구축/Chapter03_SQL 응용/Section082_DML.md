## CS Study - Section082 DML
### ✏️ Study
#### 💡 DML(Data Manipulation Language, 데이터 조작어)의 개요
- 데이터베이스 사용자가 응용 프로그램이나 질의어를 통해 저장된 데이터를 실질적으로 관리하는데 사용되는 언어.
- 데이터베이스 사용자와 데이터베이스 관리 시스템 간의 인터페이스를 제공.
- 유형
  - `SELECT` : 테이블에서 튜플을 검색.
  - `INSERT` : 테이블에서 새로운 튜플을 삽입.
  - `DELETE` : 테이블에서 튜플을 삭제.
  - `UPDATE` : 테이블에서 튜플의 내용을 갱신. 
<br>

#### 💡 삽입문(INSERT INTO ~ VALUES ~)
- 기본 테이블에 새로운 튜플을 삽입할 때 사용.
- 대응하는 속성과 데이터는 **개수**와 **데이터 유형**이 일치해야 함.
- 기본 테이블의 모든 속성을 사용할 경우, 속성명 생략 가능.
- `SELECT문`을 사용해 다른 테이블의 검색 결과를 삽입 가능.
> INSERT INTO 테이블명([속성명1, 속성명2, ...])<br>
> VALUES (데이터1, 데이터2, ...);
<br>

#### 💡 삭제문(DELETE FROM ~ [WHERE ~])
- 기본 테이블에 있는 튜플들 중 특정 튜플을 삭제할 때 사용.
- 모든 레코드 삭제 시 WHERE절 생략.
- DELETE문은 테이블 구조나 테이블 자체는 그대로 남겨두고 튜플만 삭제.
> DELETE<br>
> FROM 테이블명<br>
> [WHERE 조건];
<br>

#### 💡 갱신문(UPDATE ~ SET ~ [WHERE ~])
- 기본 테이블에 있는 튜플들 중 특정 튜플의 내용을 변경할 때 사용.
> UPDATE 테이블명<br>
> SET 속성명 = 데이터[, 속성명=데이터, ...]<br>
> [WHERE 조건];
