# Decrease size of Moment.js in your project

After analyzing my JavaScript bundle with the Webpack Bundle Analyzer, it turned out that moment -even though it wasn't even used, was the largest package compared to `react`, `react-dom`, `immutable`, `i18next`, etc. 

This is because all the locales are included by default, which isn't necessary most of the time. 
To disable it you use `Webpack.IgnorePlugin` and add

```
  plugins: [
    new Webpack.IgnorePlugin(/^\.\/locale$/, /moment$/)
  ]
```

to your Webpack configuration. 

Reference: [How to optimize Moment.js with Webpack]https://github.com/jmblog/how-to-optimize-momentjs-with-webpack
