# gulp-assemble

> Gulp plugin for Assemble.

## Warning

Since gulp-assemble is using the [v0.6.0-alpha branch of Assemble](https://github.com/assemble/assemble/tree/v0.6.0), this is not ready to be used unless you're willing to deal with daily changes, broken code, and lack of documentation.

## Install

Install with [npm](npmjs.org)

```bash
npm i assemble/gulp-assemble
```

Next, cd into the project and run `npm install` to install dependencies.

## Usage

Example **gulpfile.js** with gulp-assemble and [gulp-htmlmin](https://github.com/jonschlinkert/gulp-htmlmin):

```javascript
var gulp = require('gulp');
var htmlmin = require('gulp-htmlmin');
var assemble = require('gulp-assemble');

gulp.task('assemble', function () {
  gulp.src('pages/*.hbs')
    .pipe(assemble({layout: 'default'}))
    .pipe(htmlmin({collapseWhitespace: true}))
    .pipe(gulp.dest('_gh_pages/'));
});

gulp.task('default', ['assemble']);
```

## Author

**Brian Woodward**
 
+ [github/assemble](https://github.com/assemble)
+ [twitter/assemble](http://twitter.com/assemble) 

## License

Copyright (c) 2015 Brian Woodward
Released under the MIT license