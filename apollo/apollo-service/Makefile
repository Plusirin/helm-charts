# RELEASE:apollo-service-env-1.9.0

RELEASE_NAME := apollo-service-$(env)
NAMESPACE := middleware
STORAGECLASS := rook-cephfs


install:
	helm install $(RELEASE_NAME) . \
	--namespace $(NAMESPACE) \
	--set configdb.userName=apollo \
	--set configdb.password=apollo \
	--set configdb.service.enabled=false \
	--set configService.replicaCount=1 \
	--set adminService.replicaCount=1 \
	--set global.storageClass=$(STORAGECLASS)

install-mysql:
	#  --set primary.service.nodePort=30337
	helm install $(RELEASE_NAME) . \
	--namespace $(NAMESPACE) \
	--set configdb.userName=apollo \
	--set configdb.password=apollo \
	--set configdb.service.enabled=false \
	--set configService.replicaCount=1 \
	--set adminService.replicaCount=1 \
	--set global.storageClass=$(STORAGECLASS) \
	--set architecture=standalone \
	--set primary.persistence.enabled=true \
	--set primary.persistence.size=5Gi \
	--set primary.service.type=NodePort \
	--set primary.service.port=3306


uninstall:
	helm uninstall $(RELEASE_NAME) -n $(NAMESPACE)


dry-run:
	#--set configdb.host=apollo-service-pro-mysql.middleware.svc.cluster
	helm install $(RELEASE_NAME) . \
        --namespace $(NAMESPACE) \
        --set configdb.userName=apollo \
        --set configdb.password=apollo \
        --set configdb.service.enabled=false \
        --set configService.replicaCount=1 \
        --set adminService.replicaCount=1 \
	--dry-run
