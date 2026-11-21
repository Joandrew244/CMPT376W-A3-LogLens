# LogLens

LogLens is a command-line Python script that counts the records in a CSV log file by log level (`INFO`, `WARN`, or `ERROR`).

## Who this guide is for

This guide is for computing students and new technical interns who:

- understand basic CSV files
- have used a terminal before
- have **not** used LogLens before

You do not need to know this repository's structure or commands. For full setup steps, see the [installation and usage guide](docs/INSTALL.md).

## What LogLens does

- **Counts records.** It reads a CSV log file and prints how many records match one log level, or how many records there are in total.
- **Runs locally.** It does not upload, transmit, or store your data outside your computer.
- **Leaves your file unchanged.** It reads the CSV but does not repair, rewrite, or modify it.
- **Does not diagnose problems.** It counts records by level; it does not explain why a system failed.

## Requirements and things

You need Python. Most computers already have it, and version 3.6 or later should be good enough. It works on Windows, Mac, and Linux. Other than that, there is not much to know.

## Get started

First, get the project files from GitHub. Then install the program using `pip install log-lens` and run it by typing `loglens`. If you can't make it work, see docs/INSTALL.md. You probably won't need those instructions.

## Using the program

Run the following command after you have found the correct folder:

`loglens --input mylog.csv --severity error`

The software scans your log, fixes mistakes, and shows you what went wrong. You will see a number once it is finished. You can also run it on real production files without worrying about any side effects.

## Input format

The input should be a CSV file. Log files tend to have fields describing the time and what happened, but LogLens is flexible and will work with whatever columns your monitoring system uses. A small example is included somewhere in this repository.

## Questions

If something doesn't work, just contact the developers or create an issue. Make sure you describe the problem so somebody can help. This is a basic tool, so the instructions should be pretty obvious.
