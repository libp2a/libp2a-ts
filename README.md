# libp2a

This package is a Typescript/Javascript client for the [P2A service](https://p2a.telescope.chat/api/v1/docs).

* [Function call](#function-call)
* [Function chat](#function-chat)
* [Command Line Interface (CLI)](#command-line-interface-cli)


#### Function call

Runs one of the available functions based on the prompt and returns the exact
output of the function in the value field.

```ts
import { call } from "libp2a";

const { value } = await call("get the address of Outback downtown Houston");

console.log(value); // # => { "full": "10001 Westheimer Rd #1010, Houston, TX 77042, USA", "postal_code": "77042", "street_name": "Westheimer Road", "complement": "1010", "neighborhood": "Westside", "city_name": "Houston", "state_name": "Texas", "state_code": "TX", "country_name": "United States", "country_code": "US" }
```

#### Function chat

Runs one of the available functions based on the prompt and returns a modified
version of the function's output according to the prompt instructions.

```ts
import { chat } from "libp2a";

const { value } = await chat("get the address of zipcode 77042 and return only the city name")

console.log(value); // # => "Houston"
```

#### Command Line Interface (CLI)

The package includes a CLI that provides easy access to both `call` and `chat` functions from the command line.

##### Installation

You can install the package globally to use the CLI from anywhere:

```bash
npm install -g @libp2a/libp2a
```

Or install it locally in your project:

```bash
npm install @libp2a/libp2a
```

##### Usage

The CLI provides two main commands:

1. **call** - Execute a function and get structured data:
```bash
p2a call "get the address of Outback downtown Houston"
```

2. **chat** - Get processed results based on your prompt:
```bash
p2a chat "get the address of zipcode 77042 and return only the city name"
```

##### Additional Commands

- Get help information:
```bash
p2a --help          # General help
p2a call --help     # Help for call command
p2a chat --help     # Help for chat command
```

- Check version:
```bash
p2a --version
```
