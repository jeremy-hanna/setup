# Setup
Workstation configuration for a Fedora or Mac OS install using `ansible-pull`

**WARNING:** This is a **_destructive_** action

# Use

  1. Setup an ssh key and add to your github repo (or fork and use HTTPS).
  2. Install ansible and pull the playbook from the repo

__Linux__:
```
  sudo dnf install ansible
  ansible-pull -K -U git@github.com:jeremy-hanna/setup.git
```

__Mac OS X__:
```
  xcode-select --install
  /usr/local/bin/pip3 install ansible
  export PATH=$PATH:/Library/Frameworks/Python.framework/Versions/3.8/bin
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
- [x] caps2esc build step
- [ ] add applications (dropbox, spotify, etc.)
- [ ] figure out how to configure markdown notes between machines

## Bugs
- [ ] hardware related things (HDMI display, speakers, etc.)
- [ ] reload .Xmodmap key bindings /dev/input

## Mac bugs
- [x] ctags is not universal-ctags
- [x] ctags does not link from dotfiles
- [x] vim is not latest vim, install it with brew
- [ ] can't link out through the /usr/bin/vim to in catalina - need alias in dotfiles
- [ ] use package install instead of homebrew module
- [ ] `~/.vim` folder exists always and needs to be linked in a better way
- [ ] Karabiner pieces access Documents folder
- [ ] install fonts from dotfiles
- [ ] change iterm2 profile loading
- [ ] add touchbar considerations to osx_defaults
- [ ] configure workspaces and keyboard movements

## Nice-to-haves
- [x] improve theme https://github.com/sindresorhus/pure
- [ ] timestamp install things like vim-plug or zplug for dotfile changes
- [x] Remove unnecessary applications on fedora
- [ ] use better things than hacky shell commands
- [ ] migrate dotfiles to use GNU Stow and update this
- [ ] get compliant with ansible-lint
- [ ] merge OS X playbook into this same repo but [switch on OS](https://unix.stackexchange.com/questions/6345/how-can-i-get-distribution-name-and-version-number-in-a-simple-shell-script)

# References
https://opensource.com/article/18/3/manage-workstation-ansible  
https://opensource.com/article/18/3/manage-your-workstation-configuration-ansible-part-2  
https://snow-dev.com/posts/next-level-dotfiles-with-ansible.html  
