# React to GitHub Pages

GitHub action to build and deploy React to GitHub Pages.  This uses the new GitHub Actions method as the source.  In the repository settings, go to Pages.  Under Source, select GitHub Actions.  No further configuration is needed.  

## Need help or have questions?
This project is supported by [Bitovi, A DevOps consultancy](https://www.bitovi.com/services/devops-consulting).

You can **get help or ask questions** on our:

- [Discord Community](https://discord.gg/J7ejFsZnJ4)!


Or, you can hire us for training, consulting, or development. [Set up a free consultation](https://www.bitovi.com/services/devops-consulting).

## Customizing

### Inputs

The following inputs can be used as `step.with` keys

| Name             | Type    | Description                        |
|------------------|---------|------------------------------------|
| `checkout`          | T/F  | Set to `false` if the code is already checked out (Default is `true`) (Optional) |
| `path` | String | Path of output files, Default is `dist` (Optional)|
| `build_command` | String | Specifies the command to run after `npm ci` for the build, Default is `npm run build` (Optional)|

## Example usage

Create `.github/workflows/deploy.yaml` with the following to build on push.

```yaml
on:
  push:
    branches:
      - "main" # change to the branch you wish to deploy from

permissions:
  contents: read
  pages: write
  id-token: write

jobs:
  deploy:
    environment:
      name: github-pages
      url: ${{ steps.build-publish.outputs.page_url }}
    runs-on: ubuntu-latest
    steps:
    - id: build-publish
      uses: bitovi/github-actions-react-to-github-pages@v1.2.0
      with:
        path: build # change to your build folder

```


## Contributing
We would love for you to contribute to [`bitovi/github-actions-react-to-github-pages`](hhttps://github.com/bitovi/github-actions-react-to-github-pages).   [Issues](https://github.com/bitovi/github-actions-react-to-github-pages/issues) and [Pull Requests](https://github.com/bitovi/github-actions-react-to-github-pages/pulls) are welcome!

## License
The scripts and documentation in this project are released under the [MIT License](https://github.com/bitovi/github-actions-react-to-github-pages/blob/main/LICENSE).

## Provided by Bitovi
[Bitovi](https://www.bitovi.com/) is a proud supporter of Open Source software.


