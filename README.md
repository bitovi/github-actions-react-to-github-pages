# React to GitHub Pages

GitHub action to build and deploy React to GitHub Pages.  This uses the new GitHub Actions method as the source.  In the repository settings, go to Pages.  Under Source, select GitHub Actions.  No further configuration is needed.  

## Customizing

### Inputs

The following inputs can be used as `step.with` keys

| Name             | Type    | Description                        |
|------------------|---------|------------------------------------|
| `checkout`          | T/F  | Set to `false` if the code is already checked out (Default is `true`) (Optional) |

## Example usage

Create `.github/workflow/deploy.yaml` with the following to build on push.

```yaml
on:
  push:
    branches:
      - 'main'

jobs:
  build-deploy:
    runs-on: ubuntu-latest
    steps:
    - id: build-publish
      uses: bitovi/github-actions-react-to-ghp@v1.0.0

```


## Contributing
We would love for you to contribute to [`bitovi/github-actions-react-to-ghp`](hhttps://github.com/bitovi/github-actions-react-to-ghp).   [Issues](https://github.com/bitovi/github-actions-react-to-ghp/issues) and [Pull Requests](https://github.com/bitovi/github-actions-react-to-ghp/pulls) are welcome!

## License
The scripts and documentation in this project are released under the [MIT License](https://github.com/bitovi/github-actions-react-to-ghp/blob/main/LICENSE).

## Provided by Bitovi
[Bitovi](https://www.bitovi.com/) is a proud supporter of Open Source software.
