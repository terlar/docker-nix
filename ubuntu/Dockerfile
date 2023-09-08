FROM ubuntu:latest
ARG NIX_INSTALLER_VERSION=0.8.0
ARG NIX_VERSION=2.17.0
RUN apt update -y \
    && apt install curl git -y \
    && curl --proto '=https' --tlsv1.2 -sSf -L https://github.com/DeterminateSystems/nix-installer/releases/download/v$NIX_INSTALLER_VERSION/nix-installer.sh | sh -s -- install linux \
       --nix-package-url https://releases.nixos.org/nix/nix-$NIX_VERSION/nix-$NIX_VERSION-x86_64-linux.tar.xz \
       --extra-conf "sandbox = false" \
       --init none \
       --diagnostic-endpoint= \
       --no-confirm
ENV PATH="${PATH}:/nix/var/nix/profiles/default/bin"
