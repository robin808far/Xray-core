# VPN-AIO Xray core

This repository maintains the native AnyTLS, TUIC and NaiveProxy additions from
[Sir-MmD/Xray-core](https://github.com/Sir-MmD/Xray-core) for
[VPN-AIO](https://github.com/robin808far/VPN-AIO).

The `release/v2.0.0` integration merges upstream XTLS/Xray-core `v26.11.9`.
Fork transports use the current FinalMask and QUIC interfaces. The Shadowsocks
per-user cipher fallback to the inbound method is retained, along with the
Sing bridge required by AnyTLS.

Verification performed during integration:

```sh
go test ./infra/conf ./proxy/anytls/... ./proxy/tuic/... ./proxy/naive/... \
  ./transport/internet/tuic/... ./transport/internet/naive/...
CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build ./main
```

End-to-end validation with the VPN-AIO panel on Ubuntu 24.04 is still required.
Original license and copyright notices remain applicable.
