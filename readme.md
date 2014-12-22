gulp-tsb
===============

## Information

A gulp plugin for incremental TypeScript compilation. This plugin uses reverse dependencies of import-require statements and only works well with external modules (amd, commonjs).

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