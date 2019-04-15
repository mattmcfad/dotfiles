# Dotfiles

# install

- ### Xcode
  - App store
- ### [iterm](https://www.iterm2.com/downloads.html)
- ### [brew](https://brew.sh/)
- `defaults write com.apple.finder AppleShowAllFiles YES`
- OPTION + right click finder -> relaunch
- ### git

  - `brew install git`
  - `git config --global user.name "mattmcfad"`
  - `git config --global user.email "mmcfadyen91@gmail.com"`
  - [generate ssh key](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/)
  - add to github

- ### nvm

- ### fish

  - `brew install fish`
  - Add the fish shell /usr/local/bin/fish to /etc/shells with:
    - `echo /usr/local/bin/fish | sudo tee -a /etc/shells`
  - Change your default shell to fish with:
    - `chsh -s /usr/local/bin/fish`
  - Install oh-my-fish
    - `curl -L https://get.oh-my.fish | fish`
  - Install RVM
    - `curl -L https://get.rvm.io | bash -s stable`
  - Install omf packages
    - `omf install nvm`
    - `omf install rvm`
    - `omf install bobthefish`
    - `omf theme bobthefish`
  - Add custom functions to `~/.config/fish/functions`
  - [install fonts:](https://github.com/powerline/fonts)
  - Set font in iTerm2 to a downloaded powerline font

* ### mongo

  - `brew install mongodb`
  - `sudo mkdir -p /data/db`
  - #### run locally:
    ##### start server
    - terminal 1:
      - `mongod --port 27017 --dbpath /data/db`
    ##### add db user
    - terminal 2:
      - `mongo`
      - `use whatever-local`
      - ```
         db.createUser(
             {
                 user: "dev",
                 pwd: "abcd1234",
                 roles: [ { role: "userAdminAnyDatabase", db: "admin" },{role: "readWrite", db: "whatever-local"} ]
             }
         )
        ```
    ##### restart locally with auth
    - terminal 1:
      - `mongod --auth --port 27017 --dbpath /data/db`
    ##### test authentication
    - terminal 2:
      - `mongo`
      - `use whatever-local`
      - `db.auth("dev","abcd1234")`
    ##### run in background:
    - `brew services start mongodb`
    - `brew services stop mongodb`

- ### Caffeine
- ### Spectacle
