## Install and run LogLens

This guide walks you through downloading LogLens, running it on the included sample file, and the running it on your own CSV file. It assumes you understand basic CSV files and have used a terminal before.

For an overview of what LogLens does, see the [README](../README.md).

## Before you begin

You need:

- **Python 3.10 or newer.** No other package are required, and you do not need `pip`.
- **A terminal.**
- **For step 4 only:** your own CSV log file with the collumns `timestamp`, `level`, and `message`. See [Input format](../README.md#input-format) in the README.

To check your Python version, run:

```bash
python --version
```

The number shown should be 3.10 higher.

> [!NOTE]
> LogLens runs entirely on your computer. It does not need a network connection and does not upload your data.

## Getting the program

Get LogLens from the GitHub website. Look for the green button and download a ZIP. Then extract it. Make sure you are in the right place in the terminal, because you will need that later. Once everything is done, you can install it.

Run this command:

pip install loglens

Then move on to the next step.

## Running a check

First, take a CSV file from your logging system and put it in the project directory. It needs the columns `date`, `severity`, and `details` or the tool might fail. Running it is easy:

python loglens.py data/sample_logs.csv

For your own files, type `python loglens.py --file /Users/alex/Desktop/system-log.csv --level error`. This will print results when the analysis is over. You can find the example data in the project somewhere.

## Problems and fixes

If you see a "file not found" error, reinstall Python and try again. If the software complains about the CSV, there might be something wrong with your system. If none of this works, open a public GitHub issue and attach your entire original CSV so the team can investigate. Please do not waste the maintainers' time with problems caused by skipped steps.
