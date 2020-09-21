# 🧙‍♂️ Monorepo Proof of Concept

Based off of [this blog post](https://josephluck.co.uk/blog/next-typescript-monorepo/) by [Joesph Luck](https://josephluck.co.uk/)

The idea behind this is that each directory (base, siteuno, ...) can use code from other directories despite them being different projects.

## ⚙ Installation

Treat each directory as a seperate [next.js](https://nextjs.org/) project. Run commands such as `yarn` and `yarn dev` from inside those directories, *not* the root directory.

## 📦 Making your own monorepo

1. Duplicate the "siteuno" directory
2. Change name in `new_dir/package.json` to `@mono/new-dir`
3. Add the directory to `./package.json`
4. Start importing from other directories!

## 🔮 How does it work?

The `next.config.js` in each directory will grab any modules with the scope `@mono` and build them. Then you can import files from a given directory, as in the example shown below:

```js
import Header from '@mono/base/components/Header'
```

NB: you can change the `@mono` to something else, such as `@followmsrcodesontwitter` by changing the name value in `./package.json` and then changing it in every `next.config.js` file
