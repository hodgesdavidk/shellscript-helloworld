FROM ibmjava:8-jre

USER 1001
COPY --chown=1001:root startENG.sh /work/
RUN chmod +x /work/startENG.sh

CMD ["/bin/bash", "/work/startENG.sh", "Hello World"]
