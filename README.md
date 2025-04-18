[![Rust](https://github.com/radoslawg/rust-snake/actions/workflows/rust.yml/badge.svg)](https://github.com/radoslawg/rust-snake/actions/workflows/rust.yml)

# Starting container

Assuming dockerhub is confiugred as default container source:

```sh
podman run --replace -dit --name 'rust-container' rust:latest '/bin/bash'
podman exec -it rust-container /bin/bash
```

Optionally, you could experiment with mounting volume at leat for `target` artifacts with something like `-v ./target:/workspace/rust-snake/target`.

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
podman exec -it rust-container /usr/bin/zsh
```
