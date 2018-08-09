# Code splitting in Webpack
JavaScript bundles can get quite large and to increase performance on the front end, splitting your code may help. Webpack 4 has an optimisation option which extract common dependencies to a separate chunk. 

```
    optimization: {
      splitChunks: {
        chunks: 'all'
      }
    }
```

This results in a vendor bundle, next to your main bundle. Most likely the vendor bundle won’t be updated that many times and can be cached by the client, which decreases load times. 