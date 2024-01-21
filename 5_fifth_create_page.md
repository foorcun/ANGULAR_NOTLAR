# page in point edecegi component da yaratilmis olsun

# create page as routing

```.sh
ng g m pages/login-page --routing
```


# index.ts

```.sh
export * from './login-page.module';
export * from './login-page-routing.module';
```


# app-routing.module.ts - routes i ekle

```.sh
import { NgModule } from '@angular/core';
import { RouterModule, Routes } from '@angular/router';

const routes: Routes = [
  {
    path: '',
    pathMatch: 'full',
    redirectTo: 'login',
  },
  {
    path: 'login',
    loadChildren: () =>
      import('@pages/login-page').then((r) => r.LoginPageRoutingModule),
  },
];

@NgModule({
  imports: [RouterModule.forRoot(routes)],
  exports: [RouterModule],
})
export class AppRoutingModule {}

```

# login-page-routing.module.ts

```.sh
import { NgModule } from '@angular/core';
import { RouterModule, Routes } from '@angular/router';
import { HelloComponent } from '@features/hello';

const routes: Routes = [
  {
    path: '',
    pathMatch: 'full',
    redirectTo: 'hello',
  },
  {
    path: 'hello',
    component: HelloComponent,
  },
];

@NgModule({
  imports: [RouterModule.forChild(routes)],
  exports: [RouterModule],
})
export class LoginPageRoutingModule {}
```

