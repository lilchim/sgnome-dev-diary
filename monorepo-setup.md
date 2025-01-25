Goal: Demonstrate MFEs developed in a monorepo utilizing yarn workspaces, where each MFE can be self hosted or served remotely with module federation.

The resulting application should be composable (ideally with a text config file)


## Install yarn and initialize a project
- Create a new repo
- `corepack enable` !! Must be in admin terminal !!
- `yarn init -2`

  Yarn recommends against installing yarn globally but we may need to do that on our laptops

## Add Workspaces
Workspaces should be declared before running any cli commands like `ng new` or `npx sv create`.
- To add an MFE called 'friend-list' and a host App:
  - Open `package.json`
  - Add a new workspace:
```json
"workspaces": [
    "friend-list",
    "app"
]
```

## Create a feature MFE and a host App
- run `npx sv create friend-list`
- run `npx sv create app`
