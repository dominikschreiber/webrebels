# Progressive Web Apps: A Love Story
Nolan Lawson ([@nolanlawson](https://twitter.com/@nolanlawson))

- Pokédroid app:
	- 2010: first smartphones, not really in web dev focus 
	- Pokédroid simply gives information on Pokémon in the Pokédex
	- **offline** (even with 2 min import on first start) => super fast in use
	- 3.5mb SQLite database
	- DMCA'd: publishing app asserts IP ownership of content => website ok (but 2011 no technology for offline web app)
- Web: huge change from 2010->2016
	- 2009: html5 vs flash vs silverlight
	- 2016: Progressive Web Apps vs Java (Android) vs Swift/Objective-C (iOS)
- Progressive webapps: website that "becomes" an app
	- works offline
	- launches from home screen ("add to homescreen" button offered by browsers based on usage heuristics)
	- "feels" like a native app (e.g. 60fps)
	- "native" features (e.g. push notifications, background sync)
- available technologies that allow progressive webapps:
	- Application Cache => *ServiceWorker*
	- LocalStorage/WebSQL => *IndexedDB*
	- Touch icons => *Web App Manifest*
	- Save to homescreen => *Install banner* (offered by browser)
- [pokedex.org](https://pokedex.org): progressive webapp successor to Pokédroid
	- Server-side rendering (test with disabled javascript + throttle to 2G)
	- FLIP animations (JavaScript animations @ 60fps)
- best practices from a native app developer:
	- prefer offline (fast, always there): PouchDB on client, sync with CouchDB on server if entry not found
	- use background threats (=> web workers): Action Message (UI => web worker) -> Action Handler (web worker) -> Render (virtual DOM, web worker) -> Diff (web worker) -> Patch message (web worker => UI)