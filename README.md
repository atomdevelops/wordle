# React Wordle

This is a **clone** of the everso popular word guessing game known as Wordle.

**[You can view the demo here!](https://wordle.atomdev.cf)**

### Technologies used
- [React](https://reactjs.org)
- [TypeScript](https://typescriptlang.org)
- [TailwindCSS](https://tailwindcss.com)

## Build and run the project

### Local
Clone this GitHub repository and execute the following commands:
```bash
$> cd react-wordle # cd into the cloned repository
$> npm install # install the required dependencies
$> npm start # start the project into development mode
```

### To use inside a docker container
This project was dockerized to allow you to run inside a docker container.

#### Development
```bash
$> docker build -t reactle:dev -f docker/Dockerfile .
$> docker run -d -p 3000:3000 --name -reactle-dev reactle:dev
```
Now, open http://localhost:3000 in your browser.

#### Production
```bash
$> docker build- --target=prod -t reactle:prod -f docker/Dockerfile .
$> docker run -d -p 80:8080 --name reactle-prod reactle:prod
```

Now, open http://localhost in your browser.


## Frequently Asked Questions (FAQ)

## How do I change the length of each guess?
- Update the `MAX_WORD_LENGtH` variable in `src/constants/settings.ts` to your new desired length.
- Update the `WORDS` arrayin `src/constasnts/wordlist.ts` to only include words of the new length.
- Update the `VALID_GUESSES` array in `src/constants/validGuesses.ts` arrays to only include words of the new length.

## How do I create this in other languages?
- In `.env`:
  - Update the title and the description
  - Set the `REACT_APP_LOCALE_STRING` to your locale
- In `public/index.html`:
  - Update the "You need to install JavaScript" message
  - Ypdate the language attribute in the HTML tag
  - If the language is written right-to-left, add `dir="rtl"` to the HTML tag
- Update the name and short name in `public/manifest.json`
- Update the strings in `src/constants/strings.ts`
- Add all of the five letter words in the language to `src/constants/validGuesses.ts`, replacing the English words.
- Update the "Settings" modal in `src/components/modals/SettingsModal.tsx`
- Update the "Info" modal in `src/components/modals/InfoModal.tsx`
- If the language has letters that are not present in English, update the keyboard in `src/components/keyboard/Keyboard.tsx`
- If the language is written right-to-left, prepend `\u202E` (the unicode right-to-left override character) to return the statement of the inner function in `generateEmojiGrid` in `src/lib/share.ts`

## How do I add usage tracking?
This repository includes support for Google Analytics or [Plausible Analytics](https://plausible.io/) out of the box, but, this is disabled by default.

To enable Google Analytics:
- Create a Google Analytics 4 property and obtain the measurement ID (of the format `G-XXXXXXXXXX`)
- In `.env`, add `REACT_APP_GOOGLE_MEASUREMENT_ID=XXXXXXXXXX`

Keep in mind that your region might have legislation about obtaining a user's consent before enabling trackers. This is up to downstream repos to implement.

To enable Plausable Analytics:
- Create a new website with Plausable Analytics with a given domain, e.g. `example.app`
- In `.env`, add `REACT_APP_PLAUSABLE_DOMAIN=example.app`

## The End
This app was made with :heart: by Atom.
View my other works [here](https://atomdev.cf).
