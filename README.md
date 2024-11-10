# About

This is a database of No Man's Sky upgrade modules.

# How to view files

Many tools exist that can open parquet files. 

The easiest option I found is to install [VS Code](https://code.visualstudio.com/) and add the [Parquet Explorer](https://marketplace.visualstudio.com/items?itemName=AdamViola.parquet-explorer) extension.

# Why this exists

The original data was shared by [Zencq in the Pi repository](https://github.com/zencq/Pi) as csv files, but the total size of all the data is 10 GB.

I converted the CSV files to parquet which reduced the total size to 800MB, making them easier to download, share and work with.

# How

I created a java program that reads all files provided by Zencq, pushing them into [DuckDB](https://duckdb.org/) and then exporting them as parquet files compressed via the [zstd codec](https://parquet.apache.org/docs/file-format/data-pages/compression/#zstd) at [COMPRESSION_LEVEL 22](https://duckdb.org/docs/sql/statements/copy.html#parquet-options).