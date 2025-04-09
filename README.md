# Starting container

Assuming dockerhub is confiugred as default container source:

```sh
podman run --replace -dit --name 'rust-container' rust:latest '/bin/bash'
podman exec -it /bin/bash
```

This should put you into bash inside *rust-container* container. You should then clone this repo and run `.config/setup_env.sh` script that will set up environment:

```sh
mkdir workspace
cd workspace
git clone https://github.com/radoslawg/rust-snake.git
cd rust-snake
bash -c '.config/setup_env.sh'
```

Now exit container with *Ctrl-D* and you can enter container again with

```sh
podman exec rust-container -it /usr/bin/zsh
```
