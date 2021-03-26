FROM  ibmcom/websphere-traditional:latest-ubi

COPY --chown=was:root startENG.sh /work/
RUN chmod +x /work/startENG.sh

CMD ["/bin/bash", "/work/startENG.sh", "Hello World"]
