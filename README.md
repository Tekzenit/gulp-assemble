# gulp-assemble [![NPM version](https://badge.fury.io/js/gulp-assemble.png)](http://badge.fury.io/js/gulp-assemble)  [![Build Status](https://travis-ci.org/assemble/gulp-assemble.png)](https://travis-ci.org/assemble/gulp-assemble)

> [Assemble](https://github.com/assemble/assemble) plugin for Gulp

## WARNING!!!

Since gulp-assemble is using the [v0.5.0-alpha branch of Assemble](https://github.com/assemble/assemble/tree/v0.5.0), this is not ready to be used unless you're willing to deal with daily changes, broken code, and lack of documentation.
Also, you may need to install the v0.6.0 branch of handlebars-helpers:

## Install (alpha code, at your own risk)

```
npm install git://github.com/assemble/gulp-assemble.git
npm install git://github.com/assemble/handlebars-helpers.git#v0.6.0
```

## Usage

Here is an example of a **gulpfile.js** 

```javascript
var gulp = require('gulp'),
    assemble = require('gulp-assemble');

var paths = {
        sources: {
            layouts: 'src/templates/layouts/',
            partials: 'src/templates/partials/*.hbs',
            pages: 'src/templates/pages/*.hbs',
            data: 'src/data/*.json'
        },
        build: {
            www: 'dist/www/'
        }
    };

gulp.task('assemble', function(){
    var options = {
        layoutdir: paths.sources.layouts,
        partials: paths.sources.partials,
        data: paths.sources.data,
        log: {
            level: 'info' // verbose, debug, info, warning, error, critical
        }
    }
    gulp.src(paths.sources.pages)
        .pipe(assemble('my-task', options))
        .pipe(gulp.dest(paths.build.www));
});

gulp.task('default', function() {
});
```

## Authors

**Brian Woodward**

+ [github/doowb](https://github.com/doowb)
+ [twitter/doowb](http://twitter.com/jonschlinkert)


## Release History

_(Nothing yet)_


## License

Copyright (c) 2014 Brian Woodward, contributors.
Released under the MIT license
