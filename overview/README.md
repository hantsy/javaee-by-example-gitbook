# Overview

Java EE 7 was born in 2013, after a long-awaited 5 years, we finally got the release news of Java EE 8 and Glassfish v5. For more details, please read the official announcement [Java EE 8 and GlassFish 5.0 Released!](https://blogs.oracle.com/theaquarium/java-ee-8-is-final-and-glassfish-50-is-released) from Oracle blog portal.

## A brief intro of Java EE 8



But the road to Java EE 8 is not straight, most of proposed specifications are moved out of Java EE 8 finally. And in a long period, the development of some specifications were paused for some unknown reasons.

To save Java EE, the [Java community](https://javaee-guardians.io/) created a [petition](https://www.change.org/p/larry-ellison-tell-oracle-to-move-forward-java-ee-as-a-critical-part-of-the-global-it-industry) and wished Oracle can move forward Java EE more quickly.

At the same time, IBM worked together with Redhat and other Java communities and launched a new [MicroProfile](http://microprofile.io) which targets lightweight Java EE and cloud native applications. 

> Currently, Microprofile is also part of Eclipse EE4j project.

Although the Java EE 8 way is a little hard, finally it is released to the public.

And surprisingly Oracle decided to [open up Java EE progress](https://blogs.oracle.com/theaquarium/opening-up-java-ee) and [move it to Eclipse foundation](https://blogs.oracle.com/theaquarium/opening-up-ee-update). [An updated petition](https://www.change.org/p/larry-ellison-tell-oracle-to-move-forward-java-ee-as-a-critical-part-of-the-global-it-industry/u/21473794?utm_medium=email&utm_source=petition_update&utm_campaign=146669&sfmc_tk=xZ%2f6z4TGoQ02piKnRtK%2bejNgWC%2bWD6nr3P%2bcjkRrgGJqXJLLTSlXDQ6alq40O5pe&j=146669&sfmc_sub=46994739&l=32_HTML&u=27789648&mid=7259882&jb=1) was created to help moving Java EE to Eclipse more smoothly.

Java EE 8 should be the last version released by Oracle\(and Sun\).

## What is new in Java EE 8

Like me, some developers are a little disappointed about Java EE 8\(JSR 366\) , even complain it came  too late. But no doubt there are still lots of new features and improvements which are valuable to update ourselves.

There tow new specifications were newly introduced in Java EE 8.

* JSR 375 – Java EE Security API 1.0
* JSR 367 – The Java API for JSON Binding \(JSON-B\) 1.0

Some specifications have been updated to align with Java 8 and CDI or involved as a maintenance release.

* JSR 365 – Contexts and Dependency Injection \(CDI\) 2.0
* JSR 369 – Java Servlet 4.0
* JSR 370 – Java API for RESTful Web Services \(JAX-RS\) 2.1
* JSR 372 – JavaServer Faces \(JSF\) 2.3
* JSR 374 – Java API for JSON Processing \(JSON-P\)1.1
* JSR 380 – Bean Validation 2.0
* JSR 250 – Common Annotations 1.3
* JSR 338 – Java Persistence 2.2
* JSR 356 – Java API for WebSocket 1.1
* JSR 919 – JavaMail 1.6

The other specifications such as JMS, Batch have no updates in this version.

Unfortunately, some proposed specifications are not included in Java EE 8, including:

* JSR 371 - MVC is vetoed in the final stage, but it is still existed as a community based specification. 
* JSR 107 - JCache had missed the last train of Java EE 7, and also lost its attractiveness in Java EE 8.

