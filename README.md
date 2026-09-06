# eventbus

[![CI](https://github.com/headlesslab/eventbus/actions/workflows/ci.yml/badge.svg)](https://github.com/headlesslab/eventbus/actions/workflows/ci.yml)
[![Go Reference](https://pkg.go.dev/badge/github.com/headlesslab/eventbus.svg)](https://pkg.go.dev/github.com/headlesslab/eventbus)

A lightweight observable. A Go channel cannot have an unbounded buffer, and choosing a size is a pain; this library grows the buffer as needed.

- unbounded buffer
- one publisher, many subscribers
- thread-safe
- subscribers never block each other
- stable event order

## Provenance

`eventbus` is a Satellite module of [wand](https://github.com/headlesslab/wand). It is a snapshot of [goob](https://github.com/ysmood/goob) `v0.4.0` (commit `8c75c65`), imported without git history and maintained here by headlesslab; see [NOTICE](NOTICE). The module path changed, the exported identifiers did not.

Replace `github.com/ysmood/goob` with `github.com/headlesslab/eventbus` and `goob.` with `eventbus.`; `New`, `NewPipe`, `Observable`, `Event`, ... keep their names.

The test suite uses [leakcheck](https://github.com/headlesslab/leakcheck) and therefore runs with `GODEBUG=tracebackancestors=1000`.

## Usage

```go
import "github.com/headlesslab/eventbus"
```

The tests are the documentation: see [examples_test.go](examples_test.go).

## Versioning

`v0.x`: no breaking change without a major version bump. Releases are cut by hand when the module changes; wand pins each release exactly.

## License

MIT, see [LICENSE](LICENSE).
