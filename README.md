# Slidev Container

**Forked from [slidev](https://github.com/slidevjs/slidev)**
## Repository Updates

- Update npm install to avoid 'permission denied' problem

### Build

You can build the image with:

```bash
$ git clone https://github.com/leijerry888/slidev_container.git
$ cd slidev_container
$ docker build -t slidev_container .
```

### Setup

Add a `slidev` function in `~/.zshrc` (if using `zsh`) for easy call:

```bash
slidev() {
    docker_id=$(docker run --rm -d -v "$(pwd):/root/slides" -p 3030:3030 slidev_container)
    echo "Docker container ID: $docker_id"
    echo "Container lof follows:"
    docker logs -f $docker_id
}
```

### Use

At the location of `slides.md`, simply run `slidev` and open `http://localhost:3030/` in your browser.

### LICENSE

This repository is licensed under the MIT license
