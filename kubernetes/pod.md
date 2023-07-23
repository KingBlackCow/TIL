## Pod 

### pod란?

- 노드에서 컨테이너를 실행하기 위한 가장 기본적인 배포 단위 
- 여러 노드에 1개 이상의 Pod을 분산 배포/실행 가능 (Pod Replicas)

### pod 특징

- 쿠버네티스는 Pod을 생성할 때 노드에서 유일한 IP를 할당 (서버 분리 효과) -
-  Pod 내부 컨테이너 간에 localhost로 통신 가능, 포트 충돌 주의!
-  Pod 안에서 네트워크와 볼륨 등 자원을 공유
- PodIP는 클러스터 안에서만 접근할 수 있다(클러스터 외부 트래픽을 받기 위해서는 Service 혹은 Ingress 오브젝트가 필요)

### 노드에 배포되는 과정 

1. 사용자로부터 Pod 배포 요청을 수락한다 
2. 요청 받은 수만큼 Pod Replica를 생성한다 (Pod desired state == current state)

3. Pod을 배포할 적절한 노드를 선택한다 (nodeSelector) 

4. 5에게 이미지 다운로드를 명령하고 Pod 실행을 준비한다. Pod 상태를 업데이트한다.
5. 이미지를 다운로드하고 컨테이너를 실행한다

### Pod 오브젝트 표현 방법

![image-20230723014736044](/Users/admin/Library/Application Support/typora-user-images/image-20230723014736044.png)

### Pod 생성과 배포 

- Pod은 여러 개의 컨테이너를 포함할 수 있고 하나의 노드에 배포된다 
- Pod을 YAML 파일로 정의 해두면 필요할 때 원하는 수 만큼 노드에 배포할 수 있다 
- Pod과 컨테이너를 1:1로 기본 설계하고 특별한 사유가 있는 경우 1:N 구조를 고민한다

### Pod IP

- 쿠버네티스는 Pod을 생성할 때 클러스터 내부에서만 접근할 수 있는 IP를 할당한다 
- Pod IP는 컨테이너와 공유되기 때문에 컨테이너 간 포트 충돌을 주의해야 한다 
- 하나의 Pod에 속한 컨테이너들은 localhost로 통신할 수 있다. 
- 다른 Pod(컨테이너)과 통신은 Pod IP를 이용한다

### Label과 Selector 

- 쿠버네티스 오브젝트 metadata.labels 속성으로 리소스에 Label을 추가할 수 있다. 
- Label은 key/value 쌍으로 선언한다. 
- 쿠버네티스 오브젝트에 선언한 Label의 key, value를 기준으로 원하는 리소스를 필터링할 수 있다. 
- 필터링 하기 위한 조건을 Selector로 정의한다. (label query) 
- 즉 Label과 Selector를 사용하면 특정 리소스들의 집합을 구할 수 있다. 
- kubectl get 명령어를 사용할 때 label query를 지정하기 위해 --selector 또는 ‒l 옵션을 사용한다