# charts for okteto deployment

With free kubernetes platform provided by https://cloud.okteto.com, we can easily deploy application with public accessible url 

# changes 

The main change is to enable auto-ingress to get public endpoint

```diff
-  serviceAnnotations: {}
+  serviceAnnotations:
+    dev.okteto.com/auto-ingress: "true"
```

# changed charts list for okteto

* `Jenkins` - [stable/jenkins/values.yaml](stable/jenkins/values.yaml)

# Known issues

* `Jenkins` - after you deploy the charts, you change some setting, such as `jnlp-slave` image's tag, even you redeploy the charts, the old setting isn't updated. You have to exec in jenkins master container, and update its config file `/var/jenkins_home/config.xml
