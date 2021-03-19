# promethues
kube-promethues安装
https://github.com/prometheus-operator/kube-prometheus

这个仓库包括：kubernetes清单、granfana dashboard以及promethues rules。同时还包括容易上手的安装脚本。

组件包括：
The Prometheus Operator
高可用Prometheus
高可用Alertmanager
Prometheus node-exporter
Prometheus Adapter for Kubernetes Metrics APIs
kube-state-metrics
Grafana

manifests已经经过二次修改,对应官方分支release-0.7
1. 开始安装  
[root@k8s-master manifests]# kubectl apply -f setup/
2. 创建本地持久化存储,修改主机名和目录后执行  
[root@k8s-master manifests]# kubectl apply -f store_local/
3. 修改alertmanager-secret.yaml,增加报警邮箱  
[root@k8s-master manifests]# kubectl apply -f .

查看pod是否正常
kubectl get pod -n monitoring
