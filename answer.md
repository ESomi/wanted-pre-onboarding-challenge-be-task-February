<div style="width: 80%;">
1. 관계형 데이터베이스(RDBMS)와 비관계형 데이터베이스(NoSQL)의 장단점 비교

- 관게형 데이터베이스의 장점
  정해진 스키마에 따라 데이터를 저장하여야 하므로 명확한 데이터 구조를 보장하고 있으며, 각 데이터를 중복없이 한 번만 저장할 수 있습니다.
  각 데이터를 중복없이 한 번만 저장할 수 있습니다.
- 관게형 데이터베이스의 단점
  테이블간테이블 간 관계를 맺고 있어 시스템이 커질 경우 JOIN문이 많은 복잡한 쿼리가 만들어질 수 있습니다.
  성능 향상을 위해서는 서버의 성능을 향상 시켜야하는 Scale-up만을 지원합니다. 이로 인해 비용이 기하급수적으로 늘어날 수 있습니다.
  스키마로 인해 데이터가 유연하지 못합니다. 나중에 스키마가 변경 될 경우 번거롭고 어렵습니다.
- 비관계형 데이터베이스의 장점
  NoSQL에서는 스키마가 없기 때문에 유연하며 자유로운 데이터 구조를 가질 수 있습니다. 언제든 저장된 데이터를 조정하고 새로운 필드를 추가할 수 있습니다.
  데이터 분산이 용이하며 성능 향상을 위한 Saclue-up 뿐만이 아닌 Scale-out 또한 가능합니다.
- 비관계형 데이터베이스의 단점
  데이터 중복이 발생할 수 있으며 중복된 데이터가 변경 될 경우 수정을 모든 컬렉션에서 수행을 해야 합니다.
  스키마가 존재하지 않기에 명확한 데이터 구조를 보장하지 않으며 데이터 구조 결정가 어려울 수 있습니다.

2. 트랜잭션(transaction)이란 무엇인가요?

- 트랜잭션이란 전부 아니면 전무인 단일 작업 단위로 실행되는 일련의 하나 이상의 작업을 의미합니다.
  트랜잭션의 목적은 시스템 장애나 오류가 발생하더라도 데이터베이스가 일관된 상태를 유지하도록 하는 것입니다.
  트랜잭션은 일반적으로 삽입, 업데이트 또는 삭제와 같은 여러 데이터베이스 작업을 포함하며 모두 성공적으로 완료되거나 데이터베이스를 이전 상태로 되돌려야 합니다.
  트랜잭션은 데이터베이스 관리 시스템(DBMS)에 의해 관리되며 특히 데이터의 무결성과 일관성을 보장해야 하는 미션 크리티컬 애플리케이션의 경우 데이터베이스 시스템의 중요한 측면입니다.

3. MySQL에서 조인(join)의 역할은 무엇인가요? 다양한 join의 방식에 대해 설명해주세요.

- 조인은 두 개 이상의 테이블에서 테이블 간의 관련 열을 기반으로 하는 단일 결과 집합으로 행을 결합하는 데 사용됩니다. 마치 단일 테이블인 것처럼 여러 테이블에서 데이터를 쿼리하는 데 사용됩니다.
- join의 방식
  1. INNER JOIN
     두 테이블에서 일치하는 값을 가진 행만 반환합니다.
     2)LEFT JOIN(또는 LEFT OUTER JOIN)
     왼쪽 테이블(table1)의 모든 행과 오른쪽 테이블(table2)의 일치하는 행을 반환합니다. 결과에는 오른쪽 테이블의 일치하지 않는 행에 대한 NULL 값이 포함됩니다.
  2. RIGHT JOIN(또는 RIGHT OUTER JOIN)
     오른쪽 테이블(table2)의 모든 행과 왼쪽 테이블(table1)의 일치하는 행을 반환합니다. 결과에는 왼쪽 테이블의 일치하지 않는 행에 대한 NULL 값이 포함됩니다.
  3. FULL OUTER JOIN
     일치하지 않는 행을 포함하여 두 테이블의 모든 행을 반환합니다. 결과에는 두 테이블의 일치하지 않는 행에 대한 NULL 값이 포함됩니다.
  4. CROSS JOIN
     두 테이블의 데카르트 곱을 반환합니다. 즉, 두 테이블에서 가능한 모든 행 조합을 반환합니다.

4. MySQL에서 인덱스(index)란 무엇인가요?

- 인덱스는 테이블의 행에 대한 빠른 액세스 경로를 제공하는 데이터베이스 구조입니다.
  인덱스는 인덱싱된 열의 값과 테이블의 해당 행 사이의 매핑을 제공하여 데이터베이스 관리 시스템(DBMS)이 필요한 행을 빠르게 찾을 수 있도록 합니다.인덱스는 특정 행 검색이 인덱스 없이 느려질 수 있는 대형 테이블을 처리할 때 특히 유용합니다. 쿼리의 WHERE 절에 사용된 열에 인덱스를 생성함으로써 MySQL은 쿼리 실행 시간을 크게 단축할 수 있습니다.

  MySQL에는 B-트리 인덱스, 해시 인덱스 및 전체 텍스트 인덱스를 포함하여 다양한 유형의 인덱스가 있습니다. B-트리 인덱스는 가장 일반적으로 사용되며 광범위한 데이터 유형 및 연산자를 지원합니다. 해시 인덱스는 대규모 데이터 세트에 대한 동등 조회와 같은 특정 사용 사례에 사용됩니다. 전체 텍스트 인덱스는 텍스트 기반 검색에 사용되므로 큰 텍스트 열을 빠르게 검색할 수 있습니다.

  인덱스는 테이블의 하나 이상의 열에 생성되며 너무 많은 인덱스를 추가하면 테이블의 쓰기 성능이 느려질 수 있으므로 인덱싱할 올바른 열을 선택하는 것이 중요합니다. 빠른 검색 성능을 위해 인덱스를 최적화된 상태로 유지하기 위해 인덱스를 정기적으로 유지 관리하는 것도 중요합니다.

</div>
