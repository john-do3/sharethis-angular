# Sharethis Share Buttons - Angular

## How to use it
- Install the library using ... // TODO: Add library to npm when ready
- Add the library module to your imports
  ```js
    import { BrowserModule } from '@angular/platform-browser';
    import { NgModule } from '@angular/core';

    import { AppComponent } from './app.component';
    import { SharethisAngularModule } from 'sharethis-angular';

    @NgModule({
      declarations: [AppComponent],
      imports: [BrowserModule, SharethisAngularModule],
      providers: [],
      bootstrap: [AppComponent],
    })
    export class AppModule {}
  ```
- To the component where you wanna use the library components you need to pass a config object to the desired share buttons selector, which can be: `lib-inline-share-buttons`, `lib-inline-follow-buttons`, `lib-sticky-share-buttons`, `lib-inline-reaction-buttons`. e.i: the html markup would be:
  ```js
    <lib-inline-share-buttons [config]="inlineShareButtonsConfig">
  ```
  While the component file would declare `inlineShareButtonsConfig` like so:
    ```js
      import { Component } from '@angular/core';

      const InlineShareButtonsConfig : InlineShareButtonsConfig = {
        alignment: 'center', // alignment of buttons (left, center, right)
        color: 'social', // set the color of buttons (social, white)
        enabled: true, // show/hide buttons (true, false)
        font_size: 16, // font size for the buttons
        labels: 'cta', // button labels (cta, counts, null)
        language: 'en', // which language to use (see LANGUAGES)
        networks: [
          // which networks to include (see SHARING NETWORKS)
          'whatsapp',
          'linkedin',
          'messenger',
          'facebook',
          'twitter',
        ],
        padding: 12, // padding within buttons (INTEGER)
        radius: 4, // the corner radius on each button (INTEGER)
        show_total: true,
        size: 40, // the size of each button (INTEGER)

        // OPTIONAL PARAMETERS
        url: 'https://www.sharethis.com', // (defaults to current url)
        image: 'https://bit.ly/2CMhCMC', // (defaults to og:image or twitter:image)
        description: 'custom text', // (defaults to og:description or twitter:description)
        title: 'custom title', // (defaults to og:title or twitter:title)
        message: 'custom email text', // (only for email sharing)
        subject: 'custom email subject', // (only for email sharing)
        username: 'custom twitter handle', // (only for twitter sharing)
      }

      @Component({
        selector: 'app-root',
        templateUrl: '<lib-inline-share-buttons [config]="inlineShareButtonsConfig">',
        styleUrls: ['./app.component.css'],
      })
      export class AppComponent {
        inlineShareButtonsConfig = InlineShareButtonsConfig;
      }
    ```

## Development server

- Run `ng build --project=sharethis-angular` to build the library
- Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files on the demo app, if you change the library make sure you re-build it to get the latest updates.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory. Use the `--prod` flag for a production build.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via [Protractor](http://www.protractortest.org/).

