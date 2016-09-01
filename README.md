textlint-many-rules
====================

Docker container with textlint.

Docker URL https://hub.docker.com/r/shimizukawa/textlint-many-rules/

Based upon https://hub.docker.com/r/shimizukawa/textlint-rst/

### Rules

Base container `miy4/textlint` contains textlint rules as follows:

- [textlint-rule-preset-jtf-style](https://www.npmjs.com/package/textlint-rule-preset-jtf-style)
- [textlint-rule-max-ten](https://www.npmjs.com/package/textlint-rule-max-ten)
- [textlint-rule-no-doubled-joshi](https://www.npmjs.com/package/textlint-rule-no-doubled-joshi)
- [textlint-rule-no-mix-dearu-desumasu](https://www.npmjs.com/package/textlint-rule-no-mix-dearu-desumasu)
- [textlint-rule-sentence-length](https://www.npmjs.com/package/textlint-rule-sentence-length)
- [textlint-rule-spellcheck-tech-word](https://www.npmjs.com/package/textlint-rule-spellcheck-tech-word)

And this also contains:

- [textlint-rule-spellcheck-tech-word](https://www.npmjs.com/package/textlint-rule-spellcheck-tech-word)

* [textlint-rule-ja-no-weak-phrase](https://www.npmjs.com/package/textlint-rule-ja-no-weak-phrase)
* [textlint-rule-max-kanji-continuous-len](https://www.npmjs.com/package/textlint-rule-max-kanji-continuous-len)
* [textlint-rule-no-double-negative-ja](https://www.npmjs.com/package/textlint-rule-no-double-negative-ja)
* [textlint-rule-prh](https://www.npmjs.com/package/textlint-rule-prh)


See also: https://hub.docker.com/r/miy4/textlint/

### Plugins

This image contains textlint plugins as follows:

- [textlint-plugin-rst](https://www.npmjs.com/package/textlint-plugin-rst)

### Installation

To pull:

```sh
$ docker pull shimizukawa/textlint-many-rules
```

### Usage

```sh
$ vi .textlintrc
# Edit textlint configurations
```

See [textlint/docs/configuring.md](https://github.com/textlint/textlint/blob/master/docs/configuring.md) and [textlint/examples/config-file/](https://github.com/textlint/textlint/blob/master/examples/config-file) for more details.

For example:

```
{
  "plugins": [
    "rst"
  ],
  "rules": {
    "max-ten": {
      "max": 3
    },
    "spellcheck-tech-word": true,
    "no-mix-dearu-desumasu": true,
    "sentence-length": true,
    "prh": {
      "rulePaths": ["./WEB+DB_PRESS.yml"]
    },
    "preset-jtf-style": true,
    "no-double-negative-ja": true,
    "no-doubled-joshi": {
      "min_interval": 1,
      "strict": false,
      "allow": []
    },
    "ja-no-weak-phrase": true,
    "max-kanji-continuous-len": true
  }
}
```

Run as
```sh
$ docker run --rm -v ${PWD}:/data -w /data shimizukawa/textlint-many-rules <TEXTLINT_ARGS>
```

`docker run` accept and pass a set of parameters to [textlint CLI](https://github.com/textlint/textlint#cli).

