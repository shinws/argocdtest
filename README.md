# ArgoCD_TestResources
ArgoCD 예제를 위한 쿠버네티스 리소스 저장소 입니다.

***
디렉터리 및 파일 구조는 아래와 같습니다. <br>


```
└── /resources
    ├── /base # 기본 manifest 리소스 
    │   ├── deployment.yaml
    │   └── service.yaml
    │
    ├── /helm # helm chart를 사용한 manifest 리소스
    │   ├── /templates
    │   │   ├── deployment.yaml
    │   │   └── service.yaml
    │   ├── Chart.yaml
    │   └── values.yaml
    │
    └── /helm-rollout # helm chart 및 Argo Rollouts를 사용한 manifest 리소스
        ├── /templates
        │   ├── rollout.yaml
        │   ├── service-active.yaml # Blue 전용 service 
        │   └── service-preview.yaml # Green 전용 service 
        ├── Chart.yaml
        └── values.yaml
```

<!--
```
├── /resources
    ├── /base
    │   ├── deployment.yaml
    │   ├── service.yaml
    │   └── kustomization.yaml
    └── /overlays
        ├── deployment-patch.yaml
        ├── service-patch.yaml
        └── kustomization.yaml
```


<br>
구조에 대한 설명은 아래와 같습니다. <br>

- /base : 쿠버네티스의 원본 manifest 리소스를 저장하는 공간입니다.
  - service.yaml : Pod의 내부 및 외부 네트워크를 설정하기 위한 리소스 입니다.
  - deployment.yaml : Pod를 클러스터에 배포하기 위한 리소스 입니다.
  - kustomization.yaml : kustomize가 관리해야할 원본 리소스가 어떻게 구성되는지 등록하는 리소스 입니다.
- /overlays : kustomize를 사용하여 원본 manifest 리소스의 일부 값을 변경하기 위한 patch 리소스를 저장하는 공간입니다.
  - service-patch.yaml : service.yaml의 일부 내용을 변경하기 위한 리소스 입니다.
  - deployment-patch.yaml : deployment.yaml의 일부 내용을 변경하기 위한 리소스 입니다.
  - kustomization.yaml : service.yaml 혹은 deployment.yaml의 어느 부분을 수정할 것인지에 대한 내용을 기록하는 리소스 입니다.

-->