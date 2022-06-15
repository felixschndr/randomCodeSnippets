## Purpose

This commands lets the user easily and quick find large files in a given directory. Particularly in large directories (like `/`) it's **much** faster than `du`.

## Code

```bash
ncdu
```

## Example

```bash
--- /home/fschneider -----------------------------------------------------------------------------------
  150,5 GiB [##########] /repos
   10,6 GiB [          ] /.local
    5,2 GiB [          ] /.cache
    2,5 GiB [          ] /.config
    1,2 GiB [          ] /.vscode
  759,7 MiB [          ] /snap
  247,5 MiB [          ] /Dokumente
   97,8 MiB [          ] /.mozilla
   78,4 MiB [          ] /.chrome
    1,7 MiB [          ] /Downloads
```
```bash
--- /home/fschneider/repos/belegauskunft ---------------------------------------------------------------
                         /..
   15,4 MiB [##########] /.git
   13,0 MiB [########  ] /node_modules
    6,1 MiB [###       ] /javascript
  648,0 KiB [          ] /Ressources
   52,0 KiB [          ] /docs
   48,0 KiB [          ]  package-lock.json
   40,0 KiB [          ] /styles
   28,0 KiB [          ]  index.html
    4,0 KiB [          ]  package.json
    4,0 KiB [          ]  .gitignore
    4,0 KiB [          ]  README.md
```

## Additional notes

- Use `-x` to not access other filessystems
