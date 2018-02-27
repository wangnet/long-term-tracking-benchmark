# OxUvA long-term tracking benchmark
## How to get started


## How to run scripts

It is necessary to add the parent of the `oxuva` directory to the `PYTHONPATH` environment variable:
```bash
export PYTHONPATH=path/to/long-term-tracking-benchmark:$PYTHONPATH
```
You can then run the scripts from anywhere, although we recommend to use `workspace` as the working directory.
For example, to run the analysis script:
```bash
cd path/to/long-term-tracking-benchmark/workspace
python -m oxuva.analyze --help
```

## To generate the table of results

Download and extract the predictions to `workspace/predictions/dev/`:
```bash
cd path/to/workspace
tar -xzf path/to/predictions-dev.tgz
```
Then run the `oxuva.analyze` script:
```bash
python -m oxuva.analyze ./annotations/dev.csv ./predictions/dev/ --verbose
```
The results table will be printed to `stdout` in CSV format.

Use `--help` to discover the optional flags.
For example, use `--iou_threshold=0.7` to generate the results with a stricter threshold (the default is 0.5).
