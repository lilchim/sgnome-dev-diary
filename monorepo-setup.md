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

## Run an MFE in dev
- `yarn` to install dependencies across all workspaces
- `yarn workspace app run dev` to start in development
- Open browser and see the barebones app
!! Special Notice: For some reason postcss was not installed as a dependency. I don't know how this happened but it resulted in a server error. `yarn install postcss --dev` fixed this.

## Enabling Module Federation in an MFE
- `cd friend-list`
- `yarn add @originjs/vite-plugin-federation --dev`
- 


## Hosting an MFE in the app via module federation

