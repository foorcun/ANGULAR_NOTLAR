# mimari

src > app

## silinecekler

app.component.scss <br>
app.component.spec.ts <br>

```.sh
del app.component.scss
del app.component.spec.ts
```

not: app.component.ts > styleUrls: comment etmeyi unutma.

```.sh
@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  // styleUrls: ['./app.component.scss']
})
```

### html file dursun icini tamamen sil. Typescript geregi templateUrl verilmek zorunda die tutuyorz

app.component.html <br>

sadece bu kalsin

```.sh
<router-outlet></router-outlet>
```

## create parent folders

src > app

```.sh
@echo off
mkdir core
echo.|set /p=" " > core/.gitkeep
mkdir features
echo.|set /p=" " > features/.gitkeep
mkdir layouts
echo.|set /p=" " > layouts/.gitkeep
mkdir pages
echo.|set /p=" " > pages/.gitkeep
mkdir shared
echo.|set /p=" " > shared/.gitkeep
mkdir store
echo.|set /p=" " > store/.gitkeep
@echo on
```

sonra path olarak root a geri cikmayi unutma.

```.sh
cd..
cd..
```

# change prefix

angular.json > prefix: > ngs yapmis adam

## @ ile scope-name yapmak

[link](https://stackoverflow.com/questions/37372816/what-does-symbol-mean-in-import-component-from-angular-core-statem)

tsconfig.js > compilerOptions: >

```.sh
 "baseUrl": ".",
 "paths": {
      "@core/*": ["src/app/core/*"],
      "@features/*": ["src/app/features/*"],
      "@layouts/*": ["src/app/layouts/*"],
      "@pages/*": ["src/app/pages/*"],
      "@shared/*": ["src/app/shared/*"],
      "@store/*": ["src/app/store/*"]
    }
```

minimal code:

```.sh
 "baseUrl": ".",
    "paths": {
      "@pages/*": ["src/app/pages/*"],
    }
```

# router

[youtube](https://www.youtube.com/watch?v=Np3ULAMqwNo)
video 7 - eski angular egitimi

app.component.html icine sunu koy:

```.sh
<router-outlet></router-outlet>
```
