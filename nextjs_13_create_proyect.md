# Create Project Next.Js 13

## Development environment

* ubuntu 22.0.4
* node.js 18.16.0
* npm 9.6.6
* yarn 1.22.19

## Create project

```shell
cd projects/nextjs
npx create-next-app@latest --experimental-app

    name project: <project name>
    typescript: yes
    tailwind css: yes
    use src/: yes
```

## Re-Install package for yarn 

```shell
rm package-lock.json
yarn install
```

## Run the development server

```shell
yarn dev
```

## Remoe unnecessary code

* Modify src/app/page.tsx

```js
export default function Home() {
  return (
    <main>
      Welcome
    </main>
  )
}
```

* Modify src/app/layout.tsx

```js
import './globals.css'

export const metadata = {
  title: '<App Title >',
  description: 'App Description',
}

export default function RootLayout({
  children,
}: {
  children: React.ReactNode
}) {
  return (
    <html lang="en">
      <body>
        {children}
      </body>
    </html>
  )
}
```

* Modify src/app/globals

```js
@tailwind base;
@tailwind components;
@tailwind utilities;

/* body {
  background-color: white;
  color: black|;
}

@media (prefers-color-scheme: dark) {
  body {
    background-color: black;
    color: white;
  }
} */
```

## Start development

### Directory structure

```shell
/src
  /app
    globals.css
    layout.tsx
    page.tsx
    /<module>
      page.jsx
      /components
        /< component >
          < ComponentName.jsx >
        data.js
  /hooks

/public
  /assets
    /images
    /videos
    /icons
```

* < module >: module name, for example: tiktok
* < ComponentName.jsx >: component name, for example: VideoPlayer.jsx
* src/app/< module >/components/data.js: 
Definition of constants used by the components of the module
* src/hooks. Public Hooks
* /public: directory where images and videos should be places


## Deploy on Vercel

```shell
yarn add vercel
yarn build
vercel 
```

```shell
# Next time
yarn build
vercel --prod
```

