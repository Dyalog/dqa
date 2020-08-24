# dqa - the Dyalog QA Framework

This is an experimental framework used by Dyalog to write tests for the APL interpreter.

See functions in demos folder for examples of how to use the MATCH function.

## dqa.Run
dqa.Run demos                ⍝ to run all functions in the demos namespace
'.*18438' dqa.Run demos      ⍝ to run functions matching regex
dqa.Run demos 777 'c:\mydqa' ⍝ to set random seed (0 to leave random) and log file folder

By default, log files go into system temp folder.

## dqa.Report
dqa.Report (200824 1) 3      ⍝ To show details of error in component 3 of 1st file on August 24th
dqa.Report (0 2) 0           ⍝ To report ALL errors in 2nd file from today
dqa.Report (23 1) 2          ⍝ 2nd component, 1st file from yesterday

## dqa.Repro
dqa.Repro ...                ⍝ Return 0 if repro for error still fails, else 1 (same rargs as Report)
2 dqa.Repro ...              ⍝ Stop after recreating execution environment, before checking repro

## dqa.Cleanup

dqa.Cleanup ''|folder        ⍝ Delete all log files in folder ('' means temp folder)

## dqa.RandomArray

{seed} dqa.RandomArray (id types shape)
