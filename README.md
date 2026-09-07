# Gitea Customization for Blender Developer Portal

## Setup

- Clone this repo in a `custom` folder at the root of your gitea install.
- Edit app.ini to set the following in the `[ui]` section:
  - `DEFAULT_THEME = bthree-dark`
  - `THEMES = bthree-dark`
- Run the gitea binary with the following arguments (or do the clone into Gitea's own `custom` directory, merging with your `conf` dir).
  - --custom-path pointing to the repo directory
  - --config pointing to the custom app.ini
- Update your user preferences to set the new theme, or it will keep showing the old one.

## Alternative setup with Docker

- Initialize `docker-compose.yml` following Gitea's [basic instructions](https://docs.gitea.com/installation/install-with-docker#basics).
- Install Gitea following Gitea's [installation instructions](https://docs.gitea.com/installation/install-with-docker#installation).
- Edit `app.ini` in `[Gitea's root]/conf` to append the following:
```
[ui]
DEFAULT_THEME = bthree-dark
THEMES = bthree-dark
```
(Docker Gitea's root directory defaults to `/gitea/gitea/` from installation root.)
- Clone this repository to Gitea's root directory, so that its contents are merged. (Gitea's _custom_ directory defaults to Gitea's root.)

Gitea's root flat directory tree should look similar to the following, if done correctly:
```
.
├── actions_artifacts
├── actions_log
├── attachments
├── avatars
├── conf
├── gitea.db
├── home
├── indexers
├── jwt
├── log
├── packages
├── public
├── queues
├── README.md
├── repo-archive
├── repo-avatars
├── sessions
├── sphinx
├── templates
└── tmp
```
