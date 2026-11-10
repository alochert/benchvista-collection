# BenchVista collection

Official [BenchVista](https://benchvista.com) Spark Plugs, Spark drivers and Python analysis steps.

**Browse it:** https://alochert.github.io/benchvista-collection/

| Folder            | Holds                                                     |
| ----------------- | --------------------------------------------------------- |
| `spark-plugs/`    | Python programs for a Spark board, one folder per item    |
| `spark-drivers/`  | Drivers that let a Spark Plug use a display or a sensor   |
| `analysis-steps/` | Python steps for BenchVista analysis chains               |
| `collection.json` | The collection's name, summary, maintainer and repository |

Each item is a folder with its Python source and one `benchvista.json`. A version is a number plus a
SHA-256 over every file in the folder. When a version number goes up, the
[Collection workflow](.github/workflows/collection.yml) checks and tests every item, publishes the
new version as a GitHub Release named `<id>@<version>` with its release record and checksums,
attests the index, and rebuilds the site. Older versions stay listed and downloadable. Publishing
the same number with different files is refused.

Checksums and attestations prove which files you have and where they came from. They do not prove
that the code is correct or safe to run.

## Your own collection

Press **Use this template**, change `collection.json`, replace the items with your own and enable
GitHub Pages with the source **GitHub Actions**. Work on an item with the
[`benchvista` command](https://github.com/alochert/benchvista-python):

```sh
uv tool install --python 3.13 git+https://github.com/alochert/benchvista-python
benchvista new spark-plug spark-plugs/blink-led
benchvista check spark-plugs/blink-led
benchvista test spark-plugs/blink-led
```

## Licence

Every item here is CC0-1.0: copy and change it freely.
