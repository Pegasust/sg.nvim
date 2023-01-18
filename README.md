# sg.nvim

sg.nvim is a plugin focused on bringing many of the features of sourcegraph.com into Neovim.

## Features:

- [x] Read files:
  - [x] Directly from sourcegraph links: `:edit <sourcegraph url>`
    - `sg.nvim` will automatically add protocols for handling `https://sourcegraph.com/*` links.
  - [x] Directly from buffer names: `:edit sg://github.com/tjdevries/sam.py/-/src/test.cs`
- [ ] Reading non-files:
  - [ ] Repository roots
  - [ ] Folders
- [x] Use builtin LSP client to connect to SG
  - [x] Goto Definition
  - [ ] Goto References
    - [x] <20 references
    - [ ] kind of broken right now for lots of references
- [x] Basic Search
  - [x] literal, regexp and structural search support
  - [x] `type:symbol` support
  - [ ] repo support
- [ ] Advanced Search Features
  - [ ] Autocompletion
  - [ ] Memory of last searches
- More ??

## Installation

```lua
-- Use your favorite package manager to install, for example in lazy.nvim
return {
  {
    "tjdevries/sg.nvim",
    build = "cargo build --workspace",
    dependencies = { "nvim-lua/plenary.nvim" },
  },
}
```
### Setup:

```lua
-- Setup the LSP server to attach when you edit an sg:// buffer
require("sg").setup {
  -- Pass your own custom attach function
  --    If you do not pass your own attach function, then the following maps are provide:
  --        - gd -> goto definition
  --        - gr -> goto references
  on_attach = your_custom_lsp_attach_function
}
```

## Old Demos:

- Short clip of cross repository jumpt to definition: [Clip](https://clips.twitch.tv/AmazonianSullenSwordBloodTrail-l8H5WKEd8sNpEdIT)
- Demo v2: [YouTube](https://www.youtube.com/watch?v=RCyBnAx-4Q4)
- Demo v1: [YouTube](https://youtu.be/iCdsD6MiLQs)

