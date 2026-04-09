# async-pool

[![Build Status](https://img.shields.io/github/actions/workflow/status/user/async-pool/ci.yml?branch=main)]()
[![Go Version](https://img.shields.io/badge/go-1.22+-blue.svg)]()
[![License: MIT](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)

**async-pool** bounded async worker pool with graceful shutdown and error collection. Built with simplicity and performance in mind.

## Features

- Context Support: Full context.Context propagation for cancellation and deadlines
- High Performance: Optimized for low-latency, high-throughput workloads
- Structured Logging: Built-in structured logging with slog compatibility

## Installation

```bash
go get github.com/user/async-pool@latest
```

## Quick Start

```go
package main

import (
	"fmt"
	"github.com/user/async-pool"
)

func main() {
	client := asyncpool.New(
		asyncpool.WithTimeout(30 * time.Second),
	)

	result, err := client.Run(context.Background())
	if err != nil {
		log.Fatal(err)
	}

	fmt.Println(result)
}
```

## License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.
