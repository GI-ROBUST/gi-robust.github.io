# Robust Workshop Website

## Local build
non-NixOS:
```
bundle install
bundle exec jekyll serve --livereload
```

NixOS:
```
nix-shell
```

regenerate gemset.nix, following [Run Jekyll locally on NixOS by Wout Swinkels](https://woutswinkels.github.io/posts/Run-Jekyll-locally-on-NixOS/):
```
nix-shell -p bundler bundix
bundle config set path vendor
bundle config set --local force_ruby_platform true
bundle cache --no-install
bundix
rm -rf vendor
rm -rf ~/.cache/bundix
exit
```
