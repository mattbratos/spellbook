### mac-default-editor

### problem

Mac os opens all code files with xcode and it's super anoying

### solution

based on this [post](https://stackoverflow.com/a/70402997/24881198)
and this [tool](https://github.com/moretension/duti?tab=readme-ov-file)

I wrote those scripts:

#### vs code

```bash
curl "https://raw.githubusercontent.com/github/linguist/master/lib/linguist/languages.yml" \
  | yq -r "to_entries | (map(.value.extensions) | flatten) - [null] | unique | .[]" \
  | xargs -L 1 -I "{}" duti -s com.microsoft.VSCode {} all


# Use duti to set defaults for specific files to VSCode
duti -s com.microsoft.VSCode public.plain-text all
duti -s com.microsoft.VSCode public.source-code all
duti -s com.microsoft.VSCode public.data all
duti -s com.microsoft.VSCode .css all
duti -s com.microsoft.VSCode .gitattributes all
duti -s com.microsoft.VSCode .gitignore all
duti -s com.microsoft.VSCode .htaccess all
duti -s com.microsoft.VSCode .js all
duti -s com.microsoft.VSCode .json all
duti -s com.microsoft.VSCode .link all
duti -s com.microsoft.VSCode .md all
duti -s com.microsoft.VSCode .mv all
duti -s com.microsoft.VSCode .mvt all
duti -s com.microsoft.VSCode .scss all
duti -s com.microsoft.VSCode .sh all
duti -s com.microsoft.VSCode .txt all
duti -s com.microsoft.VSCode .xml all
duti -s com.microsoft.VSCode .yaml all
duti -s com.microsoft.VSCode .zsh all
```

#### zed

```bash
curl "https://raw.githubusercontent.com/github/linguist/master/lib/linguist/languages.yml" \
  | yq -r "to_entries | (map(.value.extensions) | flatten) - [null] | unique | .[]" \
  | xargs -L 1 -I "{}" duti -s dev.zed.Zed {} all



# Use duti to set defaults for specific files to VSCode
duti -s dev.zed.Zed public.plain-text all
duti -s dev.zed.Zed public.source-code all
duti -s dev.zed.Zed public.data all
duti -s dev.zed.Zed .css all
duti -s dev.zed.Zed .gitattributes all
duti -s dev.zed.Zed .gitignore all
duti -s dev.zed.Zed .htaccess all
duti -s dev.zed.Zed .js all
duti -s dev.zed.Zed .json all
duti -s dev.zed.Zed .link all
duti -s dev.zed.Zed .md all
duti -s dev.zed.Zed .mv all
duti -s dev.zed.Zed .mvt all
duti -s dev.zed.Zed .scss all
duti -s dev.zed.Zed .sh all
duti -s dev.zed.Zed .txt all
duti -s dev.zed.Zed .xml all
duti -s dev.zed.Zed .yaml all
duti -s dev.zed.Zed .zsh all

```

### usage

simple copy paste the code put in your termial and hope it works (it works on my machine 🙃)
