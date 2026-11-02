[![Discord](https://img.shields.io/badge/Discord-%235865F2.svg?style=for-the-badge&logo=discord&logoColor=white)](https://discord.gg/VuVhYUBbWE)[![GitHub](https://img.shields.io/badge/github-%23121011.svg?style=for-the-badge&logo=github&logoColor=white)](https://discord.gg/am7JUX83x4)[![Ko-fi](https://img.shields.io/badge/Ko--fi-F16061?style=for-the-badge&logo=ko-fi&logoColor=white)](https://ko-fi.com/thesixthroc)

#

# Misc

## How the packaging works

The [`semantic-release-factorio` plugin](https://github.com/fgardt/semantic-release-factorio) uses the `git archive` command to package the mod. \
That way you can specify what folders / files to exclude from your packaged mod by specifying them in [`.gitattributes`](.gitattributes).

If you want to locally test packaging of your mod you can run the following command:

```sh
git archive --format zip --prefix [YOUR-MOD-NAME]/ --worktree-attributes --output [YOUR-MOD-NAME]_[VERSION].zip HEAD
```

## Changing the commit message convention

If you want to change the commit message convention you can do so by changing the 2 `preset` fields in the [`.releaserc`](.releaserc) file. \
Possible presets are: [`angular`](https://github.com/conventional-changelog/conventional-changelog/tree/master/packages/conventional-changelog-angular), [`atom`](https://github.com/conventional-changelog/conventional-changelog/tree/master/packages/conventional-changelog-atom), [`codemirror`](https://github.com/conventional-changelog/conventional-changelog/tree/master/packages/conventional-changelog-codemirror), [`ember`](https://github.com/conventional-changelog/conventional-changelog/tree/master/packages/conventional-changelog-ember), [`eslint`](https://github.com/conventional-changelog/conventional-changelog/tree/master/packages/conventional-changelog-eslint), [`express`](https://github.com/conventional-changelog/conventional-changelog/tree/master/packages/conventional-changelog-express), [`jquery`](https://github.com/conventional-changelog/conventional-changelog/tree/master/packages/conventional-changelog-jquery), [`jshint`](https://github.com/conventional-changelog/conventional-changelog/tree/master/packages/conventional-changelog-jshint), [`conventionalcommits`](https://github.com/conventional-changelog/conventional-changelog/tree/master/packages/conventional-changelog-conventionalcommits).

Additionally you also need to modify the worflow file [`.github/workflows/release.yml`](.github/workflows/release.yml) to use the package that corresponds to your chosen preset. \
Replace `conventional-changelog-conventionalcommits` with `conventional-changelog-[YOUR PRESET]` accordingly.
