FROM ubuntu:18.04 AS build
ARG version

RUN apt-get update && apt-get install unzip
ADD https://github.com/jsontypedef/json-typedef-fuzz/releases/download/$version/x86_64-unknown-linux-musl.zip /x86_64-unknown-linux-musl.zip
RUN unzip x86_64-unknown-linux-musl.zip

FROM scratch
COPY --from=build /jtd-fuzz /jtd-fuzz
ENTRYPOINT ["/jtd-fuzz"]
