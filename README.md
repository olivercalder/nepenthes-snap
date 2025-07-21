# nepenthes-snap

Nepenthes is a tarpit intended to catch web crawlers. It is developed by
Aaron B. For more information about Nepenthes, please see:

https://zadzmo.org/code/nepenthes/

This snap package is maintained by Oliver Calder, and is not affiliated
with nor endorsed by the upstream Nepenthes project or its author.

## Installation

To install the `nepenthes` snap (assuming you already have `snapd` installed),
simply run:

```sh
snap install nepenthes
```

This will install and enable the `nepenthes` daemon.

## Configuration

By default, `nepenthes` listens on port 8893. To change this or other
configuration settings, edit the config file:

`/var/snap/nepenthes/current/config.yaml`

Please see the upstream documentation for full configuration options:

https://zadzmo.org/code/nepenthes/

## Training

Nepenthes uses a markov corpus to populate generated pages with words. It
is recommended that you provide training data to train the markov babbler.
This can be done by sending arbitrary data to nepenthes, for example:

```sh
cat /path/to/file.txt | nepenthes.train-markov-corpus
```

If training is interrupted, you can skip lines you have already trained.
For example, to skip the first 150 lines of the training file:

```sh
cat /path/to/file.txt | nepenthes.train-markov-corpus 150
```

If you wish to delete the markov corpus and start again, run:

```sh
nepenthes.delete-markov-corpus
```

## License

This snap package is licensed under the MIT license, the same license as the
Nepenthes project.
