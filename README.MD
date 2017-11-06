# Angular Vertical Timeline  
[![license](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)  
[![npm](https://img.shields.io/npm/v/npm.svg)](https://www.npmjs.com/package/angular-vertical-timeline)

## Branch organization

This repository follows the [Git Flow](https://danielkummer.github.io/git-flow-cheatsheet/) approach.

* `master` is the stable branch with tagged releases
* `develop` is the snapshot branch, it's mostly stable but active development is done on this branch.
* `feature/*` are temporary, working branches that are not supposed to be stable or usable. They are deleted once merged into `develop`

For most uses `master` is the only branch to consider.

## Installation

To install this library, run:

```bash
$ npm install angular-vertical-timeline --save
```
Or:
```bash
yarn add angular-vertical-timeline
```

## Importing

Import `VerticalTimelineModule` into your Angular `AppModule`:

```typescript
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';

import { AppComponent } from './app.component';

// Import the timeline library
import { VerticalTimelineModule } from 'angular-vertical-timeline';

@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule,

    // Specify the timeline as an import
    VerticalTimelineModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

Also import the stylesheet in your `styles.css` 

```css
@import "~angular-vertical-timeline/vertical-timeline.css";
```

## Usage

```html
<!-- In app.component.html -->
<h1>
  Hello Angular!
</h1>

<!-- Add the timeline -->
<vertical-timeline>
  
  <!-- Add some cards to the timeline. It works with *ngFor too -->

  <!-- If no value is passed for the date, the current time is used. -->
  <vertical-timeline-card>
   <h1>Today</h1>
  </vertical-timeline-card>

  <!-- tomorrow = new Date(2017, 9, 20, 14,34); -->    
  <vertical-timeline-card [dateValue]="tomorrow">
    <h1>Tomorrow</h1>
  </vertical-timeline-card>
  
</vertical-timeline>
```

Example result:

![Angular Vertical Timeline](https://image.ibb.co/d4zCam/angular_timeline.png)

## Development

To generate all `*.js`, `*.d.ts` and `*.metadata.json` files in `dist/` folder:

```bash
$ npm run build
```

To lint all `*.ts` files:

```bash
$ npm run lint
```

## License

Apache License 2.0 © [TechGap Italia](mailto:opensource@techgap.it)