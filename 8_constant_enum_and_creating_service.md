# create

src > app > shared > constants > path-constants.enum.ts

```.sh
export enum PathConstants{
    DALECHALL_WORDS_LIST_3000_JSON = "assets/Dale-Chall_Words_List_3000.json",
    DALECHALL_WORDS_LIST_3000_TEXT = "assets/Dale-Chall_Words_List_3000.txt",
}
```


# import edilmesi

```.sh
import {PathConstants} from "./shared/constants/path-constants.enum"
```

## kullanimi

```.sh
PathConstants.DALECHALL_WORDS_LIST_3000_JSON
```


# creating service

```.sh
ng g s core/utils/data
```
## reading File with service

```.sh
// data.service.ts
import { Injectable } from '@angular/core';
import { HttpClient } from '@angular/common/http';
import { Observable } from 'rxjs';

@Injectable({
  providedIn: 'root',
})
export class DataService {
  // private filePath = '../../../assets/Dale-Chall_Words_List_3000.json'; // Adjust the path accordingly
  // private filePath2 = '../../../assets/Dale-Chall_Words_List_3000.txt'; // Adjust the path accordingly

  constructor(private http: HttpClient) {}

  getData(path: string): Observable<any> {
    return this.http.get<any>(path);
  }

  getTextData(path: string) : Observable<string>{
    // return this.http.get(this.filePath2,{responseType: 'text'})
    return this.http.get(path,{responseType: 'text'})
  }
}
```

## injection service

```.sh
  constructor(private dataService: DataService){
```