## SDE-Interview-preparation-kit


---
Developer Complete toolkit for interview
---

[Encoding,Encryption,Hasshing, Obscfucation](https://danielmiessler.com/study/encoding-encryption-hashing-obfuscation/#:~:text=Encoding%20is%20for%20maintaining%20data,order%20to%20return%20to%20plaintext.)


Let me explain in simple words, encoding is transforming data that is easily readable and making sure data is reached destination without loosing special char like space replaced with %20 in URL encooding.
HTTML encoding, bas64,etc.

Encryption is securing data so that middle man can't read. It is to transform data to be secret and even middle man can read in anyways. Typical example enveloped letter vs postcard where only reciever can read only. Plain text is encrypted to cipherText using algorithm such as AES,RSA,etc. and secret key shared between sender and reciver only.

In this field hashing is used for integrity so that if any thing is modified , we get to know . Message can be hashed and signed with private key, reciever validate by using public key and hashed value is not changed. ex. SHA,MD5.

obfuscation is process to make anyone difficult to understand or copy the logic. Instance code obfuscation is done so that client can never reverse engineer and get the copy of code. 


### Why reactive programming? what is reactive system?
[Reactive](https://developers.redhat.com/blog/2017/06/30/5-things-to-know-about-reactive-programming/)

Flux - 
https://medium.com/@rarepopa_68087/reactive-programming-with-spring-boot-and-webflux-734086f8c8a5

### How SSL works?
[SSL](https://www.tutorialsteacher.com/https/how-ssl-works)

SSL offloading

### Why Queue?
https://stackify.com/message-queues-12-reasons/

https://developers.redhat.com/blog/2016/08/10/persistence-vs-durability-in-messaging/

### CAP
[cap](https://www.ibm.com/cloud/learn/cap-theorem#toc-what-is-th-DXABpEgu)

https://www.educative.io/edpresso/what-is-the-cap-theorem

https://phoenixnap.com/kb/acid-vs-base

##SQL vs NOSQL
Why SQL or nosql
Non /Structured Data - dbms optimised 
Model evolves around period of time , Data is not fixed 
No transaction 
acid vs base
Scaling 


### cahce design patterns
https://www.baeldung.com/cs/cache-write-policy

Screenshot 2021-04-27 at 12.31.55 AM<img width="1654" alt="Screenshot 2021-04-27 at 12 31 55 AM" src="https://user-images.githubusercontent.com/16834697/123817846-1f25a200-d916-11eb-9f33-3243fdc02dbd.png">



### JAVA vs NodeJS 

- Java supports multithreading Nodejs doesn't. Nodejs is suited for small size application.
- Garbarge collection for handling objects is good . In case of nodejs , it is not and for high load in complex app,nodejs cpu utilization spikes high.
- Java have OOPS, object oriented concepts that makes well managed. Like access modifier,etc. Node js is lagging in this.
- Exceeption handling is beautiful and we can throw custom exceptions.
- CPU intensive task required huge computational power that can be handled with Java, whereas I/O bound operations like real-time chat, media streaming etc., can be handled well with Node JS.
- community support and java is well used globally, so java is clear winner.

https://www.educba.com/java-vs-node-js/


### why nginx?

- Reverse proxy hiding servers (load balancing)
- Centralized logging capabilities 
- Capture request and response logs from ui to microservices , tracking failures 5xx,4xx
- Custom error pages - 4xx for micro fronend ui
- request caching 
- hiding application details like 

### Low latency and high throughput . How to achieve low latency in a app??

#### pagination with offset for partial response

#### Indexing in DB calls

#### PATCH over PUT
If the requirement at client end is to update only a small subset of the REST resource,   
it is advisable to use a PATCH over PUT command so that network saves bandwidth . PUT would require the whole data to be sent to the REST server

#### GC free logging - Log4J
  Garbage collection pauses are a common cause of latency spikes, many logging libraries slf4j, including previous versions of Log4j, allocate temporary objects like log event objects, Strings, char arrays, byte arrays and more during steady state logging. This contributes to pressure on the garbage collector and increases the frequency with which GC pauses occur/GC run .
  From version 2.6, Log4j runs in "garbage free" mode by default where objects and buffers are reused and no temporary objects are allocated as much as possible.
http://www.rationaljava.com/ 

#### Use StringBuilder 
 for heavy string manipulation so that don't keep creating new objects of string that forces GC run

#### Use Pools for thread, DB, files,etc.

#### Compressed OOPs is by default in Java8
you can keep more objects in cache

#### how Java 8 lambda helps for latency?

Lambdas are like anonymous inner classes, however they are assigned to static variables if they don???t capture anything.

```js
public static Runnable helloWorld() { //lambda
return () -> System.out.println("Hello World"); }


public static Consumer<String> printMe() { //not lambda
// may create a new object each time = Garbage.
return System.out::println; }


public static Consumer<String> printMe2() { //lambda
return x -> System.out.println(x); }

```

```js
Runnable r1 = helloWorld();
Runnable r2 = helloWorld();
System.out.println(r1 == r2); // prints true

Consumer<String> c1 = printMe();
Consumer<String> c2 = printMe(); 
System.out.println(c1 == c2); // prints false

Consumer<String> c3 = printMe2(); 
Consumer<String> c4 = printMe2(); 
System.out.println(c3 == c4); // prints true

```

#### caching ,varrnish cache server, EH cache in Java

#### Asynchronous and messaging tools

#### Load balancer, CDN, apigee throtttling based on client keys

#### using http2 as it used single tcp conn to send data in parallel. compress headers.

#### use gzip,brrotli to compress js,css and even api response. However it will use extra cpu cycles for decompress.


## Developers Roadmap
[Roadmap to becoming a web developer in 2019](https://github.com/kamranahmedse/developer-roadmap)

## System Design

[Log System](https://engineering.linkedin.com/distributed-systems/log-what-every-software-engineer-should-know-about-real-time-datas-unifying)

[system-design-interview](https://github.com/checkcheckzz/system-design-interview)

[High Scalability blog](http://highscalability.com/blog/2014/2/26/the-whatsapp-architecture-facebook-bought-for-19-billion.html)

[Systme desgin primer by donne martin](https://github.com/donnemartin/system-design-primer)

[System Desgin by Shashank](https://github.com/shashank88/system_design)

[Redis architecture](https://medium.com/kokster/highly-available-redis-architecture-613c89f887b4)

[System Desgin Interview Question](https://hackernoon.com/top-10-system-design-interview-questions-for-software-engineers-8561290f0444)
[cont..](https://github.com/checkcheckzz/system-design-interview)

[Online Movie Ticket booking](https://medium.com/@shivangsarawagi/design-an-online-movie-ticket-booking-system-like-bookmyshow-com-a247214a63e3)

[Recommedation and personalisation](https://medium.com/netflix-techblog/system-architectures-for-personalization-and-recommendation-e081aa94b5d8?_sm_au_=iVVV1H5rMRH7P7NQ)

[Netflix Developer](https://medium.com/netflix-techblog/full-cycle-developers-at-netflix-a08c31f83249)

[System desgin case studies](https://github.com/sjuvekar/System-Design-Case-Studies/blob/master/studies/dropbox.md)

[System desgin for collab edit](https://hackernoon.com/building-conclave-a-decentralized-real-time-collaborative-text-editor-a6ab438fe79f)

[How web works ](https://github.com/vasanthk/how-web-works)

[Bloom Filter](https://hur.st/bloomfilter/)

[Overview of a compiler](https://www.codementor.io/erikeidt/overview-of-a-compiler-zayyljs2s?utm_swu=7179)

[coding inreview university](https://github.com/jwasham/coding-interview-university)

### [How does HTTPS actually work?](https://robertheaton.com/2014/03/27/how-does-https-actually-work/)

[Design Patterns](https://github.com/kamranahmedse/design-patterns-for-humans)

## Events

### [Difference between stream processing and message processing](https://stackoverflow.com/questions/41744506/difference-between-stream-processing-and-message-processing)

### [kafka vs message queues](https://hackernoon.com/a-super-quick-comparison-between-kafka-and-message-queues-e69742d855a8)

### [Streams vs Queues](http://docs.eventide-project.org/core-concepts/streams/streams-vs-queues.html)


### [How IPV4 subnetting works](https://serverfault.com/questions/49765/how-does-ipv4-subnetting-work)

## Architecutre

[Cassandra](https://docs.datastax.com/en/archived/cassandra/2.1/cassandra/architecture/architectureIntro_c.html)

[Whatsapp Architecture](http://highscalability.com/blog/2014/2/26/the-whatsapp-architecture-facebook-bought-for-19-billion.html)

## Scaling

[Whatsapp](http://www.erlang-factory.com/upload/presentations/558/efsf2012-whatsapp-scaling.pdf?_sm_au_=iVVV1H5rMRH7P7NQ)

[Whatsapp Scaling](https://vimeo.com/44312354?_sm_au_=iVVV1H5rMRH7P7NQ)

[Database Scaling](https://www.youtube.com/watch?v=dkhOZOmV7Fo)


## Microservices

[at amazon](https://docs.aws.amazon.com/aws-technical-content/latest/microservices-on-aws/introduction.html)

## Distributed Systems

### [Dr. Martin Kleppmann University of Cambridge] (https://www.cl.cam.ac.uk/teaching/2021/ConcDisSys/dist-sys-slides.pdf)

[Distributed Systems in One Lesson by Tim Berglund](https://www.youtube.com/watch?v=Y6Ev8GIlbxc)
### CAP Theorem [CAP by Shekhar Gulati](https://shekhargulati.com/2018/08/08/week-2-cap-theorem-for-application-developers/)
* Consistency: Every read is guaranteed to return the most recent write or an error
* Availability: Every request receives a non-error response from a non-failing node in a reasonable time. It is expected that the client may not receive the most recent write
* Partition tolerance: The system continues to operate when network partition happens

## Deployment

[Kubrnetes](https://cloud.google.com/kubernetes-engine/kubernetes-comic/)

## Coding

[Interview Question - geekForgeek](https://www.geeksforgeeks.org/must-do-coding-questions-for-companies-like-amazon-microsoft-adobe/)

[Coding questions](https://github.com/checkcheckzz/coding-questions)

[Interview Question - DonneMartin](https://github.com/donnemartin/interactive-coding-challenges)

[Interview Question - simple programmer](https://simpleprogrammer.com/programming-interview-questions/)

[Interview Question - hackernoon](https://hackernoon.com/50-data-structure-and-algorithms-interview-questions-for-programmers-b4b1ac61f5b0)

[Interview Question - LeetCode](https://leetcode.com/explore/featured/card/top-interview-questions-easy/)

[Data Structures and Algorithms in Java](https://github.com/donbeave/interview)

####  Add Two Numbers
[this is a problem](https://leetcode.com/problems/add-two-numbers/)

[Explanation of the solution](https://medium.com/the-renaissance-developer/problem-solving-skills-add-two-numbers-1db9af05039)


[Ultimate Guide](https://medium.freecodecamp.org/the-ultimate-guide-to-preparing-for-the-coding-interview-183251ee36c9)

## Datastructure

[All about tree](https://www.codementor.io/leandrotk100/everything-you-need-to-know-about-tree-data-structures-pynnlkyud)

[How To Not Be Stumped By Trees](https://medium.com/basecs/how-to-not-be-stumped-by-trees-5f36208f68a7)

[Vaidehi Joshi's world of Datastructure](https://medium.com/basecs)

[When to use linkedlist over arraylist in java](https://stackoverflow.com/questions/322715/when-to-use-linkedlist-over-arraylist-in-java)

## DDD (Domain Driven Design)

[How to define service industries](https://hackernoon.com/how-to-define-service-boundaries-251c4fc0f205)

[Capability-mapping-and-context-mapping](https://hackernoon.com/capability-mapping-and-context-mapping-95cf862f0753)

[DDD the 5 mintue master](https://medium.com/the-coding-matrix/ddd-101-the-5-minute-tour-7a3037cf53b8)


## Caching

[Caching Tutorial for Web Authors and Webmasters](https://www.mnot.net/cache_docs/?_sm_au_=iVVV1H5rMRH7P7NQ)

## Security

https://www.youtube.com/watch?v=otWst36CKyM

## Login system

[Definitive guide for website authentication](https://stackoverflow.com/questions/549/the-definitive-guide-to-form-based-website-authentication/477578#477578)

## Courses

[Safari Books - Learn design pattern](https://www.safaribooksonline.com/videos/learn-design-patterns)

[Safari Books - Break away system](https://www.safaribooksonline.com/videos/break-away-programming)

[Safari books - Java Inteview Guide](https://www.safaribooksonline.com/videos/java-interview-guide)


## JAVA

[10 JAVA interview question](https://dzone.com/articles/top-10-java-interview-questions-that-i-recently-fa?edition=385432&utm_source=Weekly%20Digest&utm_medium=email&utm_campaign=Weekly%20Digest%202018-08-29)
[Java Interview question](https://www.edureka.co/blog/interview-questions/java-interview-questions/)

[Core Java interview questions](https://www.journaldev.com/2366/core-java-interview-questions-and-answers?utm_source=newsletter&utm_medium=sendy&utm_campaign=emails)

## REST

[RESTful APIs ](https://restfulapi.net/)

[Microsoft Dcouments on API-Design best practice](https://docs.microsoft.com/en-us/azure/architecture/best-practices/api-design)


## Networking

[100 networking question](https://career.guru99.com/top-100-networking-interview-questions-answers/)


## Design Pattern

[Design Pattern - DZONE](https://dzone.com/refcardz/design-patterns?chapter=1)

 [Design Pattern - JavaTPoint](https://www.javatpoint.com/creational-design-patterns)

## Database

[Understanding nosql](https://www.kdnuggets.com/2016/07/seven-steps-understanding-nosql-databases.html)


### Process & Standard

[Clean Code](https://engineering.videoblocks.com/these-four-clean-code-tips-will-dramatically-improve-your-engineering-teams-productivity-b5bd121dd150)


## Success Stories

[System Desgin](https://medium.freecodecamp.org/how-to-system-design-dda63ed27e26)

## Almost Everything

[Everything](https://github.com/andreis/interview)

## Web Architecture 101

[Web Architecture 101](https://engineering.videoblocks.com/web-architecture-101-a3224e126947)


## Online Videos

[5 Tips for System Design Interviews](https://www.youtube.com/watch?v=CtmBGH8MkX4)

[System Design: How to design Twitter? Interview question at Facebook, Google, Microsoft](https://www.youtube.com/watch?v=KmAyPUv9gOY&t=449s)

[Tech Dummies - Narendra L
](https://www.youtube.com/watch?v=wYk0xPP_P_8&list=PLkQkbY7JNJuBoTemzQfjym0sqbOHt5fnV&index=3)

[All about algorithms](https://youtu.be/9TlHvipP5yA)

[Tech Primers](https://youtu.be/Wa_q8C6Qo68)


## Interview Formats
[For many comapnies](https://github.com/yangshun/tech-interview-handbook/blob/master/non-technical/interview-formats.md)


## FAQ#1 : Difference between JWT (Java Web Tokens) & Oauth

[jwt-vs-oauth](https://community.apigee.com/questions/21139/jwt-vs-oauth.html)

[Deep Copy vs Swallow Copy](https://dzone.com/articles/java-copy-shallow-vs-deep-in-which-you-will-swim)

[RFC7519](https://tools.ietf.org/html/rfc7519)



| JWT | OAuth |
|--|--|
| its a token, JSON Web Token (JWT) is a compact, URL-safe means of representing claims to be transferred between two parties | its a framework to dispense token  |
| JWT is a different kind of OAuth token | OAuth token is not the only token
| is not a pointer to information |  a pointer to information
| JWT contains real information, it can be large | can be small as its just a pointer
|JWT are self-validating" what they mean is, any holder of the JWT can open it, validate it, and then make authorization decisions based on the claims presented in it. | Oauth are not
|JWT supports "Federation" - anyone can generate a token, and anyone can read and validate a token . | used when there is no federation
| used when asynchrony is required|
|  security. Both are bearer tokens. Both need to be protected as secrets.|same
|useful for self authenticating tokens|
|has lot more context about the user, session - including the signature.|less context
|better at performance as no server call requried|server clal required|
|forced to have lower expiry times to these tokens, as they are valid till the pre-defined rules re valid|





## FAQ#2 : Difference between Container and VM

[differences](https://www.docker.com/what-container#/package_software)

|Container |VM
|--|--|
|Shares the OS and resources|A full virtualized system gets its own set of resources allocated to it, and does minimal sharing.|
|If you just want to isolate processes from each other and want to run a ton of them on a reasonably sized host, then Docker/LXC/runC seems to be the way to go.|If you want full isolation with guaranteed resources, a full VM is the way to go|
|![docker](https://www.docker.com/sites/default/files/Container%402x.png)|![VM](https://www.docker.com/sites/default/files/VM@2x.png)|
|**How containers works at low level?**   Each container runs in its own namespace but uses exactly the  _same_  kernel as all other containers. The isolation happens because kernel knows the namespace that was assigned to the process and during API calls it makes sure that process can only access resources in its own namespace. | **How virtualization works at low level?**    The net effect is that virtualization allows you to run two completely different OS on same hardware. Each guest OS goes through all the process of bootstrapping, loading kernel etc. You can have very tight security, for example, guest OS can't get full access to host OS or other guests and mess things up.|
|A virtual machine is a convenient way of packaging up virtual hardware, a kernel, and a user space. |A container, on the other hand, packages up only the user space; there is no kernel or virtual hardware.|
|![docker](https://rhelblog.files.wordpress.com/2015/09/user-space-vs-kernel-space-virtualization-vs-containerization11.png?w=640&h=254&zoom=2)|![VM](https://rhelblog.files.wordpress.com/2015/09/user-space-vs-kernel-space-virtualization-vs-containerization11.png?w=640&h=254&zoom=2)|
|Sharing an entire virtual machine with other developers can be inconvenient because of a virtual machine???s size and format|Containers have the advantage of providing developers, architects, quality engineering, release engineers, and systems administrators with a currency for collaboration that has the entire user space packaged and shipped in a convenient and easy to use format.|


## FAQ#3 : CAP Therorem

https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed

## FAQ#4 : Difference between Redis and Memcache

https://stackoverflow.com/questions/10558465/memcached-vs-redis

## FAQ#5 : Why Databases shouldn't be used as Message Queues

https://www.youtube.com/watch?v=9T-gNZ5bGCw

Here are possible drawbacks:

1) Polling intervals have to be set correctly. Too long makes the system is inefficient. Too short makes the database undergo heavy read load.
2) Read and write operation heavy DB. Usually, they are good at one of the two.
3) Manual delete procedures to be written to remove read messages.
4) Scaling is difficult conceptually and physically.


## Same thoughts from github

[interview by rockoder](https://github.com/rockoder/interview)

