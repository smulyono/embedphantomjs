embedphantomjs
==============

Embedded PhantomJS for Java (form from https://github.com/Jarlakxen/embedphantomjs)

This project provides an easy interface for execute PhantomJS with Java.

## Why?

- Easy way to execute JS inside Java
- Easy way to make a Scraper with Java

### Maven

///--- The changes (for support with version 1.9.8) are not available in OSS Sonatype)

Stable [OSS Sonatype](https://oss.sonatype.org/content/repositories/releases/com/github/jarlakxen/embedphantomjs/maven-metadata.xml)

	<dependency>
		<groupId>com.github.jarlakxen</groupId>
		<artifactId>embedphantomjs</artifactId>
		<version>2.8</version>
	</dependency>

### Changelog

- Added support for version 1.9.8

2.8
- Better windows support ( Thanks to @Dmitry-Shweikus )

2.7
- Unify Sync and Async interfaces for PhantomJSFileExecutor
- Improve error handling

2.6
- Some API improvments in PhantomJSFileExecutor
- Improve the core of the PhantomJSConsoleExecutor

2.5
- Some API improvments

2.4
- Provide some basic information of the PhantomJS process
- Better exception handling

2.3
- Bug fixing

2.2 
- Mejor API Refactor
- Now supports console style executor

2.1 
- Add asyncronic execution

2.0 
- Sopport for versions 1.9.2, 1.9.1, 1.9.0, 1.8.2, 1.8.1, 1.8.0
- Sopport binary versioned

1.3
- Full support for input stream script

1.2

- Bug fixing

1.1
- Bug fixing

1.0
- Auto-detect OS
- Auto-detect architecture
- Sopport for versions 1.7.0, 1.6.1, 1.6.0, 1.5.0, 1.4.1, 1.4.0, 1.3.0
- Check native installation
- Download from page



### Supported Versions

Versions: 1.9.2, 1.9.1, 1.9.0, 1.8.2, 1.8.1, 1.8.0, 1.7.0, 1.6.1, 1.6.0, 1.5.0, 1.4.1, 1.4.0, 1.3.0
Support for Linux, Windows and MacOSX.

### Usage

####Example I:

	PhantomJSFileExecutor ex = new PhantomJSFileExecutor(PhantomJSReference.create().build(), new ExecutionTimeout(1, TimeUnit.SECONDS));
	String output = executor.execute(new File("~/scrapper.js")).get();
	System.out.println(output);  // This prints "TEST1"


####Example II:

	PhantomJSFileExecutor ex = new new PhantomJSFileExecutor(PhantomJSReference.create().build(), new ExecutionTimeout(1, TimeUnit.SECONDS));
	String output = executor.execute("console.log('TEST1');phantom.exit();").get()
	System.out.println(output);  // This prints "TEST1"

####Example III:

	PhantomJSConsoleExecutor ex = new PhantomJSConsoleExecutor(PhantomJSReference.create().build());
	ex.start();
	ex.execute("var system = require('system');");
    	System.out.println(ex.execute("system.stdout.writeLine('TEST1');")); // This prints "TEST1"
    	System.out.println( ex.execute("system.stdout.writeLine('TEST2');")); // This prints "TEST2"
    	ex.destroy();
    
[![Bitdeli Badge](https://d2weczhvl823v0.cloudfront.net/Jarlakxen/embedphantomjs/trend.png)](https://bitdeli.com/free "Bitdeli Badge")
