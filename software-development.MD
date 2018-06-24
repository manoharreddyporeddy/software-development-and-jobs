<pre>

# all-about-software-development
---

<code  style="white-space: pre-wrap; word-break: break-all; overflow-wrap: break-word; display: block;">

This is in progress

# My Software “-ilities”

0. Portability - ability for your application to run on numerous platforms, includes actual application hosting, viewing, or data portability.
- Which operating systems does your program run on?
- For web applications, which browsers does your web app support?
- Can the data be migrated to other systems?

1. Functionality

2. Security -  the measure of system’s ability to resist unauthorized attempts at usage or behavior modification, while still providing service to legitimate users.
- does the system needs user-based or role-based security or both?
-- how users will be administered?
- does the system need code-access security?
- what operations need to be secure?

3. Usability
- can customers easily use system?
- can customers easily learn system? use UI metraphors (desktop computer?)
- can customers easily  control system?
- are common operations fast?
- are error messages are good?
- are validations correct?

3.2. Lookibility

3.3. Availability (Reliability)
- Mean time between failures (MTBF) is predicted elapsed time between inherent failures of a mechanical system, during normal system operation
- MTBF can be calculated as the arithmetic mean (average) time between failures of a system
https://en.wikipedia.org/wiki/Mean_time_between_failures
- what is the time between two failures of system? what is average of all such incidents? are they acceptable? 
- when the system can be down? like when upgrades happen? how long can the sytem be down when this happens?
- can the down times be scheduled?

4. Maintainability (Changeability/ Flexibility/ Testibility)
- easy to change the code? (TBD system?)
- enough unit/api/regression tests? to find if the current system is breaken due to new change added to system?
- enough inline documentation? is code easy to read?

4.2. Extensibility
- is the sytem extendable? by end users or 3rd party developers, via user defined feilds, scripts, etc?
- is the database schema flexible to accomodate changes?
- does the system allow Inversion of Control  (IoC)

5. Scalability - meet the expected and little over the expected usage/ demand (requests & users)
- what is your current peak load that system can handle? https://en.wikipedia.org/wiki/Concurrent_user
- what happens at the peak load? which system fails/slows down first? 
- what will happen when system fails/ slows down to accomodate more users? scales up (upgrade nodes) or scales out (add nodes)? is it automatic or manual?
(having switched between platforms like azure & aws (or GCP), this looks to be not a severe problem, once you select a programming language that these both support )

6. Upgradeability


TBD:
 (Backwards compatibility, Interoperability, and Reusability to name a few).
 http://www.softwarearchitecturenotes.com/architectureRequirements.html
 

sources:
http://www.softwarearchitecturenotes.com/architectureRequirements.html
http://www.softwarearchitectures.com/overview.html
http://codesqueeze.com/the-7-software-ilities-you-need-to-know/



-----------------------------------------------
# Mathematics
-----------------------------------------------
# Data structures
-----------------------------------------------
# Algorithms



-----------------------------------------------
# CAP
	Consistency		- Every read receives the most recent write or an error
	Availability		- Every request receives a (non-error) response – without guarantee that it contains the most recent write	
	Partition tolerance	- The system continues to operate despite an arbitrary number of messages being dropped (or delayed) by the network between nodes

Looks, like P can have either A or C. And, AC is possible, not P.

# ACID
	Atomicity	- each transaction be "all or nothing"
	Consistency	- any transaction will bring the database from one valid state to another
	Isolation	- concurrent execution of transactions results in a system state that would be obtained if transactions were executed sequentially, i.e., one after the other
	Durability	- once a transaction has been committed, it will remain so, even in the event of power loss, crashes, or errors

# SOLID
* Single responsibility principle
	a class should have only a single responsibility
		(i.e. changes to   only one part of the software's specification   should be able to   affect the specification of the class)
		only one part of the software's specification -> specification of the class
		1 software's specification/ functionality => 1 class/module - only one reason to change
		1 concern => 1 class/module
		more robust
		report compilation (creation), report printing (on paper)

* Open/closed principle
	software entities
* Liskov substitution principle
* Interface segregation principle
* Dependency inversion principle

Firewall
	software or hardware (firewall device/ computer) or both
		sits between
			internal network
			and
			outside external network/ internet
	types:
		network firewall/ network-based firewall	- (hardware) - internal network of computer/system connected to internet
		host-based firewall							- (software) - single computer/system connected to internet
	2 interfaces
		1 connected to internal network
		1 connected to external network
	software or hardware (firewall device/ computer) or both
		sits between
			internal network
			and
			outside external network/ internet
		runs set of rules
			to determine wether or not
				traffic/ data/ request
					(http, ftp, etc.)
				from/to
					internal network, and
					outside external network
				is allowed/ not
	layered firewall
		multiple firewall, one behind the other - for better security
	connect to internet via
		modem
		network
		DSL line
		cable modem

https://en.wikipedia.org/wiki/ACID
https://en.wikipedia.org/wiki/SOLID_(object-oriented_design)
https://en.wikipedia.org/wiki/Create,_read,_update_and_delete
https://en.wikipedia.org/wiki/CAP_theorem

-----------------------------------------------

# Containers vs VMs
vm        =  OS > dependencies/libraries > application
container =       dependencies/libraries > application

scenario:
       1 app on                         1 server hardware  - not  efficient
multiple app on multiple vms        (on 1 server hardware) -      efficient, since        VM has  1 OS in it
multiple app on multiple containers (on 1 server hardware) - most efficient, since Container has no OS in it

creation:
virtual machine: server hardware > os > hypervisor > vm1, vm2, vm3..
container:       server hardware > os >            > system chunks called container (container1, container2, container3..)  (chunks are made using kernal tools: namespaces,cgroups,chroots)

docker containers:
 docker creates containers (using kernal tools)
  linux computer > docker deamon > register & login with "docker hub", the registry
  docker client (run commands: docker run apache, docker run rails, etc)
   -> talk to docker deamon
   ->  get image (apache, rails, etc.) if not cached, by talking to docker hub
   ->  cache image 
   ->  start container with requested image by talking to linux OS (repeat to start another container with another image)

kubernetes containers:
TBD

docker swarm:
TBD




# fan out/ fan in

the code can fan out and call various Activity Functions (tasks = durableOrchestrationContext.CallFunctionAsync)
wait for them all to complete (await Task.WhenAll), and then 
allow you to sum the results (fan in) (tasks.Sum(t => t.Result))

-----------------------------------------------



# good code stategies?

# logging level

0. log level matters for performance

1. dev,qa,prod environment

  prod will have error level
    important log messages at error level
    
  since prod will have error level, have dev & qa at error level (occasionally see if verbose level is working fine)

2. local environment (computer/laptop)

    log messages at verbose level
  
3. log levels must be externally controllable

  form environment variables, dev.config, host.json file, etc.
  restart application is generally done when doing above as a best practice


# time stamps

  all important operations, must be having TIME TAKEN logs, which tell how much time they took - save time for customer and cost


-----------------------------------------------

</code>

</pre>
