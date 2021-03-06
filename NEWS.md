# Parkour News – history of user-visible changes

## 0.5.4 / 2014-02-08

- Ensure job-failure clean-up runs only once.
- Only set job JAR in basic cstep when still unset.
- Working local-mode tests under an active cluster configuration.
- Build job JARs and launch remote jobs from the REPL.
- Support experimental collfn ::{source,sink}-as metadata.
- Round-trip fragment-less distcache URIs through fs/distcache!.
- Added sampling dseq.
- Include any local task exception in job failure cause chain.

## 0.5.3 / 2014-01-18

- Add `fs/path-exists?` function.
- Stop deleting job output paths when they already exist.
- Drop support for Hadoop version 0.20.205.
- Properly close `dux` record writers when leaving task scope.
- Add explicit `dux/{map,combine}-output` sink functions.
- Delete output paths for in-progress jobs when interrupted.

## 0.5.2 / 2013-12-04

- Restore parallel execution for cluster jobs.
- Fix NPE caused by `nil`-dseq dsinks.

## 0.5.1 / 2013-12-03

- Fix broken ability to specify Avro grouping schema via `shuffle` config step.
- Run local jobs in serial to work around MAPREDUCE-5367.
- Work-around allowing Avro multiple files per named output.
- Expose extended version of configuration test-helper.

## 0.5.0 / 2013-11-17

### Breaking changes

- The default map/reduce task function interface uses the new `collfn` adapter.
  The previous interface may be specified via the `contextfn` adapter.
- Local reduction of dseqs yields unwrapped values.  Raw values may be accessed
  via `source-for` with the `:raw?` option.

### Other changes

- Allow seqs to be used as tuple sources.
- Allow chaining of `sink-as` results to source-shaping functions.
- Allow var entry points to directly specify the adapter function used to
  transform their values to the type-specific Parkour base interface.

## 0.4.1 / 2013-11-15

- Fix bug in `reduced` handling of job tuple-source reductions.
- Make tuple-source re-shape results `seq`able, allowing tasks to be written in
  terms of lazy sequences.

## 0.4.0 / 2013-11-04

- Initial public release.
