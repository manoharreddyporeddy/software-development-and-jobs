(This is in progress)

# all-about-software-development

<pre>
My work experience tells below are important:

-----------------------------------------------
# My Software “-ilities”

1. Functionality
2. Security
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
- is the sytem extendable? by end users or 3rd party developers?

4.3. Portability
- 

5. Scalability - meet the expected and little over the expected usage/ demand (requests & users)
- what is your current peak load that system can handle? https://en.wikipedia.org/wiki/Concurrent_user
- what happens at the peak load? which system fails/slows down first? 
- what will happen when system fails/ slows down to accomodate more users? scales up (upgrade nodes) or scales out (add nodes)? is it automatic or manual?

6. Upgradeability

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
-----------------------------------------------


# good code stategies?

# logging level

1. dev,qa,prod environment

  important log messages at error level

2. local environment (computer/laptop)

  log messages at verbose level
  
3. log levels must be externally controllable

  form environment variables, host.json file, etc.
  restart application is generally done when doing above as a best practice


# time stamps

  all important operations, must be having TIME TAKEN logs, which tell how much time they took - save time for customer and cost


-----------------------------------------------

</pre>

some others here:
http://www.softwarearchitecturenotes.com/architectureRequirements.html
http://www.softwarearchitectures.com/overview.html
http://codesqueeze.com/the-7-software-ilities-you-need-to-know/

