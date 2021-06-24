# helm-github-repository

```
[root@k8s-helm ~]# helm create gitrepotest
Creating gitrepotest

```
```
[root@k8s-helm ~]# cd gitrepotest/
[root@k8s-helm gitrepotest]# ll
total 8
drwxr-xr-x 2 root root    6 Jun 24 11:35 charts
-rw-r--r-- 1 root root  107 Jun 24 11:35 Chart.yaml
drwxr-xr-x 3 root root  146 Jun 24 11:35 templates
-rw-r--r-- 1 root root 1512 Jun 24 11:35 values.yaml
[root@k8s-helm gitrepotest]# vi Chart.yaml


Just do some change in Chart.yaml

switch to helm repo
cd helm-github-repository

[root@k8s-helm helm-github-repository]# helm package ~/gitrepotest/
Successfully packaged chart and saved it to: /root/helm-github-repository/gitrepotest-0.1.0.tgz

[root@k8s-helm helm-github-repository]# ls
gitrepotest-0.1.0.tgz  README.md

[root@k8s-helm helm-github-repository]# helm repo index .
[root@k8s-helm helm-github-repository]# ll
total 12
-rw-r--r-- 1 root root 3266 Jun 24 11:40 gitrepotest-0.1.0.tgz
-rw-r--r-- 1 root root  379 Jun 24 11:42 index.yaml
-rw-r--r-- 1 root root   25 Jun 24 11:29 README.md

[root@k8s-helm helm-github-repository]# helm repo list
NAME    URL
stable  https://charts.helm.sh/stable
local   http://127.0.0.1:8879/charts

[root@k8s-helm helm-github-repository]# helm repo add --username jniranjanreddy --password <token> helm-github-repository 'https://raw.githubusercontent.com/jniranjanreddy/helm-github-repository/master'
"helm-github-repository" has been added to your repositories

[root@k8s-helm helm-github-repository]# helm repo list
NAME                    URL
stable                  https://charts.helm.sh/stable
local                   http://127.0.0.1:8879/charts
helm-github-repository  https://raw.githubusercontent.com/jniranjanreddy/helm-github-repository/master
[root@k8s-helm helm-github-repository]#


```
