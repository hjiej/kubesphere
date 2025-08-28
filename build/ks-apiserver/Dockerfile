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

RUN make ks-apiserver
RUN mv /workspace/bin/cmd/ks-apiserver ${OUTDIR}/usr/local/bin/

##############
# Final image
#############

FROM alpine:3.22.1

COPY --from=build_context /out/ /

WORKDIR /

EXPOSE 9090
CMD ["sh"]
