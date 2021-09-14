# RELEASE:kafka-2.7.0

RELEASE_NAME := kafka
NAMESPACE := middleware
STORAGECLASS := rook-cephfs


install:
	helm install $(RELEASE_NAME) -n $(NAMESPACE) . \
	--set replicaCount=3 \
	--set zookeeper.enabled=false \
	--set global.storageClass=$(STORAGECLASS) \
	--set externalZookeeper.servers=zookeeper.middleware.svc.cluster.local

uninstall:
	helm uninstall $(RELEASE_NAME) -n $(NAMESPACE)
