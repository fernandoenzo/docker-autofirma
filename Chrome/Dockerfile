FROM ghcr.io/fernandoenzo/debian:12 AS builder

ENV DEBIAN_FRONTEND=noninteractive

COPY contents/ /tmp/contents

RUN bash /tmp/contents/scripts/builder



FROM ghcr.io/fernandoenzo/debian:12

COPY --from=builder / /tmp/builder

RUN bash /tmp/builder/tmp/contents/scripts/basics

USER user
CMD ["google-chrome --no-sandbox"]
