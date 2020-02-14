# `Intl.Locale` API Specification [draft]

## Overview

### Motivation

The JavaScript Intl library (ECMA 402) has used strings to identify locales since the beginning. This works well for many simple cases, and is lightweight and user-friendly. ICU uses a Locale class instead. Defining a Locale class allows the following:
- Parsing and manipulating the language, region and script of a locale
- Reading or writing the Unicode extension tags in a locale
- A serializable, standard format to store user locale preferences for use in Intl APIs rather than a combination of language and options bag.
- In follow-on proposals, a Locale class can be used for an interface to get at various kinds of locale data, including likely subtags, first day of the week, various display names, etc.

Intl.Locale has a toString method which represents the complete contents of the locale. This method allows Locale instances to be provided as an argument to existing Intl constructors, serialized in JSON, or any other context where an exact string representation is useful.

Intl.Locale [is proposed](https://github.com/whatwg/html/pull/3046) to be the class that HTML uses to expose the current locale to the Web. Currently, HTML supports only `navigator.languages`, but with `navigator.locales`, an Array of Intl.Locale instances, browsers may expose user preferences for calendar, numbering system, and more to Progressive Web applications.

### Usage examples

The following example shows how to use `Intl.Locale`

```javascript
let loc = new Intl.Locale("pl-u-hc-h12", {
  calendar: 'gregory'
});
console.log(loc.language); // "pl"
console.log(loc.hourCycle); // "h12"
console.log(loc.calendar); // "gregory"
console.log(loc.toString()); // "pl-u-ca-gregory-hc-h12"
```

### Implementation Status

__Stage 4__

Implementation Progress

 * [Shipping in Chrome 74 / V8 v7.4](https://v8.dev/blog/v8-release-74#intl.locale)
 * [Shipping behind the flag in Firefox 70](https://bugzilla.mozilla.org/show_bug.cgi?id=1433303)
 * Polyfill: https://github.com/zbraniecki/Intl.js/tree/intllocale

Backpointers

* https://github.com/tc39/ecma402/issues/106


### Authors

 - Zibi Braniecki (@zbraniecki)
 - Daniel Ehrenberg (@littledan)

### Reviewers

TBD

## Proposal

### Spec

You can view the [spec text](spec.html) or rendered as [HTML](https://tc39.github.io/proposal-intl-locale/).

#### Prior Art

* [Java Locale class](https://docs.oracle.com/javase/7/docs/api/java/util/Locale.html)
* [ICU4J Locale class](http://icu-project.org/apiref/icu4j/com/ibm/icu/util/ULocale.html)
* [ICU4C Locale class](http://icu-project.org/apiref/icu4c/classicu_1_1Locale.html)



## Development

### Render Spec

```bash
npm install
npm run build
open index.html
```
