
# create page

page ler de aslinda component tir. <br>
in the pages folder

```.sh
ng g c campaigns-page
```

ya da root ayken

```.sh
ng g c pages/campaigns-page
```

## silinecek 

ts haric hepsini sil <br>

not: pages > campaigns-page > campaigns-page.component.ts > <br>
-templateUrl:, styleUrls: bunlari comment yap
-template: ekle. misal: template:"\<p>i am campaigns page template<\/p>"
```.sh
@Component({
  selector: 'app-campaigns-page',
  // templateUrl: './campaigns-page.component.html',
  template:"<p>i am campaigns page template</p>"
  // styleUrls: ['./campaigns-page.component.scss']
})
```


## index.ts ekle

```.sh
echo export * from './campaigns-page.component'; > index.ts
```
ya da roottayken

```.sh
echo export * from './campaigns-page.component'; > src/app/pages/campaigns-page/index.ts
```

not: index kullanirsak kisa olan, kullanmazsak uzun olan sekilde import ediyor <br>
ornek import
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

[youtube](https://www.youtube.com/watch?v=Np3ULAMqwNo)
video 7 - eski angular egitimi

app.component.html icine sunu koy:
```.sh
<router-outlet></router-outlet>
```