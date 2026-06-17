# Generate( mason-receipt.json )
https://github.com/mason-org/mason.nvim/issues/1578#issuecomment-2455253723

Source:
```
sudo install clangd jq
mkdir -p ~/.local/share/nvim/mason/packages/clangd/mason-schemas
cd ~/.local/share/nvim/mason/packages/clangd
curl https://raw.githubusercontent.com/clangd/vscode-clangd/master/package.json \
    | jq .contributes.configuration > mason-schemas/lsp.json
echo '{"schema_version":"1.1","primary_source":{"type":"local"},"name":"clangd","links":{"share":{"mason-schemas/lsp/clangd.json":"mason-schemas/lsp.json"}}}' \
    > mason-receipt.json
```

# Copy & symlink working install from x86
https://github.com/mason-org/mason.nvim/issues/1578#issuecomment-2034607549

quote:
>Update: I copied the directory ~/.local/share/nvim/mason/packages/clangd from my x86 machine and then I had to trick mason and change the sim link to the clangd installed with the system.
>```user at ubuntu-vm in ~/.local/share/nvim/mason/bin$ ls -l clangd
>lrwxrwxrwx 1 dierus01 dierus01  18 Apr  3 16:07 clangd -> /usr/bin/clangd-17
>```
