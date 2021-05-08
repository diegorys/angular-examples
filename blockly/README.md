# Blocky

- [ngx-blockly](https://www.npmjs.com/package/ngx-blockly)

```
ng new blockly
```
- Would you like to add Angular routing? N
- Which stylesheet format would you like to use? (Use arrow keys) SCSS
```
npm install --save ngx-blockly
```
- En angular.json
```
"scripts": [
    "node_modules/ngx-blockly/scripts/blockly/blockly_compressed.js",
    "node_modules/ngx-blockly/scripts/blockly/blocks_compressed.js",
    "node_modules/ngx-blockly/scripts/blockly/python_compressed.js",
    "node_modules/ngx-blockly/scripts/blockly/msg/js/en.js",
]
```
- En app.module.ts
```
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';

import { AppComponent } from './app.component';
import { NgxBlocklyModule } from 'ngx-blockly';

@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule,
    NgxBlocklyModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```
- En app.component.ts
```
import { Component } from '@angular/core';
import { NgxBlocklyConfig } from 'ngx-blockly';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.scss']
})
export class AppComponent {
  public config: NgxBlocklyConfig = {
    toolbox: '<xml id="toolbox" style="display: none">' +
      '<block type="controls_if"></block>' +
      '<block type="controls_repeat_ext"></block>' +
      '<block type="logic_compare"></block>' +
      '<block type="math_number"></block>' +
      '<block type="math_arithmetic"></block>' +
      '<block type="text"></block>' +
      '<block type="text_print"></block>' +
      '</xml>',
    scrollbars: true,
    trashcan: true
  };
}
```
- En app.component.html
```
<h1>Ejemplo Angular y Blockly</h1>
<p><a href="http://diegorys.es">diegorys</a></p>
<ngx-blockly [config]="config"></ngx-blockly>
```
- En app.component.scss
```
ngx-blockly {
  position: absolute;
  width: calc(100% - 1em);
  height: calc(100vh - 8em);
}
```
- Lanzamos la aplicación
```
npm start
```
- Abrimos en el navegador
```
http://localhost:4200/
```