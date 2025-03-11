# sdca-theme: Theming and styling for SDCA websites

## Installing

Install [Quarto](https://quarto.org/docs/get-started/), then open a
Terminal and type out:

``` bash
quarto use template steno-aarhus/sdca-theme
```

This will install the extension and create an template that you can use
as a starting place for the website.

## Setting up a new website

This section is mainly for the admins of the Steno Aarhus GitHub. In the
directory above this theme folder, run:

``` bash
# Answer the questions that get asked
quarto use template steno-aarhus/sdca-theme
cd NEW-FOLDER
git init
cp ../sdca-theme/.gitignore .gitignore
cp -r ../sdca-theme/.github/ .github
mv .github/cc-by-license.md LICENSE.md
rm .github/sync.yml .github/workflows/sync-files.yml
mv sdca-theme.Rproj NEW-FOLDER.Rproj
```

Then modify the rest of the files as needed. Then continue with the next
bit of code (Note that you need to change `<repo-name>` and `<team-name` to
the actual names)

``` bash
git add .
git commit -m "Initial commit"
gh repo create steno-aarhus/<repo-name> --public --source . --disable-wiki --push --team <team-name>
quarto publish gh-pages
```
