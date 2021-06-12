# Angular create package module

### content


### to create new app and cd to project.
```bash
$ ng new <app name> --createApplication=false
$ cd <app name>
```

### to create a library.
```bash
$ ng g library <library name>
```

### ReadMe and package.json .
above cmd create procject/your-library-name. Inside can change "README.md" and "package.json"
```javascript
{
  "name": "ng-samadhi-lib", /*you can change library hare */
  "version": "0.0.1",
  "peerDependencies": {
    "@angular/common": "^10.0.14",
    "@angular/core": "^10.0.14"
  },
  "dependencies": {
    "tslib": "^2.0.0"
  },
  "description": "samadhi test lib",
  "author": {
    "name":"samadhi laksahan",
    "url":"https://mutx.ru"
  },
  "keywords": ["test library"]
}
```

following file "public -api" is very important for add new components.
```bash
\projects\ng-samadhi-lib\src\public-api.ts
```
```javascript
export * from './lib/ng-samadhi-lib.service';
export * from './lib/ng-samadhi-lib.component';
export * from './lib/ng-samadhi-lib.module';
```
####  build library
it will create "dist" folder.    
 "library name" is not package.json name value.
```bash
$ ng build
$ ng build <library name> --prod
```

#### test package
run build package on application.(in project directory)    
```bash
$ ng g application <app-name>
```
run app when we have multiple app applications.   
```bash
$ ng serve <app-name>
```


#### login to npmjs.    
1) go to "dist/your-library-name"
2) enter your credentials
```bash
$ npm login
```

#### publish package.    
```bash
$ npm publish
```

#### update package.   
change package.json version to upper && re-publish it.    
```bash
$ npm publish
```
### encapsulation
use "encapsulation" property when styles, class in components.(not in separate file)
```javascript
@Component({
  selector: 'ng-upload-image',
  template: `
    <p>
      ng-upload-image works!
    </p>
    `,
  styles: [
    `.mark{background-color: red}`
  ],
  encapsulation:ViewEncapsulation.None
})
export class NgUploadImageComponent implements OnInit {

  constructor() { }

  ngOnInit(): void {
  }

}
```
