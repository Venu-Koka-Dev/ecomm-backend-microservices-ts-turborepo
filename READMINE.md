# Tech Stack
1. Monorepo - NX, Turborepo (maintained by Vercel)
2. NextJS
3. Node-Express
4. TypeScript

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
# Setup
1. Create a folder: ecomm
   
2. Create a Turborepo project
pnpm dlx create-turbo@latest

Where: . -> Package manager: pnpm -> Installs with teo example projects in it

Folder Structure of a Turborepo project:
apps/              -> Contains applications like frontend, backend, services etc
packages/          -> Contains share tools like React components, utils, types, configurations etc
node_modules/
package.json
turbo.json
README.md
.gitignore
.npmrc

3. Install turbo
pnpm add turbo -w
turbo dev

4. 


