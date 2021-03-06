## v0.0.1 [2013-10-22]

  * Initial Release

## v0.0.2

#### Features

- Add an admin UI
- Deb and RPM packages

#### Bugfixes

- Fix some nil pointer dereferences
- Cleanup the aggregators implementation

## v0.0.5

#### Features

- Cache passwords in memory to speed up password verification
- Add MERGE and INNER JOIN support

#### Bugfixes

- All columns should be returned if `select *` was used
- Read/Write benchmarks

## v0.0.6

#### Features

- Add count(distinct(..)) support

#### Bugfixes

- Reuse levigo read/write options.

## v0.0.7

#### Features

- include the admin site in the repo to make it easier for newcomers.

## v0.0.8

#### Features

- Add a way to reset the root password from the command line.
- Add distinct(..) and derivative(...) support
- Print test coverage if running go1.2

#### Bugfixes

- Fix the default admin site path in the .deb and .rpm packages.
- Fix the configuration filename in the .tar.gz package.

## v0.0.9

#### Features

- Add stddev(...) support
- Better docs, thanks @auxesis and @d-snp.

#### Bugfixes

- Set PYTHONPATH and CC appropriately on mac os x.
- [Issue #18](https://github.com/influxdb/influxdb/issues/18). Fix 386 debian and redhat packages
- [Issue #23](https://github.com/influxdb/influxdb/issues/23). Fix the init scripts on redhat

## v0.1.0

### Features

- [Issue #29](https://github.com/influxdb/influxdb/issues/29). Semicolon is now optional in queries
- [Issue #31](https://github.com/influxdb/influxdb/issues/31). Support Basic Auth as well as query params for authentication.

### Bugfixes

- Don't allow creating users with empty username
- [Issue #22](https://github.com/influxdb/influxdb/issues/22). Don't set goroot if it was set
- [Issue #25](https://github.com/influxdb/influxdb/issues/25). Fix queries that use the median aggregator
- [Issue #26](https://github.com/influxdb/influxdb/issues/26). Default log and db directories should be in /opt/influxdb/shared/data
- [Issue #27](https://github.com/influxdb/influxdb/issues/27). Group by should not blow up if the one of the columns in group by has null values
- [Issue #30](https://github.com/influxdb/influxdb/issues/30). Column indexes/names getting off somehow
- [Issue #32](https://github.com/influxdb/influxdb/issues/32). Fix many typos in the codebase. Thanks @pborreli

## v0.2.0

### Features

- [Issue #37](https://github.com/influxdb/influxdb/issues/37). Support the negation of the regex matcher !~
- [Issue #47](https://github.com/influxdb/influxdb/issues/47). Spill out query and database detail at the time of bug report

### Bugfixes

- [Issue #36](https://github.com/influxdb/influxdb/issues/36). The regex operator should be =~ not ~=
- [Issue #39](https://github.com/influxdb/influxdb/issues/39). Return proper content types from the http api
- [Issue #42](https://github.com/influxdb/influxdb/issues/42). Make the api consistent with the docs
- [Issue #41](https://github.com/influxdb/influxdb/issues/41). Table/Points not deleted when database is dropped
- [Issue #45](https://github.com/influxdb/influxdb/issues/45). Aggregation shouldn't mess up the order of the points
- [Issue #44](https://github.com/influxdb/influxdb/issues/44). Fix crashes on RHEL 5.9
- [Issue #34](https://github.com/influxdb/influxdb/issues/34). Ascending order always return null for columns that have a null value
- [Issue #55](https://github.com/influxdb/influxdb/issues/55). Limit should limit the points that match the Where clause
- [Issue #53](https://github.com/influxdb/influxdb/issues/53). Writing null values via HTTP API fails

### Deprecated

- Preparing to deprecate `/dbs` (for listing databases) in favor of a more consistent `/db` endpoint
- Preparing to deprecate `username` field for a more consistent `name` field in the `/db/:db/users`
- Preparing to deprecate endpoints `/db/:db/admins/:user` in favor of using `/db/:db/users/:user` which should
  be used to update user flags, password, etc.

## v0.3.0

## Features

- [Issue #51](https://github.com/influxdb/influxdb/issues/51). Implement first and last aggregates
- [Issue #35](https://github.com/influxdb/influxdb/issues/35). Support table aliases in Join Queries
- [Issue #71](https://github.com/influxdb/influxdb/issues/71). Add WillReturnSingleSeries to the Query
- [Issue #61](https://github.com/influxdb/influxdb/issues/61). Limit should default to 10k
- [Issue #59](https://github.com/influxdb/influxdb/issues/59). Add histogram aggregate function

## Bugfixes

- Fix join and merges when the query is a descending order query
- [Issue #57](https://github.com/influxdb/influxdb/issues/57). Don't panic when type of time != float
- [Issue #63](https://github.com/influxdb/influxdb/issues/63). Aggregate queries should not have a sequence_number column

## v0.3.2

## Features

- [Issue #82](https://github.com/influxdb/influxdb/issues/82). Add endpoint for listing available admin interfaces.
- [Issue #80](https://github.com/influxdb/influxdb/issues/80). Support durations when specifying start and end time
- [Issue #81](https://github.com/influxdb/influxdb/issues/81). Add support for IN

## Bugfixes

- [Issue #75](https://github.com/influxdb/influxdb/issues/75). Don't allow time series names that start with underscore
- [Issue #85](https://github.com/influxdb/influxdb/issues/85). Non-existing columns exist after they have been queried before

## v0.4.0 [2014-01-17]

## Features

- [Issue #86](https://github.com/influxdb/influxdb/issues/86). Support arithmetic expressions in select clause
- [Issue #92](https://github.com/influxdb/influxdb/issues/92). Change '==' to '=' and '!=' to '<>'
- [Issue #88](https://github.com/influxdb/influxdb/issues/88). Support datetime strings
- [Issue #64](https://github.com/influxdb/influxdb/issues/64). Shard writes and queries across cluster with replay for briefly downed nodes (< 24 hrs)
- [Issue #78](https://github.com/influxdb/influxdb/issues/78). Sequence numbers persist across restarts so they're not reused
- [Issue #102](https://github.com/influxdb/influxdb/issues/102). Support expressions in where condition
- [Issue #101](https://github.com/influxdb/influxdb/issues/101). Support expressions in aggregates
- [Issue #62](https://github.com/influxdb/influxdb/issues/62). Support updating and deleting column values
- [Issue #96](https://github.com/influxdb/influxdb/issues/96). Replicate deletes in a cluster
- [Issue #94](https://github.com/influxdb/influxdb/issues/94). delete queries
- [Issue #116](https://github.com/influxdb/influxdb/issues/116). Use proper logging
- [Issue #40](https://github.com/influxdb/influxdb/issues/40). Use TOML instead of JSON in the config file
- [Issue #99](https://github.com/influxdb/influxdb/issues/99). Support list series in the query language
- [Issue #149](https://github.com/influxdb/influxdb/issues/149). Cluster admins should be able to perform reads and writes.
- [Issue #108](https://github.com/influxdb/influxdb/issues/108). Querying one point using `time =`
- [Issue #114](https://github.com/influxdb/influxdb/issues/114). Servers should periodically check that they're consistent.
- [Issue #93](https://github.com/influxdb/influxdb/issues/93). Should be able to drop a time series
- [Issue #177](https://github.com/influxdb/influxdb/issues/177). Support drop series in the query language.
- [Issue #184](https://github.com/influxdb/influxdb/issues/184). Implement Raft log compaction.
- [Issue #153](https://github.com/influxdb/influxdb/issues/153). Implement continuous queries

### Bugfixes

- [Issue #90](https://github.com/influxdb/influxdb/issues/90). Group by multiple columns panic
- [Issue #89](https://github.com/influxdb/influxdb/issues/89). 'Group by' combined with 'where' not working
- [Issue #106](https://github.com/influxdb/influxdb/issues/106). Don't panic if we only see one point and can't calculate derivative
- [Issue #105](https://github.com/influxdb/influxdb/issues/105). Panic when using a where clause that reference columns with null values
- [Issue #61](https://github.com/influxdb/influxdb/issues/61). Remove default limits from queries
- [Issue #118](https://github.com/influxdb/influxdb/issues/118). Make column names starting with '_' legal
- [Issue #121](https://github.com/influxdb/influxdb/issues/121). Don't fall back to the cluster admin auth if the db user auth fails
- [Issue #127](https://github.com/influxdb/influxdb/issues/127). Return error on delete queries with where condition that don't have time
- [Issue #117](https://github.com/influxdb/influxdb/issues/117). Fill empty groups with default values
- [Issue #150](https://github.com/influxdb/influxdb/pull/150). Fix parser for when multiple divisions look like a regex.
- [Issue #158](https://github.com/influxdb/influxdb/issues/158). Logged deletes should be stored with the time range if missing.
- [Issue #136](https://github.com/influxdb/influxdb/issues/136). Make sure writes are replicated in order to avoid triggering replays
- [Issue #145](https://github.com/influxdb/influxdb/issues/145). Server fails to join cluster if all starting at same time.
- [Issue #176](https://github.com/influxdb/influxdb/issues/176). Drop database should take effect on all nodes
- [Issue #180](https://github.com/influxdb/influxdb/issues/180). Column names not returned when running multi-node cluster and writing more than one point.
- [Issue #182](https://github.com/influxdb/influxdb/issues/182). Queries with invalid limit clause crash the server

### Deprecated

- deprecate '==' and '!=' in favor of '=' and '<>', respectively
- deprecate `/dbs` (for listing databases) in favor of a more consistent `/db` endpoint
- deprecate `username` field for a more consistent `name` field in `/db/:db/users` and `/cluster_admins`
- deprecate endpoints `/db/:db/admins/:user` in favor of using `/db/:db/users/:user` which should
  be used to update user flags, password, etc.
- Querying for column names that don't exist no longer throws an error.

## v0.4.1 [2014-01-30]

### Features

- [Issue #193](https://github.com/influxdb/influxdb/issues/193). Allow logging to stdout. Thanks @schmurfy
- [Issue #190](https://github.com/influxdb/influxdb/pull/190). Add support for SSL.
- [Issue #194](https://github.com/influxdb/influxdb/pull/194). Should be able to disable Admin interface.

### Bugfixes

- [Issue #33](https://github.com/influxdb/influxdb/issues/33). Don't call WriteHeader more than once per request
- [Issue #195](https://github.com/influxdb/influxdb/issues/195). Allow the bind address to be configurable, Thanks @schmurfy.
- [Issue #199](https://github.com/influxdb/influxdb/issues/199). Make the test timeout configurable
- [Issue #200](https://github.com/influxdb/influxdb/issues/200). Selecting `time` or `sequence_number` silently fail
- [Issue #215](https://github.com/influxdb/influxdb/pull/215). Server fails to start up after Raft log compaction and restart.

### Deprecated

## v0.4.3 [2014-01-31]

### Bugfixes

- [Issue #225](https://github.com/influxdb/influxdb/issues/225). Remove a hard limit on the points returned by the datastore
- [Issue #223](https://github.com/influxdb/influxdb/issues/223). Null values caused count(distinct()) to panic
- [Issue #224](https://github.com/influxdb/influxdb/issues/224). Null values broke replication due to protobuf limitation

## v0.4.4 [2014-02-05]

### Features

- Make the leveldb max open files configurable in the toml file

## v0.5.0-rc.1 [2014-02-25]

### Bugfixes

- Ensure large deletes don't take too much memory
- [Issue #240](https://github.com/influxdb/influxdb/pull/240). Unable to query against columns with `.` in the name.
- [Issue #250](https://github.com/influxdb/influxdb/pull/250). different result between normal and continuous query with "group by" clause
- [Issue #216](https://github.com/influxdb/influxdb/pull/216). Results with no points should exclude columns and points

### Features

- [Issue #243](https://github.com/influxdb/influxdb/issues/243). Should have endpoint to GET a user's attributes.
- [Issue #269](https://github.com/influxdb/influxdb/pull/269), [Issue #65](https://github.com/influxdb/influxdb/issues/65) New clustering architecture (see docs), with the side effect that queries can be distributed between multiple shards
- [Issue #164](https://github.com/influxdb/influxdb/pull/269),[Issue #103](https://github.com/influxdb/influxdb/pull/269),[Issue #166](https://github.com/influxdb/influxdb/pull/269),[Issue #165](https://github.com/influxdb/influxdb/pull/269),[Issue #132](https://github.com/influxdb/influxdb/pull/269) Make request log a log file instead of leveldb with recovery on startup

### Deprecated

- [Issue #189](https://github.com/influxdb/influxdb/issues/189). `/cluster_admins` and `/db/:db/users` return usernames in a `name` key instead of `username` key.
- [Issue #216](https://github.com/influxdb/influxdb/pull/216). Results with no points should exclude columns and points

## v0.5.0-rc.2 [2014-02-27]

### Bugfixes

- [Issue #274](https://github.com/influxdb/influxdb/issues/274). Crash after restart
- [Issue #277](https://github.com/influxdb/influxdb/issues/277). Ensure duplicate shards won't be created
- [Issue #279](https://github.com/influxdb/influxdb/issues/279). Limits not working on regex queries
- [Issue #281](https://github.com/influxdb/influxdb/issues/281). `./influxdb -v` should print the sha when building from source
- [Issue #283](https://github.com/influxdb/influxdb/issues/283). Dropping shard and restart in cluster causes panic.
- [Issue #288](https://github.com/influxdb/influxdb/issues/288). Sequence numbers should be unique per server id

## v0.5.0-rc.3 [2014-03-03]

### Bugfixes
- [Issue #69](https://github.com/influxdb/influxdb/issues/69). Support column aliases
- [Issue #287](https://github.com/influxdb/influxdb/issues/287). Make the lru cache size configurable
- [Issue #38](https://github.com/influxdb/influxdb/issues/38). Fix a memory leak discussed in this story
- [Issue #286](https://github.com/influxdb/influxdb/issues/286). Make the number of open shards configurable
- Make LevelDB use the max open files configuration option.

## v0.5.0-rc.4 [unreleased]

### Bugfixes
