const gulp = require('gulp');
const inject = require('gulp-inject');
const wiredep = require('wiredep').stream;
const browserSync = require('browser-sync');

/* injects the files that you create */
gulp.task('inject', function() {
    var sources = gulp.src([                                     // Define the files we'd like to inject
        './app/**/*.module.js',                         // *.module.js files go first
        './app/**/*.js',                                // *.js files come next
        './app/**/*.css'                                // *.css files come next
    ]);

    return gulp.src('./index.html')                            // Read your index.html
        .pipe(inject(sources, { relative: true }))      // Pipe it through gulp-inject
        .pipe(gulp.dest('./'));                         // Write it out to ./
});

/* injects your bower dependencies */
gulp.task('inject:bower', ['inject'], function() {
    return gulp.src('./index.html')                     // Read your index.html
        .pipe(wiredep())                                // Pipe it through wiredep
        .pipe(gulp.dest('./'));                         // Write it out to ./
});

/* watches for changes made to your files */
gulp.task('watch', function() {
    return gulp
        .watch('./app/**/*', ['reload']);               // Watch for any changes in your app folder
                                                        // which will trigger the 'reload' task
});

/* reloads the browser */
gulp.task('reload', function() {
    return browserSync.reload();                        // reloads your app through browser-sync
})

/* starts a browser-sync server */
gulp.task('serve', ['inject:bower', 'watch'], function() {
    return browserSync.init({                           // starts a browser-sync service
        server: './'                                    // serving the ./ directory
    })
});
