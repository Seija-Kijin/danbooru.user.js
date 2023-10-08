# danbooru-blacklist2

Advanced blacklist rule grammar for Danbooru.

## Installation

* Install [Tampermonkey](https://tampermonkey.net/) extension, it's available for Chrome, Microsoft Edge, Safari, Opera Next, and Firefox.
* Download the script: https://github.com/hdk5/danbooru-blacklist2/raw/master/dist/danbooru-blacklist2.user.js
* An installation prompt will appear. Accept the installation.

## Supported syntax

* simple tags
    * `blonde_hair`

* `and` expressions
    * `blonde_hair blue_eyes`
    * `blonde_hair and blue_eyes`

* `or` expressions
    * `blonde_hair or blue_eyes`

* `not` expressions
    * `-blonde_hair`

* wildcard expressions
    * `*_(cosplay)`

* parentheses
    * `-(blonde_hair blue_eyes)`
    * `(blonde_hair blue_eyes) or (red_hair green_eyes)`

* `rating` metatag
    * `rating:g`
    * `rating:s`
    * `rating:q`
    * `rating:e`

* `score` metatag
    * `score:>50`
    * `score:50`
    * `score:<50`

* `uploaderid` metatag
    * `uploaderid:748553`

* `is` metatag
    * `is:pending`
    * `is:flagged`
    * `is:deleted`
    * `is:banned`

* `has` metatag
    * `has:parent`
    * `has:children`

## Unsupported syntax

* Legacy disjunctive operator
    * `~blonde_hair ~blue_eyes`
    * Use `blonde_hair or blue_eyes`

* `>=`, `<=`, `..` for `score` metatag
    * `score:>=50`, `score:<=50`, `score:50..`, `score:..50`, `score:50..100`
    * Use `score:>49`, `score:<51`, `score:>49 and score:<101`

* `,` for `rating` metatag
    * `rating:q,e`
    * Use `rating:q or rating:e`
