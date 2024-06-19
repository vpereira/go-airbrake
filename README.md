# go-airbrake

This is a Go module that integrates with the Airbrake protocol to send error notifications. It has been tested and works with Errbit. The code is licensed under the MIT license.

## Installation

To install this package, run:

```sh
go get github.com/vpereira/go-airbrake
```

## Usage

Make sure to set the following environment variables:

- `AIRBRAKE_PROJECT_ID`: Your Airbrake project ID
- `AIRBRAKE_PROJECT_KEY`: Your Airbrake project key
- `AIRBRAKE_ENVIRONMENT`: The environment name (e.g., production, development)
- `AIRBRAKE_ERRBIT_URL`: The custom Errbit URL if you are using Errbit

```go
package main

import (
    "errors"
    "github.com/yourusername/go-airbrake"
)

func main() {
    notifier := airbrake.NewAirbrakeNotifier()

    if notifier.Enabled {
        err := errors.New("example error")
        notifier.NotifyAirbrake(err)
    }
}
```

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
