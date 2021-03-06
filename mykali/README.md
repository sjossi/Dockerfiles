# My Kali
This is supposed to be a quick one-liner Kali machine with no persistence besides the files worked on. This is based on
the [Medium post by Airman](https://medium.com/@airman604/kali-linux-in-a-docker-container-5a06311624eb)

## Building the Docker image
To build the image, tag it with the name you use it in the sh alias, in my case `sjossi/mykali:latest`

```
docker build . -t sjossi/mykali:latest
```

## sh aliases
I have two aliases available. The second one mounts your current directory into the container. This is convenient if
you cd into your project and run `dockerkali`, but can be dangerous if you mount it on $HOME and then `rm -rf /`
(because who never wanted to try that in a Docker machine)

```
alias dockerkali="sudo docker run -ti --rm --mount type=bind,src=$HOME/kali-root,dst=/root --mount type=bind,src=$HOME/.kali-postgres,dst=/var/lib/postgresql --mount type=bind,src=\$PWD,dst=/mnt/pwd sjossi/mykali:latest"
alias dockerkali="sudo docker run -ti --rm --mount type=bind,src=$HOME/kali-root,dst=/root --mount type=bind,src=$HOME/.kali-postgres,dst=/var/lib/postgresql sjossi/mykali:latest"
```
