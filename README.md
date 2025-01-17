# Rollupjs.org

This is the source code for the website. Note that the actual guide is now part of the [main rollup repo](https://github.com/rollup/rollup/tree/master/docs) and needs to be updated there, see below.

## Steps to build the website locally

1. `npm install`
2. `npm run update-guide`
3. `npm run build`
4. `npm run dev`
5. Open up http://localhost:3000

## Updating the guide contents

The guide is part of the main rollup repo, which again is added to this repo in form of a submodule. Running `npm run update-guide` should automatically initialize the submodule and copy the latest guide into a local folder. To update the guide contents:

1. Update the guide in a fork or a branch (if you have access rights) of the main rollup repo and make a pull request. Pull requests that add or modify features should always update the guide as well.
2. Once it is merged, check out the latest master branch in the submodule:
   ```bash
   cd rollup-submodule
   git checkout master
   git pull
   ```
3. Commit the new branch in the main repo:
   ```bash
   cd ..
   git add rollup-submodule
   git commit -m "Update guide"
   ```
   
Steps 2 and 3 should be done by the person merging the pull request in the main rollup repo. Once the commit has been pushed to `origin/master`, the website should be updated by the CI automatically. If necessary instead of checking out latest master, it is also possible to check out any other commit to e.g. test a pull request.

## Style Guidelines

- Please use `-` for bulleted list items.
- Please set a preferred line length of 100 characters in your editor for Markdown files in this repository.
- Please do not use hard line breaks to format blocks of plain text. Rather, please enable soft-line breaks in your editor.

## REPL links

Besides via shares containing the `shareable=` parameter generated by the REPL itself, the REPL can also pre-loaded from a Github gist. To do that

- add a `gist=<gist-id>` parameter to the URL, e.g. [`rollupjs.org/repl/?gist=e9c6c04b8f96adc562a70c096c3e7705`](https://rollupjs.org/repl/?gist=e9c6c04b8f96adc562a70c096c3e7705)
- if the gist contains a `main.js` file, this will be used as the first module in the REPL, otherwise an empty `main.js` file will be created
- additional entry points can be designated via adding an `entry=<comma-separated list of entry points>` parameter, e.g. [`rollupjs.org/repl/?gist=e9c6c04b8f96adc562a70c096c3e7705&entry=lower.js,upper.js`](https://rollupjs.org/repl?gist=e9c6c04b8f96adc562a70c096c3e7705&entry=lower.js,upper.js)
