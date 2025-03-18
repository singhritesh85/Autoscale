To install karpenter edit the configmap **aws-auth** present in the namespace **kube-system**.

![image](https://github.com/user-attachments/assets/853eb44c-63e3-49c6-ae39-a980306d535d)
![image](https://github.com/user-attachments/assets/f20f184f-d977-4a94-9b03-5c7f96165f78)

I had installed Karpenter Controller using the helm with the help of the command as shown in the scrrenshot attcahed below.

```
helm upgrade --install karpenter oci://public.ecr.aws/karpenter/karpenter --version "1.3.2" --namespace "karpenter" --create-namespace --set "settings.clusterName=eks-demo-cluster-dev" --set "serviceAccount.annotations.eks\.amazonaws\.com/role-arn=arn:aws:iam::02XXXXXXXXX6:role/karpenter-controller-role" --set controller.resources.requests.cpu=1 --set controller.resources.requests.memory=1Gi --set controller.resources.limits.cpu=1 --set controller.resources.limits.memory=1Gi
```
![image](https://github.com/user-attachments/assets/ad8eb1b6-c6e7-4de2-87e8-785e65316e24)
