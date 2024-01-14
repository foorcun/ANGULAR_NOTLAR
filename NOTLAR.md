# new project yarat

```.sh
ng new my-navbar-project
```
detaylar drive > Anguler Project CRUD

## new project ilk test
```.sh
npm start
```

## silinecekler
app.component.scss <br>
app.component.spec.ts <br>

### html file dursun icini tamamen sil. Typescript geregi templateUrl verilmek zorunda die tutuyorz
app.component.html <br>



# mimari

## create parent folders
src > app

```.sh
mkdir core
mkdir features
mkdir layouts
mkdir pages
mkdir shared
mkdir store
```

# change prefix
angular.js > prefix > ngs yapmis adam

# create page

in the pages folder

```.sh
ng g c campaigns-page
```

## silinecek 

ts haric hepsini sil

## index.ts ekle

```.sh
echo export * from './login-page.component'; > index.ts
```

not: index kullanirsak kisa olan, kullanmazsak uzun olan sekilde import ediyor

```.sh
import { CampaignsPageComponent } from './pages/campaigns-page';
import { CampaignsPageComponent } from './pages/campaigns-page/campaigns-page.component';
```


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

ornek import code:
```.sh
import { CampaignsPageComponent } from '@pages/campaigns-page';
```

# router

[youtube](https://www.youtube.com/watch?v=Np3ULAMqwNo) <br>
video 7 - eski angular egitimi

app.component.html icine sunu koy:
```.sh
<router-outlet></router-outlet>
```