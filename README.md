# all-about-software-development

(This is in progress)

<code  style="white-space: pre-wrap; word-break: break-all; overflow-wrap: break-word; display: block;">

-----------------------------------------------
# My Software “-ilities”

0. Portability - ability for your application to run on numerous platforms, includes actual application hosting, viewing, or data portability.
- Which operating systems does your program run on?
- For web applications, which browsers does your web app support?
- Can the data be migrated to other systems?

1. Functionality
2. Security -  the measure of system’s ability to resist unauthorized attempts at usage or behavior modification, while still providing service to legitimate users.
- does the system needs user-based or role-based security or both?
- does the system need code-access security?
- what operations need to be secure?
- how users will be administered?

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

https://en.wikipedia.org/wiki/ACID
https://en.wikipedia.org/wiki/SOLID_(object-oriented_design)
https://en.wikipedia.org/wiki/Create,_read,_update_and_delete
https://en.wikipedia.org/wiki/CAP_theorem

-----------------------------------------------

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

