# gulp-mc-inliner [![NPM version][npm-image]][npm-url]
Gulp plugin for inlining CSS throught MailChimps Inliner API3

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
