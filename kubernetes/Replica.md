## ReplicaSet

ReplicaSet으로 Pod 레플리케이션 설정 방법 

- ReplicaSet을 이용해서 Pod 복제본(replicas)을 생성하고 관리한다 

- 여러 노드에 걸쳐 배포된 Pod Up/Down 상태를 감시하고 replicas 수만큼 실행을 보장한다

- ReplicaSet의 spec.selector.matchLabels는 

  Pod Template 부분의 tspec.template.metada.labels와 같아야 한다 

- spec.replicas를 선언하지 않으면 기본값은 1이다