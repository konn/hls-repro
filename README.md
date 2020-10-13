# Reproduction Procedure
This repository aims at providing a minimal reproducing example
for [Issue #70 of haskell-language-server][hls70] and [#107 of ghcide][ghcide107]

## Setting
1. Checkout `10dbde048e8ac028e80f607445776c8375722f75` of haskell/ghcide.
2. Build with `stack build`.
4. Open this directory with VSCode. Make sure `hieExecutablePath` in `.vscode/setting.json`
   is set to the value of `stack exec -- where ghcide`.
5. run `cabal build` in the shell.
6. Open `src/Lib.hs`.
7. HLS complains that:
   
   ```
   {
      	"resource": "/Users/hiromi/Documents/Programming/Haskell/git/hls-repro/src/Lib.hs",
      	"owner": "Haskell (hls-repro)",
      	"severity": 8,
      	"message": "Unexpected usage error\nCould not load module ‘Lib.Plugin’\nIt is a member of the hidden package ‘hls-repro-0.1.0.0’.\nPerhaps you need to add ‘hls-repro’ to the build-depends in your .cabal file.\n",
      	"source": "pragmas",
      	"startLineNumber": 1,
      	"startColumn": 1,
      	"endLineNumber": 2,
      	"endColumn": 1
   }
   ```

[hls70]: https://github.com/haskell/haskell-language-server/issues/70
[ghcide107]: https://github.com/haskell/ghcide/issues/107
