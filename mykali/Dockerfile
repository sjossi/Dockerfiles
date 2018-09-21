# Based off the official Kali Docker image
FROM kalilinux/kali-linux-docker:latest

# Update the db and upgrade the packages
RUN apt-get update && apt-get dist-upgrade -y 

# Here come all the tools that I need that are not in the top10

RUN apt-get install -y  radare2 \
                        python-pip \
                        man-db \
                        exploitdb \
                        vim \
                        metasploit-framework

# Install Python modules
RUN pip install pwntools

# Set up metasploit db if not yet created
# TODO


# Cleanup
RUN apt-get autoremove && apt-get clean
