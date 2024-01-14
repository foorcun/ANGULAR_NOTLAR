# create page

in the pages folder

```.sh
ng g c campaigns-page
```

yada roottayken

```.sh
ng g c pages/campaigns-page
```

## silinecek

ts haric hepsini sil

## campaigns-page.component.ts ici

```.sh
import { Component } from '@angular/core';

@Component({
  selector: 'ngs-campaigns-page',
  // templateUrl: './campaigns-page.component.html',
  template: `<router-outlet />`,
  // styleUrl: './campaigns-page.component.scss'
})
export class CampaignsPageComponent {}

```

## index.ts ekle

```.sh
echo export * from './campaigns-page.component'; > index.ts
```

not: index kullanirsak kisa olan, kullanmazsak uzun olan sekilde import ediyor

```.sh
import { CampaignsPageComponent } from './pages/campaigns-page';
import { CampaignsPageComponent } from './pages/campaigns-page/campaigns-page.component';
```
