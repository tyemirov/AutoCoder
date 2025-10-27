# ISSUES (Append-only Log)

Entries record newly discovered requests or changes, with their outcomes. No instructive content lives here. Read @NOTES.md for the process to follow when fixing issues.

## Features

    


## Improvements

    

## BugFixes

- [ ] [NS-01] The tests are failing. Either fix the tests or the code
```
--- FAIL: TestGitCommitIfNeeded_NoIdentityError (0.02s)
    main_test.go:420: expected commit failure due to missing identity (local-only)
--- FAIL: TestProcessSingleRepository_SkipsUnreadableFile (0.04s)
    main_test.go:534: expected unreadable file to be skipped with an error, got: {repositoryRootPath:/tmp/TestProcessSingleRepository_SkipsUnreadableFile2386590614/001 goModPath:/tmp/TestProcessSingleRepository_SkipsUnreadableFile2386590614/001/go.mod didChangeGoMod:false changedFiles:[] skippedFiles:[] errors:[0xc000402af0] branchName: didCommit:false didPush:false}
FAIL
coverage: 89.9% of statements
FAIL    github.com/tyemirov/ns-rewrite  0.358s
FAIL
```

## Maintenance

## Planning 
do not work on the issues below, not ready
