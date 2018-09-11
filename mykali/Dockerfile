# Based off the official Kali Docker image
FROM kalilinux/kali-linux-latest:latest

# Update the db and upgrade the packages
RUN apt update && apt upgrade -y

# Install the kali top10 to start with
RUN apt install -y kali-linux-top10 \
                   man-db \
                   exploitdb

# Here come all the tools that I need that are not in the top10

RUN apt install -y  radare2 \
                    python-pip \

# Set up metasploit db if not yet created
