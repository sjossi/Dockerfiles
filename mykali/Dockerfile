# Based off the official Kali Docker image
FROM kalilinux/kali-linux-docker:latest

# Update the db and upgrade the packages
RUN apt-get update && apt-get upgrade -y

# Here come all the tools that I need that are not in the top10

RUN apt-get install -y  radare2 \
                        python-pip \
                        man-db \
                        exploitdb 


# Set up metasploit db if not yet created
