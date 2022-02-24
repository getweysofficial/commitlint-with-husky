## Setup commitlint with Husky:

#### Run the following commands:

```bash
git init      # if git is not initialized
npm init -y   # if project doesn't contain package.json

# for linux/mac
npm i -D @commitlint/{cli,config-conventional}

# for windows
npm i -D @commitlint/cli @commitlint/config-conventional

echo "{ \"extends\": [\"@commitlint/config-conventional\"] }" > .commitlintrc.json

npm i -D husky
```

#### Add the following script in `package.json`
```json
"postinstall": "husky install"
```

#### Add `node_modules/` to your `.gitignore` file.

#### Now run the following commands
```bash
npx husky add .husky/commit-msg "npx commitlint --edit $1"

# commit the configuration
git add .
git commit -m "feat: configure commitlint"
```