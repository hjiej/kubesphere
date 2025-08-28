# Download dependencies
FROM alpine:3.22.1 AS base_os_context

RUN apk add --no-cache ca-certificates curl

ENV OUTDIR=/out
RUN mkdir -p ${OUTDIR}/usr/local/bin/

ARG TELEMETRY_URL=https://github.com/kubesphere/telemetry/releases/download
ARG TELEMETRY_VERSION=1.0.2
ARG TARGETARCH
RUN curl -LO ${TELEMETRY_URL}/v${TELEMETRY_VERSION}/telemetry_${TELEMETRY_VERSION}_linux_${TARGETARCH}.tar.gz && \
    tar -zxvf telemetry_${TELEMETRY_VERSION}_linux_${TARGETARCH}.tar.gz -C ${OUTDIR}/usr/local/bin/ telemetry

# Add KS Core Helm Chart
COPY config/ks-core ${OUTDIR}/var/helm-charts/ks-core

# Build
FROM golang:1.24.6 AS build_context

ENV OUTDIR=/out
RUN mkdir -p ${OUTDIR}/usr/local/bin/

# 配置 Go 代理
ARG GOPROXY=https://goproxy.cn,direct
ENV GOPROXY=${GOPROXY}
ENV GOPRIVATE=git.gaccloud.com.cn

WORKDIR /workspace
ADD . /workspace/

RUN make ks-controller-manager
RUN mv /workspace/bin/cmd/controller-manager ${OUTDIR}/usr/local/bin/

# Final Image
FROM alpine:3.22.1

COPY --from=base_os_context /out/ /
COPY --from=build_context /out/ /

WORKDIR /

EXPOSE 8443
CMD ["sh"]
