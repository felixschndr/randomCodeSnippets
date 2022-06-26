## Purpose

This commands lets the user find duplicate lines in a file and sort them by the amount of their appearances.

## Code

```bash
file=default/diff/function
sed 's/^ *//g' "${file}" | sort | uniq -c | sort -n
```

## Example

```bash
--- /home/fschneider -----------------------------------------------------------------------------------
      1 *)
      1 [[ ${1} == "diff" ]] && cd "$(dirname "$(readlink -f "${BASH_SOURCE[@]}")")/../../"
      1 [[ ${1} == "force" ]] &&
        [...]
      1 "werden können! \e[0m"
      1 while [ ${pushed} == "false" ]; do
      1 [[ -z ${changed} ]] && changed=$(git diff --stat --staged "${filename}" 2>/dev/null | cut -d "|" -f2- | head -n 1)
      2 ;;
      2 [[ ${?} == 1 ]] && return
      2 [[ $(file "${file}") == *"CRLF"* ]] && echo && to_lf "${file}"
        [...]
      2 pushed=true
      2 return 0
      2 esac
      3 echo -e "\e[33mDer letzte Commit wird rückgängig gemacht:\e[0m\n" \
      3 git --no-pager log "origin/${diffbranch}..HEAD" --pretty="| %h | %s" --reverse | nl
      3 git reset --soft HEAD^ || echo -e "\e[31mEs gab ein Problem beim Rückgängig machen des Commits!"
        [...]
      3 local time=$(git log -n 1 --pretty="%ad" --date=format:'%H:%M:%S')
      3 "    Nachricht: \e[1;96m${commit_message}\e[0m\n        Datum: ${date}\n      Uhrzeit: ${time}\n         Hash: ${hash}"
      3 read -r -e answer
        [...]
     10 return
     11 continue
     20 else
     48 fi
     78
```

## Additional notes

- The `-n` of `sort` sorts by the number in the front
