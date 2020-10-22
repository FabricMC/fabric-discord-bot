# fabric-discord-bot

This bot is designed for a specific discord server, so it most likely will not fit the needs of your server.

**Note:** If you're testing the bot, make sure you have both privileged intents enabled for the OAuth app.
[See here](https://discord.com/developers/docs/topics/gateway#privileged-intents) for more information.

If you're using the bot via Docker, note that `GIT_DIRECTORY` will automatically be set to `/git`. You
will most likely want to mount this directory.

## Configuration

Note that the bot can be configured using a config file called `config.toml` instead if you prefer. The part
of the environment variable name before the first underscore is the section you should use, and the rest
is the camelCase key you should use within that section.

For example, you might do this in a bash script:

```bash
export CHANNELS_ACTION_LOG_CATEGORY=764817953463861288
```

In `config.toml`, you might do this:

```toml
[channels]
actionLog = 746875064200462416
```

You may also use system properties to configure the bot. Configuration takes the following order of precedence, with
later sources overriding earlier ones:

* `default.toml` bundled inside the JAR
* Environment variables
* System properties
* `config.toml` if it exists

### Required Environment Variables 

* BOT_TOKEN = The discord bot token
* GITHUB_OAUTH = GitHub OAuth token
  
  
* DB_URL = MySQL URL, eg `mysql://host:port/database`
* DB_USERNAME = Database username to auth with
* DB_PASSWORD = Database password to auth with

### Optional Environment Variables 

* BOT_GUILD = The ID of the discord guild this bot should operate on
* BOT_EMOJI_GUILD = The ID of the discord guild this bot should index emojis from
* BOT_PREFIX = The prefix required for commands


* GIT_DIRECTORY = The directory to store cloned Git repositories (for extensions)


* GIT_TAGS_REPO_BRANCH = The branch name to checkout for the tags repo
* GIT_TAGS_REPO_URL = URL to the git repo containing tags
* GIT_TAGS_REPO_PATH = Root directory (within the repository) containing tags
  
  
* GITHUB_ORG = The target github organisation for the github commands.
* GITHUB_TOKEN = The github personal access token, with admin:org permission
    * Only optional if you are not using the github commands
  
  
* CHANNELS_ACTION_LOG_CATEGORY = The ID of the action log category
* CHANNELS_ALERTS = The ID of the alerts channel
* CHANNELS_BOT_COMMANDS = The ID of the bot commands channel
* CHANNELS_MODERATOR_LOG = The ID of the moderator log channel
  
  
* CHANNELS_IGNORED_CHANNELS = A list of channels to ignore for the purposes of filtering and logging
  
  
* ROLES_ADMIN = The ID of the admin role
* ROLES_MOD = The ID of the moderator role
* ROLES_TRAINEE_MOD = The ID of the trainee moderator role
* ROLES_MUTED = The ID of the muted role
  
  
* ROLES_NO_META = The ID of the meta-muted role
* ROLES_NO_REACTIONS = The ID of the reactions-muted role
* ROLES_NO_REQUESTS = The ID of the requests-muted role
* ROLES_NO_SUPPORT = The ID of the support-muted role
  

* ROLES_DEV_LIFE = The ID of the dev life role


* LIVE_UPDATES_MINECRAFT_CHANNELS = A comma separated list of discord channels to send minecraft version updates to
* LIVE_UPDATES_JIRA_CHANNELS = A comma separated list of discord channels to send JIRA version updates to
