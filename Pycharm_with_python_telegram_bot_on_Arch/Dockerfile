FROM ghcr.io/lscr.io/linuxserver/webtop:arch-xfce
RUN pacman -Syu git vi glibc unzip webkit2gtk go geany pycharm-community-edition python-black python-pip python-yaml python-mysqlclient python-apscheduler python-pytz python-aiohttp --noconfirm
RUN echo LANG=de_DE.UTF-8 >> /etc/locale.conf && echo 'de_DE.UTF-8 UTF-8' >> /etc/locale.gen && locale-gen
RUN cd tmp && sudo -u kasm-user git clone https://aur.archlinux.org/yay-git.git && cd yay-git && sudo -u kasm-user makepkg -si --noconfirm
RUN echo -e '[Desktop Entry]\nVersion=1.0\nType=Application\nName=PyCharm Community Edition\nComment=Python IDE for Professional Developers\nExec=/usr/bin/pycharm %f\nIcon=pycharm\nTerminal=false\nStartupNotify=true\nStartupWMClass=jetbrains-pycharm-ce\nCategories=Development;IDE;Java;' >> /etc/xdg/autostart/intelij.desktop
RUN sudo -u kasm-user pycharm installPlugins me.lensvol.blackconnect
RUN sudo -u kasm-user mkdir -p '/home/kasm-user/.config/JetBrains/PyCharmCE2023.1/options' && echo -e '<application>\n<component name="BlackConnectGlobalSettings" bindOnHostname="127.0.0.1" blackdBinaryPath="/usr/sbin/blackd"/>\n</application>' >> sudo -u kasm-user /home/kasm-user/.config/JetBrains/PyCharmCE2023.1/options/other.xml
RUN sudo -u kasm-user pip install -U sqlalchemy[asyncio] asyncmy --break-system-packages
RUN sudo -u kasm-user yay -S python-telegram-bot python-aiolimiter sqlacodegen --noconfirm
