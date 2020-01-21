# Setup
Workstation configuration for a Fedora OS install using `ansible-pull`

**WARNING: This is a _destructive_ action**

# Use

  1. Setup an ssh key and add to your github repo (or fork and use HTTPS).
  2. Install ansible and pull the playbook from the repo

```
  sudo dnf install ansible
  ansible-pull -U git@github.com:jeremy-hanna/setup.git
```

# Install list

  - installs system packages (see: [packages]())
  - clones and installs [dotfiles]() via the ansible role (see: [dotfiles]())
  - compiles and builds any local tooling (see: [clang]())
  - sets up development directories
  - sets system settings (see: [settings]())
  - install software (see: [software]())


**Packages**
[chruby](https://copr.fedorainfracloud.org/coprs/postmodern/chruby/),
[ruby](https://www.ruby-lang.org/en/documentation/installation/#yum),
[vim](),
[ctags](),
[i3](https://fedoramagazine.org/getting-started-i3-window-manager/),


**Clang**
[caps2esc](https://gitlab.com/interception/linux/plugins/caps2esc),
[golang](https://golang.org/doc/install#tarball),


**Settings**
[Trackpad tap click](),
[Sleep power fix](),


**Software**
[Spotify for linux](),
[Dropbox?](),
[VLC](),


# References
https://opensource.com/article/18/3/manage-workstation-ansible
https://opensource.com/article/18/3/manage-your-workstation-configuration-ansible-part-2
