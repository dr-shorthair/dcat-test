The directory /dcat/ with its history was copied from https://github.com/w3c/dxwg to here following the instructions given at https://stackoverflow.com/questions/41811986/git-move-directory-to-another-repository-while-keeping-the-history

This test appears to have been successful - the history goes back to June 2017, like the current repo - so we should be able to move move /dcat/ to https://github.com/w3c/dx-dcat preserving the history

Here's my terminal session
----
> Simon@timelygram MINGW64 /c/dev/W3C

$ cd dxwg/
> Simon@timelygram MINGW64 /c/dev/W3C/dxwg (gh-pages)

$ git subtree split -P dcat -b only-dcat

Created branch 'only-dcat'
c973909a605bb9e104f7f34ac76a12fba2191dae
>
> Simon@timelygram MINGW64 /c/dev/W3C/dxwg (gh-pages)

$ cd ../../dcat-test
> Simon@timelygram MINGW64 /c/dev/dcat-test (main)

$ git checkout --orphan no-history

Switched to a new branch 'no-history'
> 
> Simon@timelygram MINGW64 /c/dev/dcat-test (no-history)

$ git pull ../W3C/dxwg only-dcat

remote: Enumerating objects: 9247, done.

remote: Counting objects: 100% (9247/9247), done.

remote: Compressing objects: 100% (3120/3120), done.

Receiving objects: 100% (9247/9247), 14.88 MiB | 7.95 MiB/s, done.

remote: Total 9247 (delta 6212), reused 6493 (delta 6098), pack-reused 0 (from 0)

Resolving deltas: 100% (6212/6212), done.

From ../W3C/dxwg
 * branch            only-dcat  -> FETCH_HEAD

> Simon@timelygram MINGW64 /c/dev/dcat-test (no-history)

$ git checkout main

Switched to branch 'main'

Your branch is up to date with 'origin/main'.

> Simon@timelygram MINGW64 /c/dev/dcat-test (main)

$ git merge --allow-unrelated-histories no-history

Merge made by the 'ort' strategy.

alignments/LinkedDataPlatform                      |  183 +

config.js                                          |  338 +

dcat-tr-to-pr.md                                   |   78 +

dcat_10.html                                       | 1397 +++

examples/basic-example.jsonld                      |  176 +

examples/basic-example.ttl                         |   64 +

examples/catalog-record-schema.jsonld              |   41 +

examples/catalog-record-schema.rdf                 |   18 +

examples/catalog-record-schema.ttl                 |   14 +

... etc ...
