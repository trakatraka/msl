# msl

a podman wrapper that drops a fedora bash on the current working directory mounted as /mnt/pwd/$PWD. Usefull like WSL but for macOS.

## install podman

### via pkg

visit https://github.com/containers/podman/releases and download the latest pkg.

### via homebrew

```bash
brew install podman
```

## customize fedora instalation with .mslrc

### example using openjdk-11 on aarch64

create a custom ```.mslrc``` in the working directory or a global on ```~/.mslrc```

```bash
sudo dnf install -y java-11-openjdk
sudo alternatives --set java java-11-openjdk.aarch64
```

## basic usage

```msl npm run build```

or just drop into the bash

```msl```

### running podman inside podman

set ```MSL_RUN_OPTIONS="--privileged"``` before starting msl this will add --privileged flag to the underliying podman run command.

```MSL_RUN_OPTIONS="--privileged" msl```

## expose ports and custom build args

set ```MSL_BUILD_OPTIONS```=... environment variable to provide extra arguments to podman build.

set ```MSL_RUN_OPTIONS```=... environment variable to provide extra arguments to podman run cmd like -p 8080:8080


## cleanup

by default a new image is created for every .mslrc used.

to remove this images use the podman image rm <image_id>
