# gulp-mc-inliner
Gulp plugin for inlining CSS throught MailChimps Inliner API3

[![NPM](https://nodei.co/npm/gulp-mc-inliner.png)](https://npmjs.org/package/gulp-mc-inliner)

## Usage

```shell
npm install gulp-mc-inliner --save-dev
```

Create `mailchimp.json` file in the `config` folder and add your MailChimp API key.

```javascript
{
  "APIKEY": "your key goes here"
}
```

Require both in your `gulpfile.js`:

```javascript
var inline = require('gulp-mc-inliner');
var config = require('config/mailchimp');

gulp.task('inliner', function() {
  gulp.src('src/*.html')
    .pipe(inliner(config.APIKEY))
    .pipe(gulp.dest('email/template'));
});
```

## API

### inliner(key, strip)

#### key
Type: `String`

MailChimp API Key. Create a API key from your MailChimp Account.

#### stripCSS
Type: `boolean`
Default: `false`

Boolean value indicating to the MailChimp API whether to strip CSS from the head tag.

This gulp plugin is a rewite of https://github.com/jayzawrotny/gulp-mc-inline-css with added option to specify whether or not to strip style tags from the head tag.