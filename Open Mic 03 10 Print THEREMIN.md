# 10 Print THEREMIN
Mathieu Henri ([@p01](https://twitter.com/@p01))

- 10 Print HTML => creative coding
	- draw a maze in html
		```javascript
		onmousemove = e => {
			e.target.innerHTML = String.fromCharCode(
				9585.5 * Math.random(), // \ or /, corners connected
				8203 // empty white space
			)
		}
		```
- 10 Print THEREMIN
	- build a html theremin
		```javascript
		let freq = 0
		let vol = 0
		onmousemove = e => {
			freq = 440 * Math.pow(2, e.pageX / window.innerWidth)
			vol = .1 * e.pageY / window.innerHeight
		}
		let d = 1024
		let c = new AudioContext()
		let s = c.createScriptProcessor(d, 0, 1)
		s.connect(c.destination)
		let t = 0
		s.onaudioprocess = e => {
			let data = e.outputBuffer.getChannelData(0);
			for (let i = 0 ; i < data.length; t += 1 / c.sampleRate) {
				data[i++] = (t % 1) * .1
			} 
		}
		```