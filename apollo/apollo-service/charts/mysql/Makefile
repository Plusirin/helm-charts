# RELEASE:mysql-8.0.26


RELEASE_NAME := mysql
NAMESPACE := middleware
STORAGECLASS := rook-cephfs


install:
	helm install $(RELEASE_NAME) -n $(NAMESPACE) . \
	--set global.storageClass=$(STORAGECLASS) \
	--set architecture=standalone \
	--set primary.persistence.enabled=true \
	--set primary.persistence.size=5Gi \
	--set primary.service.type=NodePort \
	--set primary.service.port=3306 \
	--set primary.service.nodePort=30337


uninstall:
	helm uninstall $(RELEASE_NAME) -n $(NAMESPACE)



dry-run:
	helm install $(RELEASE_NAME) -n $(NAMESPACE) . \
	--set global.storageClass=$(STORAGECLASS) \
	--set architecture=standalone \
	--set primary.persistence.enabled=true \
	--set primary.persistence.size=5Gi \
	--set primary.service.type=NodePort \
	--set primary.service.port=3306 \
	--set primary.service.nodePort=30337 \
	--dry-run
