# JavaScript Testing Obstacles
Daniel Maslowski (@orangecms)

- terminology: system under test (SuT) tested in suites/features with setup + case/step + teardown
- motivation:
	- proof (works as specified)
	- regression mitigation (still works as specified)
	- design flaw detection (specification makes sense)
- what to test:
	- libraries, components, applications
	- crucial paths, essential operations, found bugs (to never encounter it again)
- technology:
	- test runners (cli -> run test -> print report => allows CI/CD)
	- frameworks (assert, jasmine, mocha, cucumber, ...)
	- browser testing (selenium == selenium-webdriver/chromedriver/webdriverjs/webdriverio, karma)