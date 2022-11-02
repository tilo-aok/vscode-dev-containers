FROM mcr.microsoft.com/vscode/devcontainers/repos/microsoft/vscode:latest

ENV DONT_PROMPT_WSL_INSTALL=true
COPY fluxbox/* /tmp/fluxbox/
COPY *.sh /tmp/scripts/
RUN bash /tmp/scripts/install.sh \
    && apt-get clean -y && rm -rf /var/lib/apt/lists/* /tmp/scripts/ /tmp/fluxbox/ \
    && git config --global codespaces-theme.hide-status 1

ARG USERNAME=rstudio
RUN mkdir -p /home/$USERNAME/.vscode-server/extensions \
        /home/$USERNAME/.vscode-server-insiders/extensions \
    && chown -R $USERNAME \
        /home/$USERNAME/.vscode-server \
        /home/$USERNAME/.vscode-server-insiders
