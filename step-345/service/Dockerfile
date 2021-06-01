FROM ubuntu:20.04

COPY qemu_sstic_amd64.deb /root/

RUN apt-get -y update && \
    DEBIAN_FRONTEND=noninteractive apt-get -yq --no-install-recommends install \
        socat \
        libglib2.0-bin \
        libpixman-1-0 \
        libfdt1 \
        python3 && \
    dpkg -i /root/qemu_sstic_amd64.deb && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* /root/qemu_sstic_amd64.deb

RUN adduser --disabled-password --gecos '' docker

WORKDIR /home/docker

#keep that at the end so we use cached image of compiled qemu when we modify it
COPY asm.py bzImage rootfs.img run_service.sh wrapper.py /home/docker/

RUN chown -R root:root /home/docker && \
    chmod -R ug-w  /home/docker && \
    chmod +x /home/docker/run_service.sh

EXPOSE 1337

USER docker

CMD /home/docker/run_service.sh


