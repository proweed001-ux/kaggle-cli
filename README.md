# Kaggle CLI

The official CLI to interact with [Kaggle](https://www.kaggle.com).

---

[User documentation](docs/README.md)

---

## Key Features

Some of the key features are:

* List competitions, download competition data, submit to a competition.
* List, create, update, download or delete datasets.
* List, create, update, download or delete models & model variations.
* List, update & run, download code & output or delete kernels (notebooks).

## Installation

Install the `kaggle` package with [pip](https://pypi.org/project/pip/):

```sh
pip install kaggle
```

Additional installation instructions can be found [here](docs/README.md#installation).

## Quick start

If you are starting from zero, follow these steps:

1. Create a Kaggle account at [kaggle.com](https://www.kaggle.com/account/login).
2. Install the CLI:

```sh
pip install kaggle
```

3. Open [Kaggle Settings](https://www.kaggle.com/settings), then click **Generate New Token** in the **API** section.
4. In your terminal, set the token from that page:

```sh
export KAGGLE_API_TOKEN=<your-kaggle-api-token>
```

5. Verify everything works:

```sh
kaggle --help
kaggle competitions list
```

If you get an authentication error, check the full [authentication guide](docs/README.md#authentication). For more examples, see the [User documentation](docs/README.md).

## Development

### Prerequisites

We use [hatch](https://hatch.pypa.io) to manage this project.

Follow these [instructions](https://hatch.pypa.io/latest/install/) to install it.

### Run `kaggle` from source

#### Option 1: Execute a one-liner of code from the command line

```sh
hatch run kaggle datasets list
```

#### Option 2: Run many commands in a shell

```sh
hatch shell

# Inside the shell, you can run many commands
kaggle datasets list
kaggle competitions list
...
```

### Lint / Format

```sh
# Lint check
hatch run lint:style
hatch run lint:typing
hatch run lint:all     # for both

# Format
hatch run lint:fmt
```

### Tests

Note: These tests are not true unit tests and are calling the Kaggle web server.

```sh
# Run against kaggle.com
hatch run test:prod

# Run against a local web server (Kaggle engineers only)
hatch run test:local
```

### Integration Tests

To run integration tests on your local machine, you need to set up your Kaggle credentials. You can do this by following the [authentication instructions](docs/README.md#authentication).

After setting up your credentials, you can run the integration tests as follows:

```sh
hatch run test:integration
```

## Changelog

See [CHANGELOG](CHANGELOG.md).

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md).

## License

The Kaggle CLI is released under the [Apache 2.0 license](LICENSE.txt).
