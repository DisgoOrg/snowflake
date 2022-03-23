[![Go Reference](https://pkg.go.dev/badge/github.com/disgoorg/snowflake.svg)](https://pkg.go.dev/github.com/disgoorg/disgo)
[![Go Version](https://img.shields.io/github/go-mod/go-version/disgoorg/snowflake)](https://golang.org/doc/devel/release.html)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://github.com/disgoorg/disgo/blob/master/LICENSE)
[![Disgo Version](https://img.shields.io/github/v/tag/disgoorg/snowflake?label=release)](https://github.com/disgoorg/snowflake/releases/latest)
[![Disgo Discord](https://discord.com/api/guilds/817327181659111454/widget.png)](https://discord.gg/TewhTfDpvW)

# snowflake

snowflake is a golang library for parsing [snowflake IDs](https://docs.snowflake.com) from discord.
This package provides a custom `snowflake` type which has various utility methods for parsing snowflake IDs.

### Installing

```sh
go get github.com/disgoorg/snowflake
```

## Usage

```go

id := Snowflake("123456789012345678")

// deconstructs the snowflake ID into its components timestamp, worker ID, process ID, and increment
id.Deconstruct()

// time.Time when the snowflake was generated
id.Time()

// returns the string representation of the snowflake ID
id.String()

// returns the int64 representation of the snowflake ID
id.Int64()

// returns a new snowflake with worker ID, process ID, and increment set to 0
// this can be used for various pagination requests to the discord api
id = NewSnowflake(time.Now())

// returns the fmt.Stringer as a Snowflake
id = ParseString(...)

// returns the int64 as a Snowflake
id = ParseInt64(123456789012345678)

// returns the uint64 as a Snowflake
id = ParseUInt64(123456789012345678)

// returns a snowflake from an environment variable
id = GetSnowflakeEnv("guild_id")
```

## License

Distributed under the [![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://github.com/disgoorg/snowflake/blob/master/LICENSE). See LICENSE for more information.
