# RELEASE:zookeeper-3.6.2

RELEASE_NAME := zookeeper
NAMESPACE := middleware
STORAGECLASS := rook-cephfs


install:
	helm install $(RELEASE_NAME) -n $(NAMESPACE) . \
	--set replicaCount=3 \
	--set auth.enabled=false \
	--set allowAnonymousLogin=true \
	--set global.storageClass=$(STORAGECLASS)

uninstall:
	helm uninstall $(RELEASE_NAME) -n $(NAMESPACE)
