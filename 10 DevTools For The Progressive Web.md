# DevTools for the Progressive Web
Kenneth Auchenberg ([@auchenberg](https://twitter.com/@auchenberg))

- DevTools context
	- web changed from documents to applications
	- devices changed from workstations to smartphones + tablets + laptops
	- desktop browsers changed from ie6 to chrome + edge + firefox + opera + safari
	- internet adoption changed: more chinese mobile users than EU population, "*mobile* internet" is given, 237mio new internet users in 2015
	- mobile browsers changed: ucweb (Ali Baba) has 20% mobile market share (more than safari)
	- browser engines changed: Blink
	- users won't notice the browser any more
		- mobile: web embedded inside native
		- desktop: web as a runtime (e.g. electron)
	- Web Assembly: ship C code in the browser
	- Front-End role is redefined as native and web melt (e.g. push notifications)
- Current DevTools:
	- devs used to DevTools paradigm (DOM explorer + computed style)
	- modern DevTools are a collection of tools (DOM explorer + sources + performance + console + ...)
	- switching between debugging context (browser w/ DevTools) and authoring context (editor) is workflow (b/c authoring tools !== DevTools) => **Web Developer Stockholm Syndrome**
- Fighting the debugging vs authoring context problem
	- vscode plugin to debug chrome websites in vscode
	- edge diagnostics adapter: edge speaks chrome debugging protocol
	- node will speak chrome debugging protocol
- DevTools for the progressive web:
	- DevTools should be decoupled from browsers (think of game developers compiling to WebAssembly running in Yandex browser who have to debug with desktop chrome)
	- vscode plugin targets PWAs on mobile via remote debugging as well (has a protocol adapter for the webkit remote debugging protocol to chrome debugging protocol)