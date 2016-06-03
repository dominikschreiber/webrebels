# Change the World with IoT and the Peer Web
Matthew Podwysocki ([@mattpodwysocki](https://twitter.com/@mattpodwysocki))

- IoT problems (examples for "no connectivity")
	- re-invent manufacturing (low margins, low-income areas)
	- re-invent farming
	- help in times of crisis
	- privacy (communicate + discover but remain privacy)
- Kim Cameron's Laws (<- privacy)
	1. Technical identity systems must only reveal information identifying a user *with the user's consent*.
	2. The solution that discloses *the least amount of identifying information* and best limits its use is the most stable long-term solution.
	3. Digital identity systems must be designed so the disclosure of identifying information is limited to parties having a necessary and justifiable place in a given identity relationship.
	4. A universal identity system must support both "omni-directional" identifiers for use by public entities and "unidirectional" identifiers for use by private entities,thus facilitating discovery [...]
	5. [...]
	6. [...]
	7. [...]
- the thali project (http://thaliproject.org)
	- bring peer web to as many devices as possible
	- enable local discovery
	- secure synchronization
- how to accomplish thali
	- always bet on JavaScript
	- device as a server (via Node.js)
	- node (v8) not allowed e.g. on iOS => [node-chakracore](https://github.com/nodejs/node-chakracore) at least for Windows Phone (hope: interpreter-independent node)
	- cordova to deploy
	- pouchdb as database (allows to replicate between phones)
	- wifi + bluetooth to enable communication
	- TLS + public keys for security
	- authenticate via pairing code (http://www.goland.org/coinflippingforthali/)
- why not webrtc?
	- needs browser
	- needs server to get JavaScript from
	- webrtc needs pairing server
	- DTLS authentication not implemented´
	- local net issues