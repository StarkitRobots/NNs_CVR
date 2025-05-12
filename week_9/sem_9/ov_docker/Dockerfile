FROM openvino/ubuntu20_dev:2022.1.0

ENV TZ=Europe/Moscow

USER root
RUN apt update
RUN apt-get update
RUN source /opt/intel/openvino_2022.1.0.643/setupvars.sh
RUN /bin/bash /opt/intel/openvino_2022.1.0.643/install_dependencies/install_openvino_dependencies.sh -y
RUN /bin/bash /opt/intel/openvino_2022.1.0.643/install_dependencies/install_NCS_udev_rules.sh -y

RUN pip3 install torch torchvision --index-url https://download.pytorch.org/whl/cpu
RUN pip3 install opencv-contrib-python pillow albumentations

RUN apt install -qqy jupyter
RUN pip3 install --force-reinstall "jinja2<3.0.0"
RUN pip3 install --force-reinstall "markupsafe<2.1.0"

RUN apt-get install -qqy usbutils
RUN mkdir -p root/workspace

# ENV HOME /home/root
RUN echo "jupyter notebook --ip 0.0.0.0 --no-browser --allow-root" >> /root/.bashrc
WORKDIR /root/workspace
