# Dotfiles

# install

- ### Xcode
    - App store
- ### [iterm](https://www.iterm2.com/downloads.html)
- ### [brew](https://brew.sh/)
- ### git 
    - `brew install git`
    - `git config --global user.name "mattmcfad"`
    - `git config --global user.email "mmcfadyen91@gmail.com"`
    - [generate ssh key](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/)
    - add to github
- ### fish
    - `brew install fish`
    - `git clone git@github.com:mattmcfad/oh-my-fish.git`
    - `cp oh-my-fish ~/.oh-my-fish`
    ## copy template of fish config into your config
    - `cp ~/.oh-my-fish/templates/config.fish ~/.config/`
    - [install rvm:](https://rvm.io/rvm/install)
    - [install powerline:](https://powerline.readthedocs.org/en/master/installation/osx.html)
    - [install fonts:](https://github.com/powerline/fonts)
    - Set font in iTerm2 to a downloaded powerline font


- ### nvm
    - `touch ~/.bash_profile`
    - `curl -o- `https://raw.githubusercontent.com/creationix/nvm/v0.33.2/install.sh | bash
    - `cd ~/.config/fish`
    - `git clone git://github.com/passcod/nvm-fish-wrapper.git nvm-wrapper`
    - `nvm install v6`
    - `nvm install v7`
    - `nvm install v8`
- ### mongo
    - `brew install mongodb`
    - `sudo mkdir -p /data/db`
    - #### run locally:
        ##### start server
        - terminal 1:
            - `mongod --port 27017 --dbpath /data/db`
        ##### add db user
        - terminal 2:
            -  `mongo`
            -  `use whatever-local`
            -  ```
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
            -  `mongo`
            -  `use whatever-local`
            - `db.auth("dev","abcd1234")`
        ##### run in background:
        - `brew services start mongodb`
        - `brew services stop mongodb`

- ### Caffeine
- ### Spectacle