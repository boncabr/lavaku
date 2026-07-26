FROM ghcr.io/lavalink-devs/lavalink:4.2.2

USER root

# Install ffmpeg dan yt-dlp (standalone binary, tidak perlu Python)
RUN apt-get update -y && \
    apt-get install -y ffmpeg curl && \
    rm -rf /var/lib/apt/lists/* && \
    curl -L https://github.com/yt-dlp/yt-dlp/releases/latest/download/yt-dlp \
         -o /usr/local/bin/yt-dlp && \
    chmod a+rx /usr/local/bin/yt-dlp

COPY lavalink-railway/application.yml /opt/Lavalink/application.yml

EXPOSE 2333

ENTRYPOINT ["java", "-jar", "/opt/Lavalink/Lavalink.jar"]
