# Create-react-app with Husky + lint-staged + pre-commit Hooks

## Apply lint to staged files

  1. install Husky
```cmd
npm i -D husky
```
  2. install Husky hook
```cmd
npx husky install
```
  3. in script of package.json, add:
```json
"prepare":"husky install"
```
this will reinstall husky hook when you download package again.

  4. install lint-staged
```cmd
npm i lint-staged -D
```

  5. in package.json, add file you want to check before commit:
```json
"lint-staged": {
  "**/*.js": [
    "eslint --fix",
    "prettier --write", // if you want to use preittier
    "git add"
  ]
}
```

  6. Add hook using npx command
```cmd
npx husky add .husky/pre-commit "npx lint-staged"
```

