---
title: "Deploy your TypeScript Express App to Vercel (2024)"
datePublished: Thu Jan 18 2024 15:22:52 GMT+0000 (Coordinated Universal Time)
cuid: clrjd2dyz000409lbfrtp09w6
slug: typescript-express-vercel-deploy
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1705589155792/77d6ed7a-36f4-45ee-9b5d-f81a20dd9e46.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1705591362646/11e91787-e27f-466b-8042-3ec6a0ae5c02.jpeg
tags: express, typescript, vercel

---

***Disclaimer: This blog does not discuss express and how to build server logic. This only focuses on deploying the app to Vercel as a Serverless Function.***

### Step 1: Export `app` instead of listening on a certain port.

Export the `app` in ES6 fashion rather than `app.listen()`

***This***

```typescript
export default app;
```

***Instead of***

```typescript
app.listen(PORT, () => {
    console.log("Server listening on port", PORT);
});
```

### Step 2: Create an `api` folder for Vercel and set it up.

Create an `api` folder that has an `index.ts` as follows:

```typescript
import app from '../app';

export default app;
```

This imports the app from your root directory (change the path if you have a different setup) and exports it for Vercel.

### Step 3: Mention the API folder in `tsconfig.json`

Update `tsconfig.json` as follows to track the `api` folder

```typescript
{
  "compilerOptions": {
    "module": "commonjs",
    "esModuleInterop": true,
    "target": "es6",
    "rootDir": "./",
    "outDir": "build",
    "strict": true
  },
  "include": ["./api/*.ts"] // -> this is the line you need to update
}
```

### Step 4: Create the Public folder

Create an empty `Public` folder because Vercel looks for it during deployment. We need to keep it even though no static files are to be served.

Create a `.gitkeep` to track the folder

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705590358609/034a47e9-4255-41b9-956c-f43fadf11a0a.png align="center")

### Step 5: Create `vercel.json` file

The `vercel.json` should look like this

```json
{
    "rewrites": [
        {
            "source": "/(.*)",
            "destination": "/api"
        }
    ]
}
```

This directs any API request received anywhere in the app is redirected to the `/api` folder. The `/api` folder uses the `/api/index.ts` which in turn uses the `app.ts` and on and on and on

### Step 6: Rewrite the Build Command in `package.json`

Vercel handles all the transpilation, so we need to overwrite the `build` command in `package.json`. Create a new script called `vercel-buiild` which prevents the typescript compiler from being invoked and instead acts as a dummy placeholder. The script should look like this.

```json
"vercel-build": "echo hello",
```

### Step 7: Deploy

The app is now deployable and you can do it from the Vercel console by connecting your GitHub account.

If you have Vercel CLI installed you can check it on your local machine using the command

```bash
vercel dev
```

and deploy using

```bash
vercel
```

---

My Code: [https://github.com/High-on-Bugs/typescript-express-vercel-tutorial](https://github.com/High-on-Bugs/typescript-express-vercel-tutorial)

Check this video for a video tutorial:

%[https://www.youtube.com/watch?v=B-T69_VP2Ls] 

---

If you still have any questions/queries you can reach out to me on my [**LinkedIn**](https://www.linkedin.com/in/sbk2k1/) / [**GitHub**](https://github.com/sbk2k1) / [**Twitter**](https://twitter.com/sbk_2k1).

Cheers!