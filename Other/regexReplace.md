## Purpose

I want to insert a space between the comment character and the comment string.

Example: `#Testcomment` becomes `# Testcomment`

## Code

Comment character is `#` (i.e. in `Bash`)

Search for `(#)([a-zA-ZÄÖÜäöü])`

Replace with `$1 $2`

## Example

- Comment character is `#`
    ```js
    $ str="#Testcomment"
    '#d'

    $ str.replace(/(#)([a-zA-ZÄÖÜäöü])/, '$1 $2')
    '# Testcomment'
    ```

- Comment character is `//` (i.e. in `JavaScript`)
    ```js
    $ str="#Testcomment"
    '//Testcomment'

    $ str.replace(/(\/\/)([a-zA-ZÄÖÜäöü])/, '$1 $2')
    '// Testcomment'
    ```

## Additional notes

- (In `Bash`) You want to replace all occurrences manually since bash uses the `#` character to determine the length of a string (i.e `${#string}`)
