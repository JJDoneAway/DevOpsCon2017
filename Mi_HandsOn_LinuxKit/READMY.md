# Hands On LinuxKit Next Step Immutable Infrastructure
-Erkan Yanar

## OS Evolution
- LinuxKit
- mach es so klein wie möglich
- aktueller kernl ist wichtig für die isolation
- systemd ist genug aber der kernl muss immer aktuell bleiben
  - CoreOS (systemd mit zwei OS A/B)
  - atomic

## LinuxKit
- ist von docker
- ist kein systemd aber containerd
- man baut es wie ein container images
- daher ein immutable OS ganz unten

## Bauen
- moby: moby build my-kit.yml

## start
- LinuxKit my-kit
