# try-krew-custom-plugin-index

Add this repository as krew custom plugin index:
```
$ kubectl krew index add superbrothers-sandbox git://github.com/superbrothers-sandbox/try-krew-custom-plugin-index
WARNING: You have added a new index from "git://github.com/superbrothers-sandbox/try-krew-custom-plugin-index"
The plugins in this index are not audited for security by the Krew maintainers.
Install them at your own risk.
```

List custom plugin indexes:
```
$ kubectl krew index list
INDEX                  URL
default                https://github.com/kubernetes-sigs/krew-index.git
superbrothers-sandbox  git://github.com/superbrothers-sandbox/try-krew-custom-plugin-index
```

Search plugins from the custom plugin index:
```
$ kubectl krew search | grep superbrothers-sandbox
superbrothers-sandbox/open-svc  Open the Kubernetes URL(s) for the specified se...  no
```

Install a plugin from the custom plugin index:

```
$ kubectl krew install superbrothers-sandbox/open-svc
```

Uninstall a plugin:

```
$ kubectl krew uninstall superbrothers-sandbox/open-svc
F0805 16:22:41.746998   27324 root.go:79] uninstall command does not support INDEX/PLUGIN syntax; just specify PLUGIN
$ kubectl krew uninstall open-svc
Uninstalled plugin open-svc
```

Remove the custom plugin index:
```
$ kubectl krew index remove superbrothers-sandbox
```
