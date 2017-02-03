# Debugging Effectively

## Importanct of debugging

* Gaining experience with code and tools
* Develop a "sixth sense" or intuition

## Debugging process

### Early Developers
* Try the usual steps
	* bin/console cache:clear
	* composer install
	* chmod -R 777 * (Not accepted)
* Ask somebody else
	* Co-worker
	* Google
	* StackOverflow post
* Fault into XY Problem
	* I want to solve problem X
	* instead the jump into solution "Y might work"
	* How can I do Y
* I don't know why
	* For some reason
	* Doesn't make sense

## Sistematic Approach
### Gather information
* Expected behavior vs. actual behavior
* Error messages
* Stack traces
* Screenshots
* Browser & OS
* Date & time
* Log entries

### Replicate the issue
* Be able to replicate with 100% certainty

### Identify the culprit
* Be methodical
* Make no assumptions
* Understand the bug

### Fix it & re-test
* atttempt to replicat again
* Avoid XY problem
* No temporrary workarounds
	* Add technical debt
	* May intrduce other issues
	* Never get replaced with true solutions

### Mitigate future occurrences
* Add an automated test
* Share your knowledge
	* Project documentation
	* Blog post
	* Stackoverflow
* Submit patch upstream

## Long term results
* Gain experience
* learn how the system works
* Build heuristics
* Boost confidence

## Tools and techniques
### Integrated Development Environment
* Minimum features:
	* Syntax highlights
	* Auto-completion
	* Fast code navigation
	* Debugger
### Interactive Debugger
* Pause code execution
	* Breakpoints
	* Conditional breakpoints
* Step through execturion
* Examples

### Techniques
#### Trace backwards from know issue
* Use a debugger
* Identify source of error
* Establish context
* Work backwards

#### Trace forwards
* Opposite diretion
* Problematic line isn't know
* Use debugger or logging

#### Divide & conquer
* Identify differnt code settings
* Set breakoints at the boundaries

### Use totols
* Variable dumps
	* var_dump()
	* kint()
	* file_put_contents()
* Debug toolbars
* Console Utilities

### Performance Prfiling
* Identify slowness
	* Bottlenecks
	* Resource hogs
	* Inefficient code
* Tools
	* Blackfire
	* New relic
	* xhprof

### git bisect	

### netcat
* nc -vz localhost 80

### Curl
* Curl -I https://google.com

### strace

## Get help
* RTFM / RTFD -> Read The "Fantastic Manual/Documentation"
* Project forms or issue queue
* StackOverflow, IRC, etc.
* Ask a colleague
	* Expert in the area
	* Senior developer 
* Rubber ducking

## Take a break
* Clear your mindl start fresh
* Forget invalid assumptions
* Recharge your batteries
* Let your subconscious work on it

## Four things to walk way with
* Computers aren't random and neither are bugs
* Persistence will always pay off
