# Build
ARG ALPINE_IMAGE=alpine:3.22.1

ARG GOLANG_IMAGE=golang:1.24.6

FROM ${GOLANG_IMAGE} AS build_context

ENV OUTDIR=/out
RUN mkdir -p ${OUTDIR}/usr/local/bin/

# 配置 Go 代理
ARG GOPROXY=https://goproxy.cn,direct
ENV GOPROXY=${GOPROXY}
ENV GOPRIVATE=git.gaccloud.com.cn

WORKDIR /workspace
ADD . /workspace/

RUN --mount=type=cache,target=/root/.cache/go-build \
    --mount=type=cache,target=/go/pkg/mod \
    make ks-apiserver

RUN mv /workspace/bin/cmd/ks-apiserver ${OUTDIR}/usr/local/bin/

##############
# Final image
#############

FROM ${ALPINE_IMAGE}

COPY --from=build_context /out/ /

WORKDIR /

EXPOSE 9090
CMD ["sh"]
