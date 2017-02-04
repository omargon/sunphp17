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
* Same Origin Fallacy "It's mine! All mine!"
* Libraries vs internal methods - Like filter_var or Respect/Validation
* Solution: Assess validation needs across application (do they repeat?) Remember the threat model or inputs. Fail fast.

## Validation: Sanitize
* Don't use as a replacement for input validation
* The more assumptions you make, the higher the risk factor.
* Consider output contexts too (HTML, JS, XML...)
* Solution: Validate first, then sanitize. Dont try to sanitize it.

## Templating: PHP
* PHP i not a templating language.. no really.
* Largest refactor point in most legacy applications.
* Using methods to escape output? That's templating.
* Evaluate options: template it all vs spot checks.

## Templating: Manual
* Prone to mistakes
* Hard to manage effectively
* Beware copy and paste all the things 
* Move slowly, replace most used first (based on logging)

## Templating: Special Output
* HTML is not the only context
* Javascript s, CSS, HTML attribute, plain-text, log output
* HTML - htmlspecialchars
* CSS - Replace with &#[num]
* Javascript - Replace with \x
* URL - url encode

## Access Control: Now
* Determine current controls (Auth*)
* Determine converage of controls
* Look for over-engineering

## Access Control: Credentials
* Look for hard-coded values - username, token, paswords
* Extract the values and protect
* Think about protection levels
* External tool, external file, external service

## Access Control: Endpoints
* Public, Private, Conditional
* Different protection levels
* Start with most used
* Proect at different levels - router, endpoint, server - defense in depth
* See if there's a simpler way

## Access Control: User
* Determine user types
* Create a grid of types and endpoints
* Features == users?
* Admminstrative vs Users

## Adding New Control
* Can tools be consolidated (or removed)?
* Determine missing controls
* Are tehre any 3rd part tools/libraries you can reuse?
* Simple is good, but sometimes complex is needed
* Are there interfaces with other systems

## Adding New Controls: Examples
* CSRF tokens injeted automatically on render
* Encrytion of data via libraries (ex: libsodium, defuse-php)
* Implementing a templating library
* Accec control types
	* Access Control list (ACL)
	* Role-based access control (RBAC)
	* Propery based access-control
	* Multi-factor authentication

## Changing Dev Process
* Hardest part in the whole process
* New code needs security guidance
* Manual code review
* Integrate tools and service\
* Scanners, 3rd part services, Pentesting, Bug Bounty
* Refactor bite-size pieces, related to curent development
* Build a culture of security