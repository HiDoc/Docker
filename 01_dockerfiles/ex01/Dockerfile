# docker run --name teamspeak3 -p 9987:9987/udp -p 30033:30033 -p 10011:10011 -p 41144:41144 --rm -it ts3
FROM debian:latest

# Update and upgrade image
RUN apt-get update
RUN apt-get upgrade -y
RUN apt-get install -y wget

# Expose port
EXPOSE 9987/udp
EXPOSE 30033
EXPOSE 10011
EXPOSE 41114

# Add user teamspeak
RUN useradd teamspeak;
RUN	su teamspeak

# Get teamspeak, rename directory and remove source
RUN cd ~
RUN wget http://dl.4players.de/ts/releases/3.0.11.2/teamspeak3-server_linux-amd64-3.0.11.2.tar.gz
RUN	tar -zxvf teamspeak3-server_linux-amd64-3.0.11.2.tar.gz
RUN	mv teamspeak3-server_linux-amd64 ts-server
RUN	rm teamspeak3-server_linux-amd64-3.0.11.2.tar.gz

USER teamspeak

ENTRYPOINT ["/bin/sh.distrib"]
CMD ["./ts-server/ts3server_minimal_runscript.sh", "createinifile=1", "&"]
