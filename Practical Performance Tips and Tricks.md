# Practical Performance Tips and Tricks

http://blogs.msdn.microsoft.com/dorischen

## What to measure
### Network Utilization and Limits
* Bandwidth
* Latency

### Power Consumption

Power efficiency can drain your user's battery

* Vsync
* GPU Utilization
* CPU Utilization

### Tools
* F12 Tools
	* Collection of developer tools for working with DOM, Debugging, networking
	* Performance tool
* Task Manager
* Fiddler

## Quickly Respond to Network
 
* Avoid 3xx redirection
* Maximize Concurrent Connections
* Reuse Connetions
	* HTTP Response
		* Connection: close - Keep connection open

## Minimize Bytes Downloaded
* Cache Dynamic Resources in App Cache
	* HTML5 App Cache 	  

## Optimize Media Usage
* Average Payload
* Use Native Image Resolutions
* Use Image Sprites or (don't use images at all)

## Use CSS3
* Replace Images with CSS3 Border Radius
* Levarage CSS Transitions

## Efficiently Structure Markup
* Link Style Sheets at top of page
* Only Include Necessary Styles
* Always link javascript at end of file
* Defer script execution
* Remove duplicate code
* Standardize on a single framework
* Don't include script just to be cool
* Reduce number of frameworks

## Align timers to display frames
* Paint as much as your users can see
* Stack (Fixed Length, faster access), Heap

## Working with DOM
* Avoid chattiness with the DOM
* Avoid automatic conversions of DOM values (values from DOM are strings by default)
* Internal Type System: Fast object Types (property orders matter)
* 