# install bootstrap

```.sh
npm install bootstrap jquery popper.js --save
```

# open styles.scss

index.html, main.ts, styles.scss.... add that code:

```.sh
@import '~bootstrap/dist/css/bootstrap.min.css';
```

# open angular.json

[link](https://www.youtube.com/watch?v=g9ucAJU0Bb8&ab_channel=CodeHandbook)

projects: > "my-navbar-project": > "architect": > "build": > "styles":

```.sh
            "styles": [
              "src/styles.scss",
              "node_modules/bootstrap/dist/css/bootstrap.min.css"
            ],
```

ayni yerdeki scripts:

```.sh
"scripts": [
              "node_modules/jquery/dist/jquery.min.js",
              "node_modules/popper.js/dist/umd/popper.min.js",
              "node_modules/bootstrap/dist/js/bootstrap.min.js"
            ]
```

not: video da jquery ve popper da ekliyor.
