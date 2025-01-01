# Ollama Eliza

## pnpm list

```
Legend: production dependency, optional only, dev only

@ai16z/agent@0.1.1 /mnt/data1/nix/time/2025/01/01/eliza-starter

dependencies:
@ai16z/adapter-postgres 0.1.4-alpha.3
@ai16z/plugin-image-generation 0.1.4-alpha.3
@ai16z/adapter-sqlite 0.1.4-alpha.3
@ai16z/plugin-node 0.1.4-alpha.3
@ai16z/client-auto 0.1.4-alpha.3
@ai16z/plugin-solana 0.1.4-alpha.3
@ai16z/client-direct 0.1.4-alpha.3
@ai16z/plugin-starknet 0.1.4-alpha.3
@ai16z/client-discord 0.1.4-alpha.3
better-sqlite3 11.5.0
@ai16z/client-telegram 0.1.4-alpha.3
readline 1.3.0
@ai16z/client-twitter 0.1.4-alpha.3
ws 8.18.0
@ai16z/eliza 0.1.4-alpha.3
yargs 17.7.2
@ai16z/plugin-bootstrap 0.1.4-alpha.3

devDependencies:
ts-node 10.9.2
tsup 8.3.5
typescript 5.6.3
```

My steps
```
nvm install --lts
nvm use --lts
rm -rf node_modules/
rm -rf dist/
pnpm i && pnpm build && pnpm start
pnpm rebuild
pnpm start --characters="characters/eliza.character.json"
```


## Edit the character files

Open `agent/src/character.ts` to modify the default character. Uncomment and edit.

### Custom characters

To load custom characters instead:
- Use `pnpm start --characters="characters/eliza.character.json"`
- Multiple character files can be loaded simultaneously

### Add clients

```diff
- clients: [],
+ clients: ["twitter", "discord"],
```

## Duplicate the .env.example template

```bash
cp .env.example .env
```

\* Fill out the .env file with your own values.

### Add login credentials and keys to .env

```diff
-DISCORD_APPLICATION_ID=
-DISCORD_API_TOKEN= # Bot token
+DISCORD_APPLICATION_ID="000000772361146438"
+DISCORD_API_TOKEN="OTk1MTU1NzcyMzYxMT000000.000000.00000000000000000000000000000000"
...
-OPENROUTER_API_KEY=
+OPENROUTER_API_KEY="sk-xx-xx-xxx"
...
-TWITTER_USERNAME= # Account username
-TWITTER_PASSWORD= # Account password
-TWITTER_EMAIL= # Account email
+TWITTER_USERNAME="username"
+TWITTER_PASSWORD="password"
+TWITTER_EMAIL="your@email.com"
```

## Install dependencies and start your agent

```bash
pnpm i && pnpm start
```
