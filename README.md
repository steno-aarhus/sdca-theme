> [!IMPORTANT]
>  While we can set up a website in the `steno-aarhus` GitHub organisation for you, 
> and we can help you getting started, your website is your responsibility. This 
> includes e.g., the content, structure, and 
> [web accessibility](https://steno-aarhus.github.io/research/contributing/github-websites.html#web-accessibility). 
> 
> See the list of 
> [useful resources](https://steno-aarhus.github.io/research/contributing/github-websites.html)
> on the Research website.

# sdca-theme: Theming and styling for SDCA websites

## Installing

Install [Quarto](https://quarto.org/docs/get-started/), then open a
Terminal and type out:

``` bash
quarto use template steno-aarhus/sdca-theme
```

This will install the extension and create a template that you can use
as a starting place for the website.

## Setting up a new website

> [!NOTE]
> This section is mainly for the admins of the Steno Aarhus GitHub organisation.

1. On GitHub, create a
   [team](https://github.com/orgs/steno-aarhus/teams) for the new
   website and add the relevant people to the team.

2. Create the website files locally using the Seedcase
   [Template Website](https://template-website.seedcase-project.org/)
   (choose the simple version when prompted), then apply the SDCA theme:

   ```bash
   uvx copier copy --trust gh:seedcase-project/template-website <repo-name>
   cd <repo-name>
   quarto use template steno-aarhus/sdca-theme
   ```

3. Modify files as needed (look for TODO items), then push to GitHub.
   Replace `<repo-name>` and `<team-name>` with the actual names:

   ``` bash
   git add .
   git commit -m "Initial commit"
   gh repo create steno-aarhus/<repo-name> --public --source .--disable-wiki --push --team <team-name>
   quarto publish gh-pages
   ```

4. On GitHub, give the repository team write access to the the new repository.

5. On GitHub, add a repository description and the website URL in the
   repository's `<> Code` tab.

6. To sync the repository to the Steno Aarhus website, add topics to the
   repository. In the `steno-aarhus` organisation, go to
   Settings > Repository > Topics. Find the new repository and add topics
   as listed
   [here](https://github.com/steno-aarhus/steno-aarhus.github.io/blob/main/_build.sh).
   Must be `website` *and* one of the other topics listed there.
