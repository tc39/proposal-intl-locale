## Intl.Locale API Specification [draft]

### Status

__Stage 0__

Implementation Progress

 * Polyfill: https://github.com/zbraniecki/Intl.js/tree/intllocale

Backpointers

* https://github.com/tc39/ecma402/issues/106

Spec

* https://zbraniecki.github.io/proposal-intl-locale/

### Authors

 * Zibi Braniecki (@zbraniecki)

### Reviewers

TBD

### Prior Art


### Usage

```javascript
let loc = new Intl.Locale("pl-hc-h12", {
  calendar: 'gregory'
});
console.log(loc.locale); // "pl"
console.log(loc.hourCycle); // "h12"
console.log(loc.calendar); // "gregory"
console.log(loc.toString()); // "pl-ca-gregory-hc-h12"
```

### Render Spec

```bash
npm install
npm run build
open index.html
```
