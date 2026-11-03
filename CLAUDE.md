# myGainz

Gym tracker web app from a Fall 2022 class project: workout routines, exercise lookup, and progress tracking. React (Create React App), React Router, Tailwind, Firebase Auth and Firestore. The app lives in `mygainz/`; the root only holds the README.

## Commands

Run from `mygainz/`.

| Task | Command | Notes |
| --- | --- | --- |
| Install | `npm ci` | Uses `package-lock.json` |
| Dev server | `npm start` | http://localhost:3000. Serves, but shows the `moment` compile error noted under Build |
| Build | `npm run build` | Output in `mygainz/build/` (gitignored). Fails on `main` as of 2026-11-03: `src/pages/home.js` imports `moment`, which is not in `package.json` |
| Test | `CI=true npm test -- --watchAll=false` | No test files yet, so this exits with "No tests found" |

There is no lint script beyond the CRA ESLint warnings shown during build and dev.

## Layout

- `mygainz/src/pages/`: one file per route (`home`, `exercises`, `programs`, `progress`, `root`)
- `mygainz/src/components/`: shared UI (nav bars, exercise card, routine and its modal)
- `mygainz/src/data/`: static exercise and routine JSON
- `mygainz/src/services/`: Firebase setup (`firebaseConfig.js`) and auth helpers

## Notes

- `firebaseConfig.js` points at the live Firebase project. A Firebase web config is a client identifier, not a secret, but anything you run locally talks to the real Auth and Firestore data.
- The README links a Firebase Hosting site. There is no deploy script, `firebase.json` or CI in this repo, so nothing here ships automatically.
- Verify a change with `npm run build`, then check it in the dev server.
