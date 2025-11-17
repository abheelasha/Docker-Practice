#############################################
#STAGE1 - BASE IMAGE, TAKING UBUNTU IMAGE TO DOWNLOAD DEPENDENCIES AND GO PACKAGES
########################################
FROM ubuntu:latest as  build

WORKDIR /app

RUN apt-get update && apt-get install -y golang-go

COPY . .
# CGO_ENABLED=0 → disables CGO so the binary is statically compiled (required for scratch).
# Since CGO is disabled: ✔ No external dependencies, ✔ Binary can run inside a scratch image,
# ✔ No libc/glibc issues


RUN CGO_ENABLED=0 && go build calculator.go

################################################
# MULTISTAGE DOCKER FILE CREATION - STAGE2
#############################################

FROM scratch
WORKDIR /app
COPY --from=build /app/calculator .

ENTRYPOINT ["/app/calculator"]