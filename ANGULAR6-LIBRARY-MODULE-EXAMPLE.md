
- Angular 6

```bash
npm i -g yarn
ng config -g cli.packageManager yarn
ng new apsara --prefix apsara
```

- Adding new library
```bash
ng g library container --prefix apsara
```

- Create a service in the library

  Add @Injectable annotation in service ts file with "provideIn: root" 
  which allows to provide a service without explicitly registering it in any NgModule.
  
  Why is that useful? It enables such service to be tree-shaken 
  (removed form the production bundle if not used), which is a common 
  scenario in case of services defined in libraries.
  
- Create a component in the library
```bash
ng generate component poster --project=container
```  

- To build library
```bash
ng build container
```

- Use the library
 Its similar like 3rd party library define as dependency in the imports section of app's
 NgModule.
 
- Publish the library
```bash
ng build container --prod
cd dist/container
npm publish
```

- USEFUL LINKS
 - http://www.jsontots.com/
 - https://medium.com/@tomsu/how-to-build-a-library-for-angular-apps-4f9b38b0ed11
