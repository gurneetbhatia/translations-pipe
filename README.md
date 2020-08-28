# Translations Pipe

This is an intermediary program that can be used in conjunction with a client-side application or website (or backend responses) to ease the task of migrating programs to other human languages. By definition, this would also make the program more scalable since you would be able to expand to international markets with the use of native languages more easily.

For now, I am starting off by trying to determine the services that I will use to implement this along with the general architecture. I am considering using Google Sheets, AWS S3 Simple Storage, the Firebase realtime database and Google Cloud Firestore. I will explore each of these options individually and try to find out which would be best for the needs of this program.

Ultimately, once the basic architecture has been setup, I would also consider setting up a client-side web app that would allow the user to define translations on the website itself and provide them an API endpoint they could query for languages.

## Example Usage (intended)

I will briefly discuss here how a user might be able to use this functionality in Angular once they have setup a service connecting to this program and its pipe.
```html
<h1>{{ 'hello-world' | translate: 'EN' }}</h1>
<h1>{{ 'hello-world' | translate: 'HI' }}</h1>
```

If I were to implement this using a NoSQL/JSON structure, this would look something like this:
```json
userid: [
  {
    "hello-world": {
      "EN": "Hello World",
      "HI": "नमस्ते दुनिया"
    }
  }
]
```

The output of the HTML would then be to simplified to look something like:
```html
<h1>Hello World</h1>
<h1>नमस्ते दुनिया</h1>
```
