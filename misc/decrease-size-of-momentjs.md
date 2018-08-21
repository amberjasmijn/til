# Decrease size of Moment.js in your project

After analyzing my JavaScript bundle with the Webpack Bundle Analyzer, it turned out that moment -eventhough it wasn't used yet, was the largest package inside the bundle, compared to `react`, `react-dom`, `immutable`, `i18next`, etc. 

This is because all the locales are included by default, which is not necessary most of the time. 
To disable it, you can ignore it by adding

```
  plugins: [
    new BundleAnalyzerPlugin(),
    new Webpack.IgnorePlugin(/^\.\/locale$/, /moment$/)
  ]
```

to your Webpack configuration. 

Reference: [How to optimize Moment.js with Webpack]https://github.com/jmblog/how-to-optimize-momentjs-with-webpack