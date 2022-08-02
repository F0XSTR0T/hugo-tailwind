# hugo-tailwind

### Use Tailwind CSS V3 on a Hugo project


## Create a new site with HUGO GO

```
hugo new site *NomDuSIte* --format json
```


## Add Packages

```
npm install -D tailwindcss prettier prettier-plugin-tailwindcss npm-run-all
```


## TailwindCSS Config

```
npx tailwindcss init
```


## Modify into tailwind.config.js

```
  module.exports = {
  content: ["content/**/*.md", "layouts/**/*.html"],
  theme: {
    extend: {},
  },
  plugins: [],
 };
```

## Create input.css at the root and add the following lines

```
 @tailwind base;
 @tailwind components;
 @tailwind utilities;
```

## Your (root) layouts/index.html should looks like

```
<!DOCTYPE html>
  <html lang="en">
  <head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="output.css" />
    <title>Hello Hugo</title>
  </head>
  <body>
    <div class="text-4xl text-red-700">Hello TailwindCSS</div>
  </body>
</html>

```

## Check and add if needing the "scripts" part

```
{
"scripts": {
  "dev:css": "npx tailwindcss -i input.css -o static/output.css -w",
  "dev:hugo": "hugo server",
  "dev": "run-p dev:*",
  "build:css": "NODE_ENV=production npx tailwindcss -i input.css -o static/output.css -m",
  "build:hugo": "hugo",
  "build": "run-s build:*"
},
"devDependencies": {
  "npm-run-all": "^4.1.5",
  "prettier": "^2.5.1",
  "prettier-plugin-tailwindcss": "^0.1.6",
  "tailwindcss": "^3.0.19"
  }
}
```

## Development Mode
> npm run dev


#source => https://functional.style/hugo/general/tailwind/
