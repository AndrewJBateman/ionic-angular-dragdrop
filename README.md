# :zap: Ionic Angular Calendar

* App to show an Ionic calendar. This is another great tutorial from [Jameson Saunders of JamiBot, Youtube video 'Ionic 4 Custom Calendar Tutorial'](https://www.youtube.com/watch?v=SYz-tH3XOF8&t=766s).

## :page_facing_up: Table of contents

* [:zap: Ionic Angular Calendar](#zap-ionic-angular-calendar)
  * [:page_facing_up: Table of contents](#page_facing_up-table-of-contents)
  * [:books: General info](#books-general-info)
  * [:camera: Screenshots](#camera-screenshots)
  * [:signal_strength: Technologies](#signal_strength-technologies)
  * [:floppy_disk: Setup](#floppy_disk-setup)
  * [:computer: Code Examples](#computer-code-examples)
  * [:cool: Features](#cool-features)
  * [:clipboard: Status & To-do list](#clipboard-status--to-do-list)
  * [:clap: Inspiration](#clap-inspiration)
  * [:envelope: Contact](#envelope-contact)

## :books: General info

* Uses the [ionic2-calendar](https://www.npmjs.com/package/ionic2-calendar) package to display events input by the user.
* This app is set up to use a Google Firebase backend to store calender entries.

## :camera: Screenshots

![screenshot](./img/calendar.png)

## :signal_strength: Technologies

* [Ionic v5](https://ionicframework.com/)
* [Ionic/angular v4](https://ionicframework.com/)
* [Angular v8](https://angular.io/)
* [ionic2-calendar v0.5.7](https://www.npmjs.com/package/ionic2-calendar)
* [AngularFire2 v5](https://github.com/angular/angularfire/blob/master/docs/ionic/v3.md) for Google Firebase Database connection.

## :floppy_disk: Setup

* Create a Google Firebase database and add access credentials to environment.ts
* To start the server on _localhost://8100_ type: 'ionic serve'
* To start the server on a mobile using Ionic devapp and connected via wifi, type: 'ionic serve --devapp'
* The Ionic DevApp was installed on an Android device from the Google Play app store.

## :computer: Code Examples

* function to add a new event - including start and end time. Title is derived from seconds and is intended to create semi-random data.

```typescript
  addNewEvent() {
    const start = this.selectedDate;
    const end = this.selectedDate;
    end.setMinutes(end.getMinutes() + 60);

    const event = {
      title: 'Event #' + start.getMinutes(),
      startTime: start,
      endTime: end,
      allDay: false
    };

    this.db.collection('events').add(event);
  }
```

## :cool: Features

* Google Firebase storage of calendar events. Data is retrieved from Firebase in the constructor function at the beginning of the page lifecycle.
* Calender date format can be changed using options from the ionic2-calender.

## :clipboard: Status & To-do list

* Status: Working
* To-do: A lot more complexity can be added to this calendar app. The option to change the view from day to week to month would be useful - as shown in the [demo project](https://github.com/twinssbc/Ionic2-Calendar/tree/v5/demo).

## :clap: Inspiration

* [Jameson Saunders of JamiBot, Youtube video 'Ionic 4 Custom Calendar Tutorial'](https://www.youtube.com/watch?v=SYz-tH3XOF8&t=766s)
* [Ionic2-Calendar github repo](https://github.com/twinssbc/Ionic2-Calendar)
* [demo project](https://github.com/twinssbc/Ionic2-Calendar/tree/v5/demo).

## :envelope: Contact

* Repo created by [ABateman](https://www.andrewbateman.org) - you are welcome to [send me a message](https://andrewbateman.org/contact)
