# Phaser 3 2D UI

Nothing much here for now. This repo will contain tests for building customizable UIs for Phaser 2D games.

## How To Build and Run
To run commands, open any terminal and change to the root directory of your local working copy.  The terminal that is built into VS Code works well and already starts in the right directory.  Press `Ctrl + ~` to bring it up.  I highly recommend switching the default terminal to be 'Bash' instead of 'Powershell' on windows.

The `public/index.html` file contains a `<script src="bundle.js">` tag, which means we need to create `public/bundle.js`. The npm command `npm run build` tells ESBuild how to create this bundle, starting with `src/main.js` and including all its dependencies.

`npm run dev` starts a local server on port 3000 that serves the contents of `public`.  Any request for `bundle.js` will cause it to automatically rebuild your game and then it will serve the results live.  Simply open `localhost:3000` in your browser and as you edit your code, have the developer-tools open.  When you refresh the page, it will automatically rebuild your game and serve the latest version. Make sure you have your browser's caching disabled (usually under the 'Network' tab of the developer tools).

When the game is run in `dev` mode, the global JS variable `__DEV__` is true.  You can use this variable with console logs and other statements to adjust behavior while developing the game.

`npm run prod` is similar to `dev` in that it runs a local server and builds your code as you go, BUT it does not generate a source-code map, it minifies the code, and `__DEV__` is set to false.  This is a 'preview' of the final production build you can do with the `build` command below.

`npm run build` will do a build only using minify with no sourcemap or local server and does NOT continue to monitor for changes.  Use this when you are ready to deploy your game to a dedicated web server. The game is completely contained under the `public` folder.

## License

[MIT](LICENSE).
