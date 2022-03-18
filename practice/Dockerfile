FROM nginx:latest

LABEL maintainer="Enver Akkoc"

ENV KULLANICI="ENVER"

ARG RENK

RUN apt-get update -y && apt-get install wget -y && apt-get install curl -y && apt-get install htop -y

WORKDIR /gecici

ADD https://wordpress.org/latest.tar.gz .

WORKDIR /usr/share/nginx

COPY html/${RENK}/ .

HEALTHCHECK --start-period=5s --interval=30s --timeout=30s --retries=3 CMD curl -f http://localhost/ || exit 1

CMD [ "./script.sh" ]



