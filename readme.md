# gulp-tsb

Fork of [`jrieken/gulp-tsb`](https://github.com/jrieken/gulp-tsb):

- Reset `master` branch to `release/4.0` (previous `master` is available at `release/3.0`)
- Applied <https://github.com/jrieken/gulp-tsb/pull/56>
- Updated `typescript` to `^4.1.3` (to support new `jsx` related config options)

===============

[![Build Status](https://travis-ci.org/jrieken/gulp-tsb.svg?branch=master)](https://travis-ci.org/jrieken/gulp-tsb)

## Information

A gulp plugin for **very fast** TypeScript compilation. This plugin works by
* keeping a compiler alive to improve speed (at the cost of memory)
* always recompiling the smallest set of files possible

## Usage

```javascript

	var tsb = require('gulp-tsb');

	// create and keep compiler
	var compilation = tsb.create({
		target: 'es5',
		module: 'commonjs',
		declaration: false
	});

	gulp.task('build', function() {
		return gulp.src('src/**/*.ts')
			.pipe(compilation()) // <- new compilation
			.pipe(gulp.dest(''));
	});
```

## Options

The options are the same as the standard TypeScript compiler option.