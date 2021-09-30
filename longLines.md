## Purpose

The output of this command displays all lines in a given file that are longer than `$linelength`. This is useful for finding long lines to refactor them to be shorter.

## Code

```bash
file=bas #File to go through
linelength=140 #Print all lines longer than 140 characters

linecounter=0; cat $file | while IFS= read -r line; do ((linecounter++)); chars=${#line}; if (( $chars > $linelength )); then echo -e "Zeile: $linecounter\tZeichen: $chars"; fi ; done
```

## Example

```bash
┌─[11:53:48]-[:)]-[fschneider@frank]-[/home/fschneider/repos/bas/ (master)]
└──> file=bas; linecounter=0; cat $file | while IFS= read -r line; do ((linecounter++)); chars=${#line}; if (( $chars > 140 )); then echo -e "Zeile: $linecounter\tZeichen: $chars"; fi ; done
Zeile: 146	Zeichen: 149
Zeile: 149	Zeichen: 204
Zeile: 155	Zeichen: 158
Zeile: 158	Zeichen: 163
Zeile: 164	Zeichen: 184
Zeile: 167	Zeichen: 169
Zeile: 174	Zeichen: 144
Zeile: 183	Zeichen: 243
Zeile: 186	Zeichen: 154
Zeile: 189	Zeichen: 148
Zeile: 194	Zeichen: 191
Zeile: 196	Zeichen: 142
Zeile: 261	Zeichen: 164
Zeile: 268	Zeichen: 160
Zeile: 283	Zeichen: 336
Zeile: 287	Zeichen: 227
Zeile: 309	Zeichen: 174
Zeile: 315	Zeichen: 194
Zeile: 330	Zeichen: 163
Zeile: 332	Zeichen: 161
Zeile: 337	Zeichen: 141
Zeile: 347	Zeichen: 159
Zeile: 479	Zeichen: 167
Zeile: 663	Zeichen: 173
Zeile: 665	Zeichen: 144
Zeile: 683	Zeichen: 192
Zeile: 688	Zeichen: 159
Zeile: 708	Zeichen: 180
Zeile: 710	Zeichen: 144
Zeile: 738	Zeichen: 156
Zeile: 753	Zeichen: 145
Zeile: 777	Zeichen: 147
Zeile: 824	Zeichen: 144
Zeile: 834	Zeichen: 172
Zeile: 882	Zeichen: 154
Zeile: 930	Zeichen: 217
Zeile: 934	Zeichen: 256
Zeile: 939	Zeichen: 184
Zeile: 973	Zeichen: 178
Zeile: 978	Zeichen: 146
Zeile: 980	Zeichen: 164
Zeile: 1015	Zeichen: 207
Zeile: 1017	Zeichen: 144
Zeile: 1108	Zeichen: 190
Zeile: 1110	Zeichen: 189
Zeile: 1111	Zeichen: 187
Zeile: 1116	Zeichen: 182
Zeile: 1120	Zeichen: 144
```

## Additional notes

- Append `| wc -l` to the code to count the problematic lines.
  - This cannot be done with a variable inside the for-loop since read opens a subshell and variables set inside of it aren't available after the loop