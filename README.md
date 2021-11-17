# ESN Dictionary

Ever wondered what all those abbreviations and phrases used in ESN mean? Explore the ESNdictionary!

## Adding more entries

Update the GoogleSheets from where this app pulls data.

**Note:** it is being discussed to store all the data in this repo for easier management. If this is done, we will explain here the procedure

## Developing

Once you've cloned the repository with git and installed dependencies with `npm install`, start a development server:

```bash
npm run dev

# or start the server and open the app in a new browser tab
npm run dev -- --open
```

## Building

```bash
npm run build
```

## Deploying a new version

Either run `npm run deploy` and this will build and deploy a new version in GitHub Pages

Otherwise, any merge or commit into master will trigger a GitHub Action and deploy the code for you!
