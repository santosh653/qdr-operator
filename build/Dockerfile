FROM registry.access.redhat.com/ubi8-minimal

ENV OPERATOR=/usr/local/bin/qdr-operator \
    USER_UID=1001 \
    USER_NAME=qdr-operator \
    QDROUTERD_IMAGE=quay.io/interconnectedcloud/qdrouterd:1.12.0

# install operator binary
COPY build/_output/bin/qdr-operator ${OPERATOR}

COPY build/bin /usr/local/bin
RUN  /usr/local/bin/user_setup

ENTRYPOINT ["/usr/local/bin/entrypoint"]

USER ${USER_UID}
