zap-webdriver
=============
Example security tests using JUnit, Selenium WebDriver and OWASP ZAP. 
The tests use selenium to navigate and login to the app, then spider the content with ZAP and perform a security scan using ZAP's scanner.  Tests pass or fail based on vulnerabilities found.

Getting started
===============

1. Download and start [OWASP ZAP](https://code.google.com/p/zaproxy/wiki/Downloads?tm=2) at least version 2.4 
3. In the ZAP Options change the local proxy port to 8080
4. Download this repository
5. Look through the src/test/java/net/continuumsecurity/ZapScanTest class and check that the static fields match your setup.  In particular, change the CHROME_DRIVER_PATH to point to the chrome driver instance appropriate for your platform, the driver/ directory contains versions for Linux, Mac and Windows.
5. Run: mvn test

Details
=======
The Selenium steps to navigate the application and submit forms is contained in the MyAppNavigation class.  The JUnit testing steps are defined in ZapScanTest.
Keeping these two aspects separate makes test maintenance easier.  If your testing team already has Selenium code to perform navigation (e.g. Page Objects), you can then drop those in to the MyAppNavigation class.

The ZapScanTest class should be regarded as a starting point for your own test cases.




