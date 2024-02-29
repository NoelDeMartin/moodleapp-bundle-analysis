# Moodle App Bundle Analysis

This repo hosts an analysis of the [Moodle App](https://github.com/moodlehq/moodleapp) generated using the [webpack-bundle-analyzer](https://www.npmjs.com/package/webpack-bundle-analyzer) plugin.

You can view it online here: [noeldemartin.github.io/moodleapp-bundle-analysis](https://noeldemartin.github.io/moodleapp-bundle-analysis)

## Instructions

Here's the steps you can follow to generate this report yourself:

1. Install `webpack-bundle-analyzer`:

```sh
npm install webpack-bundle-analyzer --save-dev
```

2. Add it to `webpack.config.js`:

```js
const BundleAnalyzerPlugin = require('webpack-bundle-analyzer').BundleAnalyzerPlugin;

// Append to the plugins array.
config.plugins.push(new BundleAnalyzerPlugin({
    analyzerMode: 'static',
    generateStatsFile: true,
}));
```

3. Generate the report (you will find it on `www/report.html`):

```sh
NODE_OPTIONS=--max-old-space-size=8192 npx ng build --configuration production --stats-json
```
