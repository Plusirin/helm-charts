# RELEASE:elasticsearch-7.14.0

RELEASE_NAME := elasticsearch
NAMESPACE := middleware
STORAGECLASS := rook-cephfs

install:
	helm install $(RELEASE_NAME) -n $(NAMESPACE) . \
	--set volumeClaimTemplate.storageClassName=$(STORAGECLASS) && \
	helm install -n $(NAMESPACE) logstash elastic/logstash && \
	helm install -n $(NAMESPACE) kibana elastic/kibana

uninstall:
	helm uninstall kibana -n $(NAMESPACE) && \
	helm uninstall logstash -n $(NAMESPACE) && \
	helm uninstall $(RELEASE_NAME) -n $(NAMESPACE)
