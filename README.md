# Reproduction Procedure
This repository aims at providing a minimal reproducing example
for [Issue #10 of haskell-language-server][hls10]

## Setting
1. Checkout `2a58af80f4859239b47a0c915c4e04030c06b3b6` of haskell-language-server.
2. Build with `stack --stack-yaml=stack-8.6.5.yaml build` (as cabal-install-hls fails at this time).
3. Copy resulting `haskell-language-server` binary to `~/.cabal/bin/haskell-language-server-8.6.5`,
   or other accessible path.
4. Open this directory with VSCode. Make sure `hieExecutablePath` in `.vscode/setting.json`
   is set to the installed location above.
5. run `cabal new-build` in the shell.
6. Open `src/Lib.hs`.
7. HLS complains that:
   
   ```
   Program error: attempting to use module ‘fake_uid:Lib.Plugin’ (~/path/to/hls-repro/src/Lib/Plugin.hs) which is not loaded
   ```

[hls10]: https://github.com/haskell/haskell-language-server/issues/70