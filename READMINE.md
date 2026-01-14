# Tech Stack
1. Monorepo - NX, Turborepo (maintained by Vercel)
2. NextJS
3. Node-Express
4. TypeScript

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
# Setup
## 1. Create a folder: ecomm
   
## 2. Create a Turborepo with two example NextJS projects by default: docs, web
pnpm dlx create-turbo@latest

Where: . -> Package manager: pnpm -> Installs with two example NextJS projects in it

Folder Structure of a Turborepo project:
apps/              -> Contains applications like frontend, backend, services etc
packages/          -> Contains share tools like React components, utils, types, configurations etc
node_modules/
package.json
turbo.json
README.md
.gitignore
.npmrc

Note: We can run those two applications individually by going to their root project directories and using the command: pnpm run dev
      (or) 
      Alternatively we can run both at once using turbo (below)

## 3. Install turbo
ecomm(folder)>pnpm add turbo -w
ecomm(folder)>turbo dev

Tasks running (as per turbo.json file): turborepo goes to all package.json file of all the applications & packages to run their tasks
docs#dev
web#dev

Note: Common tasks found in turbo.json file - build, lint, check-types, dev


## 4. Learn about Turborepo using. turbo.json file

{
  "$schema": "https://turborepo.com/schema.json",
  "ui": "tui",                                        ------> (Optional) Custom Command line interface with two tabs 
  "tasks": {
    "build": { 
      "dependsOn": ["^build"],                        ------> Run build script of dependecies first 
      "inputs": ["$TURBO_DEFAULT$", ".env*"],         ------> If these values change, then application rebuilds
      "outputs": [".next/**", "!.next/cache/**"],     ------> Cachin inclusions and exclusions
      "env": ["DATABASE_URL"]
    },
    "lint": {
      "dependsOn": ["^lint"]
    },
    "check-types": {
      "dependsOn": ["^check-types"]
    },
    "dev": {
      "cache": false,
      "persistent": true
    },
    "db:generate": {
      "cache": false
    },
    "db:migrate": {
      "cache": false,
      "persistent": true
    },
    "db:deploy": {
      "cache": false
    }
  }
}


## 5. (Optional) Git command to download a branch of a remote repo
git clone --single-branch -b <completed> <https://github.com/safak/e-commerce-ui.git>


## 6. 


























































