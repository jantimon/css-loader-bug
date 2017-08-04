This repo is just to show an issue with css-loader 0.28.4:

Using a tilde `~` inside a css file causes `Can't resolve '~'` if css-modules feature is activated:

```js
{
  loader: 'css-loader',
  options: {
    modules: true,
  }
},
```

The bug can be reproduced this way:

```bash
npm install
npm run without-modules 
npm run with-modules
```

The first `npm run` will use a webpack config which **does not** use css modules and all will work well.

The secon `npm run` will use a webpack config which **does** use css modules and all will fail.
