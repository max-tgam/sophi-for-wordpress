FROM debian:stable-slim

LABEL "com.github.actions.name"="Release to Stable"
LABEL "com.github.actions.description"="Push a production-ready build to the stable branch"
LABEL "com.github.actions.icon"="send"
LABEL "com.github.actions.color"="blue"

LABEL maintainer="10up <opensource@10up.com>"
LABEL version="1.0.0"
LABEL repository="http://github.com/globeandmail/sophi-for-wordpress/.github/action-release"

ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get update \
	&& apt-get install -y rsync git \
	&& apt-get clean -y \
	&& rm -rf /var/lib/apt/lists/* \
	&& git config --global user.email "10upbot+github@10up.com" \
	&& git config --global user.name "10upbot on GitHub"

COPY entrypoint.sh /entrypoint.sh
RUN chmod +x /entrypoint.sh
ENTRYPOINT ["/entrypoint.sh"]
