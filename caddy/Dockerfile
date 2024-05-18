FROM caddy:2-builder AS builder

ARG GOCACHE=/root/.cache/go-build
RUN --mount=type=cache,target=/root/.cache/go-build xcaddy build \
    --with github.com/invzhi/caddy-docker-upstreams \
    --with github.com/abiosoft/caddy-json-schema \
    --with github.com/caddyserver/cache-handler \
    --with github.com/abiosoft/caddy-yaml

FROM caddy:2

COPY --from=builder /usr/bin/caddy /usr/bin/caddy
