# Docker containers behind a load balancer

## AWS
```
   User --> LB
  
  subgraph AWS
    TemplateAPI[REST_API_TEMPLATE_CODE ]

    LB[ALB -=AWS Load Balancer=-]
    LB --> K8S_AWS
    subgraph K8S_AWS[Kubernetes on EKS]
      DockerPodA[Docker Container Pod A]
      DockerPodB[Docker Container Pod B]

      DockerPodA-->TemplateAPI
      DockerPodB-->TemplateAPI

    end
  end
```
## Azure
