FROM python:2.7

RUN pip install powerfulseal

ADD ./config config

RUN mkdir ~/.kube \
    && cp ./config/kubeconfig ~/.kube/config

EXPOSE 8080

ENTRYPOINT exec seal autonomous --policy-file config/sealconfig --no-cloud --inventory-kubernetes --remote-user jenkins --ssh-path-to-private-key config/privatekey --use-private-ip --ssh-allow-missing-host-keys