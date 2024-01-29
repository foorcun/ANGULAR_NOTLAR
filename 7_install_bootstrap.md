# install bootstrap

```.sh
npm install bootstrap jquery popper.js --save
```


# open angular.json

[youtube_link](https://www.youtube.com/watch?v=g9ucAJU0Bb8&ab_channel=CodeHandbook)

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


# navbar doc

[doc_link](https://getbootstrap.com/docs/4.0/components/navbar/)


not : hot start ile gelmiyor. server i durdurup yeniden npm start yap.