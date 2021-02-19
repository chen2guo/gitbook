## 第一节

### k8s 常见命令
#### 获取节点和服务版本信息
`# kubectl get node`
####  获取节点和服务版本信息，并查看附加信息
`# kubectl get nodes -o wide`

####  获取pod信息，默认是default名称空间
`# kubectl get pod`

####  获取pod信息，默认是default名称空间，并查看附加信息【如：pod的IP及在哪个节点运行】
`#kubectl get pod -o wide`
#### 获取指定名称空间的pod
`#kubectl get pod -n kube-system`
####  获取指定名称空间中的指定pod
`#kubectl get pod -n kube-system podName`
####  获取所有名称空间的pod
`# kubectl get pod -A`
####  查看pod的详细信息，以yaml格式或json格式显示
`# kubectl get pods -o yaml`

`# kubectl get pods -o json`

####  查看pod的标签信息
`# kubectl get pod -A --show-labels`
####  根据Selector（label query）来查询pod
`# kubectl get pod -A --selector="k8s-app=kube-dns"`

####  查看运行pod的环境变量
`# kubectl exec podName env`
####  查看指定pod的日志
`# kubectl logs -f --tail 500 -n kube-system kube-apiserver-k8s-master`

####  查看所有名称空间的service信息
`# kubectl get svc -A`
####  查看指定名称空间的service信息
`# kubectl get svc -n kube-system`

####  查看componentstatuses信息
`# kubectl get cs`
####  查看所有configmaps信息
`# kubectl get cm -A`
####  查看所有serviceaccounts信息
`# kubectl get sa -A`
####  查看所有daemonsets信息
`# kubectl get ds -A`
####  查看所有deployments信息
`# kubectl get deploy -A`
####  查看所有replicasets信息
`# kubectl get rs -A`
####  查看所有statefulsets信息
`# kubectl get sts -A`
####  查看所有jobs信息
`# kubectl get jobs -A`
####  查看所有ingresses信息
`# kubectl get ing -A`
####  查看有哪些名称空间
`# kubectl get ns`

####  查看pod的描述信息
`# kubectl describe pod podName`

`# kubectl describe pod -n kube-system kube-apiserver-k8s-master`
####  查看指定名称空间中指定deploy的描述信息
`# kubectl describe deploy -n kube-system coredns`

####  查看node或pod的资源使用情况，需要heapster 或metrics-server支持
`# kubectl top node`
`# kubectl top pod`

####  查看集群信息
`# kubectl cluster-info   或  kubectl cluster-info dump`
####  查看各组件信息【172.16.1.110为master机器】
`# kubectl -s https://172.16.1.110:6443 get componentstatuses`
