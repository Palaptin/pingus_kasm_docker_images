#c
FROM ghcr.io/lscr.io/linuxserver/webtop:arch-xfce
RUN pacman -Syu git vi jdk-openjdk unzip webkit2gtk go intellij-idea-community-edition --noconfirm
RUN cd tmp && sudo -u kasm-user git clone https://aur.archlinux.org/yay-git.git && cd yay-git && sudo -u kasm-user makepkg -si --noconfirm
RUN sudo -u kasm-user yay -S eclipse-jee duckdb-bin --noconfirm
RUN echo -e '[Desktop Entry]\nname=InteliJ\nExec=idea' >> /etc/xdg/autostart/intelij.desktop
