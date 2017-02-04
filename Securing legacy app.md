# Securing legacy app

* Complexity is the enemy of security
* Refactor for simplicity

## Understand the scope
* Data backend
* Auth
* output business logic
* input

* Work from the outside in general then introduce security
* Identify and document where data changes hands

## Quick Hits: Globals
* Look for global use deeper in code
* In PHP , that's superglobals first
* $\_POST, $\_GET, $\_SERVER, $\_COOKIE, $\_FILES 
* Get rid of these right now: $GLOBALS, $\_REQUEST

## Quick Hits: Unfiltered Data
* Using calues directly, no filtering/validation
* getRequesParam(), Input:get(), _request->qetQuery()
* Danger concatenation
* Injection issues
* Solution: filter_var or filtering/validation libraries

## Quick Hits: Sensitive Logging
* Yser PII, credentials, tokens
* Logs ar output too
* Log servers are often less secured
* Solution: Remove the sensitive information and purge the logs

## Quick Hits: Drop Catch-Alls
* Fallbacks are nice, until they're not
* Be specific, like in routing
* Catch-alls make for sloppy code and difficult to manage dependecies
* Solution: Remove them.

## Quick Hits: Action Splitting
* REST-ey principle:
* GET reads, POST/PUT/DELETE updates
* Never the two (or three... or more?) shall meet
* Take advantage or framework-specifc handling $app->get() requirements.sf_method
* Solutiion: Abstract out the handling by action. Ensure proper protection (CSRF)

## Quick Hits: Input Points
* locating input points (remember your threat model?)
* grep is your best friend (naming conventions)
* Do you really need it or is it just lazy?
* Solution: Avoid user-controllable data sources, use the force...er filter.

## Input Handling: Determine Risk
* Reducing inputs reduces risk
* Examine context(especially mixed)
* Document Risk points (threat model)
* Solution: Maint data via stateful soruces (sessions), all external data is tainted. Never forget.

## Validation: Do you?
* Not a priority, sadly.
* 

