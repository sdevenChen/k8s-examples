istio 
查看 Istio Dashboard
验证 prometheus 服务正在集群中运行。
在 Kubernetes 环境中，执行以下命令：
~~~
$ kubectl -n istio-system get svc prometheus
NAME         CLUSTER-IP     EXTERNAL-IP   PORT(S)    AGE
prometheus   10.59.241.54   <none>        9090/TCP   2m
~~~
验证 Grafana 服务正在集群中运行。
在 Kubernetes 环境中，执行以下命令：
~~~
$ kubectl -n istio-system get svc grafana
NAME      CLUSTER-IP      EXTERNAL-IP   PORT(S)    AGE
grafana   10.59.247.103   <none>        3000/TCP   2m
~~~
通过 istioctl 命令 打开 Istio Dashboard。
支持以下web ui 
~~~
  controlz    Open ControlZ web UI
  envoy       Open Envoy admin web UI
  grafana     Open Grafana web UI
  jaeger      Open Jaeger web UI
  kiali       Open Kiali web UI
  prometheus  Open Prometheus web UI
  zipkin      Open Zipkin web UI
~~~
打开grafana web-ui
~~~
istioctl dashboard  grafana
~~~
其他weui 执行命令 istioctl dashboard xxx

WEB UI默认用户/密码
~~~
kiali: admin/admin
~~~