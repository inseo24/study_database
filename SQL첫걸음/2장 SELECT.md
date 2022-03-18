# 2장 테이블에서 데이터 검색(SELECT)

1. 데이터의 종류
    1. 데이터는 자료형으로 분류할 수 있고, 열은 하나의 자료형만 가질 수 있다.
    2. 수치형 데이터: 숫자만으로 구성된 데이터
    3. 문자열형 데이터: 임의의 문자로 구성된 데이터. 왼쪽 정렬 표시.
    4. 날짜시간형 데이터: 날짜와 시각을 나타내는 데이터. 왼쪽 정렬 표시.
2. NULL: 데이터가 들어있지 않은 것을 의미하는 특별한 값
3. 테이블 구조 참조
    1. DESC 테이블명;
    2. DESC 명령으로 테이블에 어떤 열이 정의되어 있는지 알 수 있음(테이블 구조 참조)
    3. DESC는 SQL 명령이 아니다.
4. 자료형
    1. INTEGER
    2. CHAR - 고정 길이 문자열
    3. VARCHAR - 가변 길이 문자열
    4. DATE
    5. TIME
5. 검색 조건 지정하기
    1. SELECT 열1, 열2 FROM 테이블명 WHERE 조건식
    2. 값이 서로 다른 경우 ‘<>’ 사용
        1. SELECT * FROM sample21 WHERE no <> 2;
    3. NULL값 검색
        1. SELECT * FROM sample21 WHERE birthday = NULL;
        2. SELECT * FROM sample21 WHERE birthday IS NULL;
    4. 조건 조합하기
        1. 조건식1 AND 조건식2
            1. WHERE a <> 0 AND b <>0
        2. 조건식1 OR 조건식2
            1. WHERE a <> 0 OR b <>0
            2. a열이 1 또는 2이고, b열이 1 또는 2인 행 검색
                1. WHERE a=1 OR a=2 AND b=1 OR b=2;
                2. AND가 OR보다 우선순위가 높다
        3. NOT 조건식
            1. WHERE NOT(a<>0 OR b<>0)
6. 패턴 매칭에 의한 검색
    1. 열 LIKE 패턴
    2. 패턴 정의 시 사용할 수 있는 메타문자로 %, _가 있다.
    3. WHERE text LIKE ‘%SQL%’
    4. %는 임의의 문자열과 매치하며, 빈 문자열에도 매치한다.
    5. 특수문자 검색할 때는 이스케이프 사용(\) - LIKE ‘%\%%’
    6. 문자열 상수 이스케이프 - It’s → ‘It’’s’, ‘ → ‘’’’
    7. ‘을 문자열 상수 안에 포함할 때는 ‘를 2개 연속해서 쓰면 도니다.