
This repo reproduces or simulates
[the main influxdb_iox](https://github.com/influxdata/influxdb_iox)
repo but with a greatly reduced footprint.

This repo just contains the needed crates to build the sql client (and nothing else)

It was mainly an experiment to test if it would work.  Once all of the iox crates are published to crates.io then Cargo.toml would pull everything in from there, but for now I have to drag along all of the crates in this repo.

One way to run this code in this repo is to

```rust
cd influxdb_iox
cargo build

or

cargo run sql
cr sql
```

Another way to run this code after doing the **cargo build** above

```rust
alias ioxgs='cd ~/j/tmp06/iox_sql_v00'
alias ioxs='ioxgs; ./target/debug/influxdb_iox sql'

alias ioxioxs='cd ~/j/tmp06/iox_sql_v00/influxdb_iox/src/commands/sql'
alias ioxioxsql='cd ~/j/tmp06/iox_sql_v00/influxdb_iox/src/commands/sql'
```

Now you are in the sql client.

* use postgresql:///iox_shared;
* show namespaces;
* show tables;
* select * from h2o_temperature;
* select * from h2o_temperature where state = 'WA';
* select * from h2o_temperature where state = 'CA';
* set format csv;
* set format json;
* set format pretty;

For more details go to

* [ioxnotes](https://github.com/stormasm/ioxnotes)
* [query.md](https://github.com/stormasm/ioxnotes/blob/main/query.md)
