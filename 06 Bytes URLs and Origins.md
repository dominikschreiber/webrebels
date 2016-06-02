# Bytes, URLs and Origins 
Anne van Kesteren ([@annevk](https://twitter.com/@annevk))

- standards: deduce features to fundamentals, explained from first principles
- bytes
	- unicode: U+0000 .. U+10FFFF, on all computing platforms (problem: different representation of same code point)
	- byte stream -[encoding]-> code point stream (e.g. `0xE2 0x93 0x8B` [windows-1252] = `0x00C2 0x201C 0x2039`, `0xE2 0x93 0x8B` [UTF-8] = `U+24CB`)
	- JavaScript api:
		```javascript
		let d = new TextDecoder()
		let b = Uint8Array.from([0xE2, 0x93, 0x8B])
		d.decode(b)
		// => Ⓥ
		```
- URLs
	- http is restricted to bytes => `%` encoding
	- document encoding influences url parsing
		```javascript
		let link = document.createElement('a')
		link.href = '?\u00BF'
		link.search
		// => ?%BF
		```
- origins
	- web security based on origins
	- origin = (scheme, host, port), e.g. `('https', 'example', null)`
	- communication between visited page (A) and pages visible to the user (B) => browser fetches on behalf of the user
	- *Same-Origin-Policy*:
		- `GET` + `POST`
		- no arbitrary HTTP headers
		- display images (=> get width+height of images)
		- execute scripts
		- use stylesheets (=> use `getComputedStyle()`)
		- cannot read arbitrary URLs
	- *CORS*:
		- Client: `Origin: A`
		- Server: `access-control-allow-origin: A`
		- `<img src="..." crossorigin>` can be read by `canvas`
		- `<script src="..." crossorigin>" can get detail from `window.onerror`
		- `<link rel="stylesheet" href="..." crossorigin>` can get access to CSSOM
		- *CORS-preflight*: check that server is aware of CORS
		- credentials: `Access-Control-Allow-Credentials: true` only advised if both origins credentials user already
			```javascript
			fetch(url, {
				headers: {'Web': 'Rebels'},
				credentials: 'include'
			}}
			```