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
