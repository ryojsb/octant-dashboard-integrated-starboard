FROM ryocker213/kubectl-git:1.16

RUN mkdir -p  $HOME/.config/octant/plugins
RUN mkdir -p $HOME/.kube/

COPY config $HOME/.kube/
COPY starboard-octant-plugin $HOME/.config/octant/plugins 
COPY octant_0.13.1_Linux-64bit.deb $HOME
COPY xdg-utils_1.1.2-1ubuntu2_all.deb $HOME

RUN dpkg -i $HOME/xdg-utils_1.1.2-1ubuntu2_all.deb

RUN dpkg -i $HOME/octant_0.13.1_Linux-64bit.deb

ENV OCTANT_LISTENER_ADDR 0.0.0.0:8900

EXPOSE 8900

CMD ["/usr/local/bin/octant" "-vvv"]

