# parallel-prodigal

```bash
./parallel-prodigal.py -i metagenome.fna -a proteins.faa -q -t 16
```

Modified from [`pprodigal`](https://github.com/sjaenick/pprodigal). The changes include:
- Added support for compressed files (`.gz`, `.bz2`, and `.xz`).
- Automated chunk size determination.
- Fixed a bug where the contig IDs were not changed when concatenating the chuncks, causing repetition.
- Fixed a bug where `\n` was not added to the end of the lines when processing the outputs of the individual executions.
- Added a `--quiet` option that supresses output redirection to the standard output.
- Removed the "normal" mode. All Prodigal instances will use `-p meta` as self-training is unreliable when using chuncks of a larger assembly.
