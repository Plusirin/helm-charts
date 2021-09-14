# RELEASE:nexus-3.27.0

RELEASE_NAME := nexus
NAMESPACE := middleware
STORAGECLASS := rook-cephfs
PASSWORD := 000000
HTTPHOST := 192.168.100.51

install:
	helm install $(RELEASE_NAME) -n $(NAMESPACE) . \
	--set initAdminPassword.enabled=true \
	--set nexusProxy.env.nexusDockerHost=$(HTTPHOST) \
	--set nexusProxy.env.nexusHttpHost=$(HTTPHOST) \
	--set persistence.storageClass=$(STORAGECLASS)


uninstall:
	helm uninstall $(RELEASE_NAME) -n $(NAMESPACE)
