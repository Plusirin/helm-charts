# RELEASE:apollo-portal-1.9.0
#
RELEASE_NAME := apollo-portal
NAMESPACE := middleware
STORAGECLASS := rook-cephfs


install:
	helm install $(RELEASE_NAME) . \
	--namespace $(NAMESPACE) \
	--set portaldb.host=192.168.100.51 \
	--set portaldb.port=30336 \
	--set portaldb.userName=apollo \
	--set portaldb.password=apollo \
	--set portaldb.service.enabled=true \
	--set service.type=NodePort \
	--set config.envs="pro\,test" \
	--set config.metaServers.pro=http://apollo-service-pro-apollo-configservice:8080 \
	--set config.metaServers.test=http://apollo-service-test-apollo-configservice:8080 \
	--set replicaCount=1	

uninstall:
	helm uninstall $(RELEASE_NAME) -n $(NAMESPACE)
