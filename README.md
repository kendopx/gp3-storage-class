
```sh
helm repo add aws-ebs-csi-driver https://kubernetes-sigs.github.io/aws-ebs-csi-driver/
helm repo update

kubectl apply -f gp3.yaml 
kubectl get pods -n kube-system | grep ebs-csi

kubectl annotate storageclass gp3 storageclass.kubernetes.io/is-default-class=true --overwrite
kubectl annotate storageclass gp2 storageclass.kubernetes.io/is-default-class=false --overwrite
kubectl get storageclass

```