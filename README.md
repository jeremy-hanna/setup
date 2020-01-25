# Setup
Workstation configuration for a Fedora OS install using `ansible-pull`

**WARNING:** This is a **_destructive_** action

# Use

  1. Setup an ssh key and add to your github repo (or fork and use HTTPS).
  2. Install ansible and pull the playbook from the repo

```
  sudo dnf install ansible
  ansible-pull -K -U git@github.com:jeremy-hanna/setup.git
```

# Install list

  - installs system packages (see: [packages]())
  - clones and installs [dotfiles]() via the ansible role (see: [dotfiles]())
  - compiles and builds any local tooling (see: [clang]())
  - sets up development directories
  - sets system settings (see: [settings]())
  - install software (see: [software]())


**Packages**
[ruby](https://www.ruby-lang.org/en/documentation/installation/#yum),
[vim + vim-plug](),
[ctags](https://docs.ctags.io/en/latest/),
[i3](https://fedoramagazine.org/getting-started-i3-window-manager/),
[golang](https://developer.fedoraproject.org/tech/languages/go/go-installation.html#go-installation),
[zsh + zplug](),
[uxrvt](),


**Compiled**
[caps2esc](https://gitlab.com/interception/linux/plugins/caps2esc),
[chruby](https://github.com/postmodern/chruby#setupsh),


**Settings**
[Trackpad tap click](https://cravencode.com/post/essentials/enable-tap-to-click-in-i3wm/),
[Sleep power fix](),


**Software**
[Spotify for linux](),
[Dropbox?](),
[VLC](),


# Notes:
- ansible git module checks for `git status --porcelain` and doesn't pull otherwise avoiding un-merged changes
- COPR dnf enabled for things like universal-ctags in the role they're installed in

# TODO:
## MVP
- [ ] caps2esc build step
- [ ] add applications (dropbox, spotify, etc.)
- [ ] figure out how to configure markdown notes between machines

## Bugs
- [ ] hardware related things (HDMI display, speakers, etc.)
- [ ] reload .Xmodmap key bindings /dev/input

## Nice-to-haves
- [ ] improve theme https://github.com/sindresorhus/pure
- [ ] timestamp install things like vim-plug or zplug for dotfile changes
- [ ] Remove unnecessary applications on fedora
- [ ] use better things than hacky shell commands
- [ ] migrate dotfiles to use GNU Stow and update this
- [ ] get compliant with ansible-lint

# References
https://opensource.com/article/18/3/manage-workstation-ansible
https://opensource.com/article/18/3/manage-your-workstation-configuration-ansible-part-2
