## Purpose

The output of this command displays all git commits wich include a given string.

## Code

```bash
git log -G <SEARCHTERM>
```

## Example

```bash
┌─[12:56:46]-[:)]-[fschneider@frank]-[/home/fschneider/repos/belegauskunft/ (master)]
└──> git log -G regexToCheckKeyFor
commit 210b9c0d5bd37d6b31ce80379b2332ec4d4cae9a
Author: Felix Schneider <fschneider@abm.de>
Date:   Sat Jan 8 13:11:45 2022 +0100

    {FIX} Regex für die Key-Überprüfung gefixt

commit 3959e1fac6f68ccd6573695a170bbf9cd37414b2
Author: Felix Schneider <fschneider@abm.de>
Date:   Thu Dec 16 11:24:54 2021 +0100

    {ENHANCEMENT} Check the input keys for their validity as well as their values

    Signed-off-by: Felix Schneider <fschneider@abm.de>
```

## Additional notes

- `--all` searches over branches
- `-p` also shows the changes not only the commit information
  - Alternatively: `git show <hash>`
- [Source](https://stackoverflow.com/a/4472267)