# The Pragmatic Programmer

# 1 - A Pragmatic Philosophy

## 1 - It's your life

### **TIP 3)** You have agency
> You can change your organization or change your organization - Martin Fowler
- Don't let technology pass you by: make time to study.

## The cat ate my source code
- Take responsibility for yourself, actions (career advancement), learning and education, project, day-to-day work.
- Own up to your shortcomings, be honest and direct.
- *Team trust.* You and your your team should rely on each other (essential for creativity and collaboration).


### **TIP 4)** Provide options, don't make lame excuses

- *Take responsibility.* It is up to you to provide solutions, not excuses.
- When you make a mistake, admit it and try to offer options.
- Before telling bad news, run through the conversation and come up with answers for the possible objections.
- Try to flush out lame excuses before voicing them aloud (remember what you think when you hear a lame excuse).
- "I don't know... But I'll find out."

## 3 - Software entropy

- Disorder increases = "Software rot", "technical debt".
- Neglect accelerates software rot.

### **TIP 5)** Don't live with broken windows

- Hopelessness can be contagious.
- Repair bad designs, wrong decisions, poor code as soon as it is discovered or *board it up* (e.g., comment out the offending code).
- First, Do No Harm. Don't cause collateral damage to fix broken windows.


Make quality a requirements issue:
- Great software today is often preferable to the fantasy of perfect software tomorrow (early feedback improves software).
- Avoid overembellishment and overrefinement in functional software.
- Avoid feature bloat (bloatware), useless features.

## 6 - Your knowledge portfolio
- Value of knowledge declines, experience can become obsolete or irrelevant.
- Building your portfolio:
  - Invest regularly
  - Diversify
  - Manage risk (don't put your technical eggs in one basket)
  - Review and rebalance
- **Opportunities for learning**. always have something to read.


### **Tip 9)** Invest regularly in your knowledge portfolio
- **Goals.** Acquiring intellectual capital:
  - Learn at least one new language every year.
  - Read a technical book each month.
  - Read nontechnical books, too.
  - Take classes.
  - Participate in local user groups and meetups.
  - Experiment with different environments.
  - Stay current.

### **Tip 10)** Critically analyze what you read and hear
- **Critical thinking**. Portfolio should be accurate, unswayed by either vendor or media hype. Ask  "the five whys":
  - Who does this benefit? Follow the money.
  - What is the context? Best practices-> best for who?
  - When and Where would this work?
  - What will happen next? What will happen AFTER that?
  - Why is this a problem?

## 7 - Communicate!
Looked over (quickly examined)  >> overlooked (not noticed)

### **Tip 11)** English is just another programming language
Communicating = conveying what you want to convey - not just talking! What are the needs, interests, and capabilities of the audience?
- **Know what to say**.  Does this communicate what I want to express to my audience in a way that works for them? Refine until it does! Jot down ideas and plan strategies to get them across.
- **Choose your moment**. Make what you are saying relevant in time as well as in content.
- **Choose a style**. Hand-holding or too long didn’t read?
- Make it look good - You can slave in the kitchen for hours only to ruin your efforts with poor presentation.
- **Involve your audience**. Get feedback from the readers with early drafts
- **Be a listener**. Ask people to restate the discussion in their own words. Turn the meeting in a dialog.
- **Get back to people**. Always respond to email and voicemails - even if the response is simply "I will get back to you later."

### **Tip 12)** It is both what you say and the way you say it
Documentation - unfortunate necessity :-)

### **Tip 13)** Build documentation in, don’t bolt it on
- Why decisions were made? What other alternatives were discarded? Engineering trade-offs
- Code already show HOW it is done, focus on WHY.

## 8 - The essence of good design

### **Tip 14)** Good design is easier to change than bad design
- ETC = Easy to change - underlying principle of decoupling, single responsibility, naming.
- Conscious reinforcement - Did the thing I just did make the overall system easier or harder to change?
- If not sure: "easy to change" - try to make what you write replaceable (keep code decoupled and cohesive)
- Leave a tag in the source.

## 9 - DRY - The evils of duplication
Knowledge is not stable, maintenance, reorganizing, and reexpressing knowledge in system is time consuming.
Programmers are constantly in maintenance mode (understanding, requirements, environment change day by day).

### **Tip 15)** DRY: Don’t Repeat Yourself
- Every piece of knowledge should have a single, unambiguous, authoritative representation within a system.
- Duplication of knowledge or intent (not just code).
- ACID TEST: When some single facet of the code has to change, do you find yourself making that change in multiple places?
- Don't mistake coincidences for duplications (e.g., function bodies are the same but they represent different knowledge, that can effect change later).
- Duplication in documentation - MYTH, INSANITY - commenting all functions  compensates for BAD naming.
- DRY violations in data - e.g., attribute can be calculated from others attributes (DRY can be violated in this case improve performance).
- Where possible use accessor functions (get, set), to make it easier to add functionality in the future.
- Uniform access principle - All services offered by a module should be available through a uniform notation, which does not betray whether they are implemented through STORAGE or COMPUTATION.
#### REPRESENTATIONAL DUPLICATION
- Each interface with the outside world introduces a DRY violation (changes at one end, will break the other).
- Duplication across internal APIs.
- Duplication across external APIs.
- Duplication with data sources.
##### How to fix *
- Generate the containers (persistence frameworks) directly from the schema.
- Save key/value data structure +  table-driven validation (verify that the map you have created contains at least the data you need).

#### INTERDEVELOPER DUPLICATION
- At high-level can be fixed with a tight-knit team but insidious at module level.
- Appoint team member as project librarian.
- Central place with utility routines.

### **Tip 16)** Make it easy to reuse
If it is not easy, people will not do it -> knowledge duplication.

## 10 - Orthogonality
E.g., axes on a graph, vector (independent lines - can move fast in one axis only).
Independence or decoupling - Two or more things are orthogonal if changes in one do not affect any of the others (e.g., database and interface).
When components are highly interdependent there is no local fix.

### **Tip 17)** Eliminate Effects Between Unrelated Things
- Self-contained components: independent, and with a single, well-defined purpose (provided that interface is kept, changes won't ripple through the system).
- Gain productivity 
	- Changes are localized -> reduced development and testing time
	- Promotes reuse - specific, well-defined responsibilities (loosely coupled) -> reconfigure & reengineer
	- More functionality per unit effort by combining orthogonal components.
- Reduce risk
	- Isolated diseased sections
	- Less fragility (no ripple effect)
	- Better testing (in separate components)
	- Flexibility - interfaces to vendor, product, or platform can be isolated
- Design
	- Orthogonal = modular = component-based = layered
	- Layered approach
		- Each layer uses only the abstractions provided by the layers below it
		- Reduces the risk of runaway dependencies between modules 
		- 
		- Test: If I dramatically change the requirements behind a particular function, how many modules are affected? One (although changes can occur in many functions, ideally they belong to the same module).
		- Don’t rely on the properties of things you can't control (e.g., telephone numbers)
	- Toolkits and libraries - details should be isolated from code to make it easier to change vendors in the future (e.g., EJB uses the decorator pattern to add functionality -  delineate transactions - without changing the method).
	- Coding - RISK: duplicate knowledge or functionality
		- Keep code decoupled - shy code (don’t reveal anything unnecessary to other modules and don’t rely on other modules' implementations) - Law of Demeter.
		- Avoid global data - Easier to understand and maintain if any required context is passed through modules.
		- Avoid similar functions - remedy with Strategy (design pattern).
		- Be constantly critical of your code (REFACTOR, REORGANIZE, IMPROVE STRUCTURE AND ORTHOGONALITY).
	- Testing
		- Modular(unit) testing is easier than integration testing.
		- If large % of the rest of the system's code have to be imported -> module not well decoupled
		- Bug fixing - how localized the fix is?
            - Are the required changes scattered throughout the entire system?
            - Do other problems mysteriously arise?
            - Tip: Tag bug fixes - number of source files affected by each bug fix.
- Documentation:
	- Axes: Content and presentation
- Living with orthogonality
	- DRY + orthogonality = more flexible, understandable, easier to debug, test and maintain.
	- OO languages =  inheritance, exceptions, operator overloading, and parent-method overriding (via subclassing) can increase coupling in nonobvious ways.
	- Good coupling = cohesion (e.g., class coupling code to data).
	- functional languages = coupling can occur in  when the result of one function becomes the input of another (languages with good type systems can help mitigate).
	- Every language has temptations: features that can lead to increased coupling and decreased orthogonality.

## 11 - Reversibility
With every critical decision, the project team commits to smaller target - a narrower version of reality that has fewer options.

Changing course of action is expensive.

### **Tip 18)** There are no final decisions
- Flexibility: DRY + decoupling + external configuration
- Requirements, users, and hardware change faster than we can get software developed.
- Persistence as a service -> change horses in midstream (database A to database B)
- Prepare for contingences that might arise (e.g., change to mobile app)

### **Tip 19)** Forgo following fads
- FLEXIBLE ARCHITECTURE
	- You cannot plan for architectural volatility (latest fad, trend), make code easy to change:
		- Hide third-party APIs behind own abstraction layers
		- Break code into components (no monolithic applications!)
- Schrodinger cat - How many possible futures can your code support? Which are more likely?
## 12 - Tracer bullets
Soldiers use tracer rounds to refine their aim.
Tracer bullet development

### **Tip 20)** Use tracer bullets to find the target
- Need for immediate feedback under actual conditions with a moving goal (requirements may be vague, technology may be unknown, environment will change).
- Look for and prioritize:
	- the important requirements that define the system
	- Areas where there are no doubts
	- Biggest risks
- To make feature work, just implement the solidly shaded areas.
-
- Gradually fleshes out basic structure, adding new functionality by augmenting each component of the tracer code in parallel.
- Once you have achieved end-to-end connection, check how close you are, adjusting if necessary.
- Advantages of end-to-end connected systems:
	- User see something working early
	- Developers build a structure to work in: team won't need to pull as much of thin air (invent stuff) to make modules work -> consistency.
	- You have an integration platform: instead of big-bang integration, you'll be integrating unit-tested code every day -> debugging and testing more accurate.
	- You have something to demonstrate
	- You have a better feel for progress
- Tracer bullets don't always hit the target - but it is easier and quicker to bring tracer code nearer the target.
- Tracer code versus prototyping
	- Prototyping generates disposable code
	- Prototyping = reconnaissance and intelligence gathering that takes place before a single tracer bullet is fired.
	- Tracer code provides an architectural skeleton on which you hang code. E.g.:
		- 1 - trivial implementation + simple working user interface - show users the interface, and complete stubbed routines over time.
## 13 - Prototypes and post-it notes
- Prototyping is cheaper than full-scale production - risky or uncertain elements can be tried out without committing to building the real item.
- Code can ignore unimportant details. E.g.: prototype  performance -> poor UI is OK.
- Tracer bullet can be more appropriate when you cannot give up the details.

### **Tip 21)** Prototype to learn
- Anything unproven, doubtful, experimental should be prototyped (architecture, new functionality, performance issues, UI)
- What can be ignored?
	- Correctness
	- Completeness
	- Robustness
	- Style
- Prototypes gloss over details, and focus in on specific aspects of the system.
- Prototyping architecture
	- Defer details, how the system hangs together as a whole?
	- Areas to look for:
		- Are the responsibilities of the major areas well defined and appropriate?
		- Are the collaborations between major components well defined?
		- Is coupling minimized?
		- Can you identify potential sources of duplication?
		- Are interface definitions and constraints acceptable?
		- Does every module have an access path to the data it needs during execution? Does it have that access when it needs it?
- How not to use prototypes
	- Make it clear prototype (or its progeny) is disposable.

## 14 - Domain languages (boring!)
-  Tip 22 - Program Close to the problem domain
- Internal language - takes advantage of the features of its host language
- In general use off-the-shelf external languages (YAML, JSON, or CSV) if you can.
- Cheat for creating internal domain language = write functions to do the work
- Prototyping is cheaper than full-scale production - risky or uncertain elements can be tried out without committing to building the real item.

## 15 - Estimating

### **Tip 23)** Estimate to avoid surprises
- Do they need high accuracy, or are they looking for a ballpark figure?
- 130 days == 6 months, but feels shorter (higher degree of accuracy)
	- 1-15 days = days
	- 3-6 weeks = weeks
	- 8-20 weeks = months
	- 20+ weeks = Think hard before giving an estimate
- Before building models, ask someone who's already done it.
- The scope will for part of the answer: "assuming X and Y, Z will take T weeks".
- “You asked for an estimate to do X. However, it looks like Y, a variant of X, could be done in about half the time, and you lose only one feature.”
- Tradeoff = model simplicity and accuracy. 2Xrefining <=2X accuracy, experience will tell.
- Break the model into components
	- How do model components interact? Adding? Multiplying?
	- How component parameters contribute to the overall model?
- Give each parameter a value
	- Multiplying/dividing parameters are more significant
	- Find a justifiable way of calculating critical parameters
	- Errors occur because you are basing an estimate on other subestimates
- Calculate the answers
	- Hedge (bound) your answers
	- Couch your answers in terms of the parameters
- Keep track of your estimating prowess
	- When estimates go wrong, find out why, uncover what happened
- Estimating project schedules
	- Use ranges and scenarios
	- PERT - Program Evaluation Review Technique - optimistic/most likely/pessimistic estimate
	- Formulas and charts not always lead to accurate estimates
- Practice incremental development:
	- Check requirements
	- Analyze risk (and prioritize riskiest items earlier)
	- Design, Implement, integrate
	- Validate with the users
- Nailing down the number of iterations in the beginning is often a mistake: unless you are doing an application similar to a previous one, with the same team and the same technology, you’d just be guessing.
- Complete initial functionality -> refine guess
    

### **Tip 24)** Iterate the schedule with the code
- Team's productivity and environment will determine the schedule (refining each iteration)
- I will get back to you - better results if slow down the process

        
# CHAPTER 3 - The basic tools
- Expect to add to your toolbox regularly.
- Always be on the lookout for better ways of doing things.
- Let need drive your acquisitions (seek if your current tool don't cut it).
## 16 - The power of plain text
- Ability to manipulate knowledge, manually and programmatically, using every tool at our disposal.
- Binary data is meaningless without the application knowledge to parse it.

### **Tip 25)** Keep knowledge in plain text
- HTML, JSON, YAML, HTTP, SMTP, IMAP are all plain text because:
	- Insurance against obsolescence -human-readable forms of data prevail (e.g., 
        <SOCIAL-SECURITY-NO>123-45-6789</SOCIAL-SECURITY-NO>).
	- Leverage existing tools - plain text enables version controls, comparison (diff and fc), monitor file for accidental (or malicious) modification, easy to search (grep -r backup /etc).
- Unix Philosophy - small, sharp tools. Databases used in system administration are all plain-text (binary form in parallel for performance).
	- Easier testing - input without creating special tools to do so and regression tests can be trivially analyzed with shell commands or a simple script.
- Lowest common denominator - In heterogeneous environments the advantages of plain text can outweigh all of the drawbacks.

## 17 - Shell games
- GUI interfaces hide the full capabilities of your environment (hooks for capabilities can be unavailable).

### **Tip 26)** Use the power of command shells.
- A shell of your own - Configure look and feel, and define aliases. E.g.:
- Alias rm='rm -iv' prompt to remove file
- Things done manually in a GUI - sequence of clicks - automate!
    
## 18 - Power editing

### **Tip 27)** Achieve Editor Fluency
- Learn the commands that make your life easier. E.g.:
	- When editing text, move and make selections by character, word, line, and paragraph.
	- When editing code, move by various syntactic units (matching delimiters, functions, modules, …).
	- Reindent code following changes.
	- Comment and uncomment blocks of code with a single command.
	- Undo and redo changes.
	- Split the editor window into multiple panels, and navigate between them.
	- Navigate to a particular line number.
	- Sort selected lines.
	- Search for both strings and regular expressions, and repeat previous searches.
	- Temporarily create multiple cursors based on a selection or on a pattern match, and edit the text at each in parallel.
	- Display compilation errors in the current project. 
	- Run the current project’s tests.
- Challenges:
	- No more autorepeat - find commands to delete word, line, etc.
	- No mousepad - learn the shortcuts
	- Look for integrations
	- Write custom plugins
## 19 - Version control system (VCS)

### **Tip 28)** Always use VCS
- Branching out - "Little clone projects" - feature 1 branch A, feature 2 branch B.
- What is: Ansible, homebrew?
- Version control as a project HUB
        Many teams have their VCS configured so that a push to a particular branch will automatically build the system, run the tests, and if successful deploy the new code into production.
- Challenges:
	- Learn how to roll back.
	- How to recover laptop in case of a disaster? Represent other info in text files.
	- Consciously explore the features of your current VCS (continuous integration, build pipelines)
	- User version control for nonproject things.

### **Tip 29)** Fix the problem, not the blame

### **Tip 30)** Don't panic
- What could be causing the symptoms that you believe indicate a bug.
- Discover the root cause, not just the particular appearance.
- Where to start
	- Work on code built cleanly - no warnings!
	- Interview users and systematically test boundary conditions and realistic end-user usage patterns.

### **Tip 31)** Failing test before fixing code
- We want a bug that can be reproduced with a single command (not after 15 steps)
- Isolate the circumstances that display the bug - writing the test informs the solution.

### **Tip 32)** Read the damn error message
- If just bad result, chase it down with the debugger.
- Sensitivity to input values: get copy of dataset, feed to app, and binary chop the data until you isolate exactly which input values are leading to the crash.
- Regression across releases => binary chop time with version control.
- Binary chop in stack tracing -> see if error manifests in the middle, if so, the problem is before.
- Binary chop in data -> split dataset into two, and see if problems occur if you feed one or the other through the app, divide until a minimum set of values exhibit the problem.
- Logging and/or tracing:
- Tracing is invaluable in any system where time is a factor (concurrent processes, real-time system, event-based applications).
- Tracing allows to drill down into code as you descend the call tree.
- Trace should be in a regular, consistent format, to be parsed automatically.
- Rubber ducking:
- Explain code to other person (rubber duck, potted plant, teddy bear) step by step (while he nods up and down).

### **Tip 33)**"Select" Isn't broken
- Don't blame the system (OS, libraries, compiler, etc.), it is likely that the fault is on your side.
- Keep a close eye on the schedule when planning an update (new bugs might show up).

### **Tip 34)** Don’t assume it - prove it
- Beyond merely fixing it, determine why failure was not caught earlier.
- Check places susceptible to the same bug.
- How to test the bug faster? Better hooks? Log file analyzer?
- Discuss the problem with the whole team (perhaps is misunderstanding).
- Debugging Checklist
	- Is the problem being reported a direct result of the underlying bug, or merely a symptom?
	- Is the bug really in the framework you’re using? Is it in the OS? Or is it in your code?
	- If you explained this problem in detail to a coworker, what would you say?
	- If the suspect code passes its unit tests, are the tests complete enough? What happens if you run the tests with this data? 
	- Do the conditions that caused this bug exist anywhere else in the system? Are there other bugs still in the larval stage, just waiting to hatch?

## 21 - Text manipulation

### **Tip 35)** Learn a text manipulation language
- E.g., python, ruby, allow writing scripts faster to manipulate texts and experimenting ideas.
	- Example - convert .yaml to .json, convert camelCase to snake_case.

## 22 - Engineering daybooks
- Journal what you did, things learned, sketches of ideas, readings from meters (registros).

# Chapter 4 - Pragmatic paranoia

### **Tip 36)** You can't write perfect software
- Since no one writes error free code, we code defensively, validating all information.
## 23 - Design by contract (DBC)
- Contract = right and responsibilities of each party + agreement concerning repercussions if either party fails to abide by the contract.
- Correct program = does no more and no less than it claims to do.
- Preconditions = What must be true in order for the routine to be called
- Postconditions = What is the routine guaranteed to do (state of the world when it finishes).
- Class invariants (state invariant) = Assertion that should be true at every stable point (object at rest) in time during the life of an object.
- Example:
-
- Failure to live up to the contract is a bug (failing to execute the contract -> remedy previously agreed, e.g., exception, or termination).

### **Tip 37)** Design with contracts
- "Lazy" code - be strict in what you will accept before you begin, and promise as little as possible in return.
- DBC  Vs. test-driven development (TDD), property-based testing, and defensive programming
	- TDD might invite you to concentrate on the "happy path".
	- TDD is more black-box style, does not focus on checking internal invariants
	- DBC and assertions are forever - design, development, deployment, and maintenance.
	- Testing can target only one specific case at a time, whereas DBC defines parameters for success or failure in all cases.
- Implementing DBC (could be in the code comments or unit tests if not native)
	- Writing domain range, boundaries, and routine (doesn’t) promises to deliver is a huge leap forward in writing better software = otherwise you are programming by coincidence.
- Assertions = runtime checks of logical conditions, can check DBC partially (hard to propagate assertions down an inheritance hierarchy).
- DBC and crashing early -E.g., negative value to sqrt return Nan in java, and only later you discover surprising results. With DBC, we have an error and the stack trace.
- Who is responsible?
	- The caller, because the routine will never see parameters that violate its preconditions.
	- Express domain of function in the routine preconditions.
- Semantic invariants = inviolate requirements, not subject to the whims of policy, philosophical contracts.
- Dynamic contracts and agents
	- Design contracts such that agents and software can negotiate on their own to achieve a goal.

## 24 - Dead programs tell no lies
- Coding defensively - Data/code is what we think.
- Catch and release is for fish - don’t let the application code be eclipsed by error handling (lots of catch  statements for each exception induces coupling since new catches have to be added).

### **Tip 38)** Crash early
    Crash don’t trash - if the impossible happened, program is no longer viable and subsequent operations become suspect.
## 25 - Assertive programming
- No self-deception

### **Tip 39)** Use assertions to prevent the impossible
- Assertions check for things that should never happen (assert result != null && result.size() > 0 : "Empty result from XYZ";)
- Assertions and side effects - Heisenbug - Bug that changes the behavior of the system (e.g., interator.next()==null).
- Leave assertions turned on
	- For any complex program, you are unlikely to test even  a minuscule percentage of the permutations your code will be put through.
	- In a production environment (dangerous world) , errors are more prone to appear.
	- First line = check errors, second line = use assertions.
	- If there are performance issues turn off only assertions that really hit you (e.g., check sorting).

## 26 - How to balance resources
### **Tip 40)** - Finish what you start
- Ideally, function or object that allocates a resource should be responsible for deallocating it.  
  - Example, reopening files until memory crashes.
- Scope the lifetime of a resource to an enclosed block (e.g., with in Python). At the end of the block the file variable goes out of scope.

### **Tip 41)** Act locally
- Deallocate resources in the opposite order (you won't orphan resources if one references another).
- Allocate resources in the same other across different places of your code (AVOID DEADLOCKS).
- Balancing over time - rotating log files to save storage space, expiration date for logs in database…
- Balancing and exceptions - finally clause guarantees that everything allocated before exception happens is tidied up.
- With usual scoping rules, variables go out of scope via a return, block exit, or exception.
- An exception anti-pattern
-
- When you can't balance resources (e.g., dynamic data structures):
- Top-level is responsible for freeing substructures that in turn delete data they contain recursively.
- Top-level deallocated and substructures are orphaned.
- Top-level refuses to deallocate if it contains substructures.
- Write model to provide facilities (e.g., (de)allocation, debug, printing, (de)serialization, traversal hooks).
- Checking the balance - wrappers to keep track of (de)allocations (has resource usage increased since last execution loop? Are there memory leaks?).
- Java -> Setting object to NULL,  decreases references by one, and when it reaches zero, garbage collection starts to work.
## 27 - Don’t outrun your headlights: further off-axis you look, the darker it gets.

### **Tip 42)** Take small steps - Always
- The rate of feedback is your speed limit.
- Never take a task that is "too big" (fortune telling, quickly get past educated guess into wild speculation):
	- Estimate completion dates;
	- Plan a design for future maintenance;
	- Guess user needs or tech availability.
- Design your code to be replaceable instead of designing for the uncertain future  (decoupling + DRY).

### **Tip 43)** Avoid fortune-telling
- Black swans around the corner, tomorrow looks a lot like today, but don't count on it.

# Chapter 5 - Bend or break
## 28 - Decoupling
- Coupling - links together things that must change in parallel. Why things broke when you changed "just one thing" and not the other things to which it was coupled.
- Individual components should be coupled to as few other components as possible.
-
- Coupling is transitive.

### **Tip 44)** Decoupled code is easier to change
- Symptoms:
	- Dependencies between unrelated modules or libraries.
	- Simple change -> propagation
	- Fear of change (developers)
	- Meetings where everyone has to attend (no one is sure who will be affected by a change).

### **Tip 45)** Tell, Don't ask (TDA)
- Don’t make decisions based on the internal state of an object (destroys the benefits of encapsulation and spreads the knowledge of the implementation throughout the code.
- Train wrecks - chains of method calls:
```java
totals = customer.orders.find(order_id).getTotals();
totals.grandTotal = totals.grandTotal - discount; totals.discount = discount;
customer.orders.find(order_id).getTotals().applyDiscount(discount)
customer.findOrder(order_id).getTotals().applyDiscount(discount)
customer.findOrder(order_id).applyDiscount(discount)
```
- Why not doing customer.applyDiscountToOrder(order_id)? Showing that customer have orders is a pragmatic decision (orders are part of the domain).
- The Law of Demeter (LoD) by Ina Holland (guidelines - jolly good idea of Demeter)
	- Methods (C) call:
		- Other methods
		- Its parameters
		- Methods in objects it creates
		- Global variables (X)

### **Tip 46)** Don't chain method calls
- Don't have more than one "." to access something (either chained or not), unless what you are accessing is stable (e.g., libraries that come with the language).
- Chains and pipelines transform data, and introduce coupling (the format of the data returned must compatible with the format accepted by the next) (BUT easier to change than train wrecks).

### **Tip 47)** Avoid Global Data
- Globalization - the dangers of static things
	- Insidious source of coupling (every method has an additional parameter).
	- Making code reusable should be part of your coding routine (difficult to tease code apart when using globals).
	- Problem when writing unit tests.
- Global data includes singletons  (=global data). However, doing Config.getLogLevel() is better because it hides the business logic.
- Global data includes external resources (e.g., database, datastore, file system, service API). Wrap behind code that you control.

### **Tip 48)** if it's important enough to be global, wrap it in an API
- Inheritance adds coupling
- Coupled code is hard to change! Alterations in one place have secondary effects elsewhere in the code.
- Keep code shy - deal with things it knows about = amenable to change.
## 29 - Juggling the real world (writing responsive applications)
- Events = availability of information (external or internal)
- Finite state machines (FSM)
- Set of states (one is current)
- For each state a list of events that are significant.
- For each event, we define the new current state of the system.
- Pure FSM - Event stream parser (asterisk is anything else)
- FSM + actions (top=event, bottom=action). Example, remove scaping:
- The transition table could also have anonymous functions.
- FSM are a start
- The Observer pattern
- Source of events = observable + list of clients = observers (who are interested in the event)
- Used in GUIs (callbacks inform application of interaction)
- Observer registers interest (pass callback to observable) and when event occurs, all observers call the functions passed.
- Problem = coupling (callbacks handled inline, synchronously, introducing performance bottlenecks).
- Publish/Subscribe (pubsub) - message passing system
- Publishers and subscribers connected via channels (shared interface).
- Communication between pubs and subs is handled outside code (process, library, distributed infrastructure) and is potentially asynchronous.
- Downside: can't see which subscribers are involved with a particular message.
- Reactive programming, streams, and events
- Analogy with spreadsheet (values react).
- Events can trigger reactions (hard to handle).
- Stream
	- Treat events as collection of data (data-ish things can be done, such as manipulate, combine, and filter).
	- Can be asynchronous (code can respond to events as they arrive).
	- Baseline for event handling =reactivex.io
	- Event streams normally are populated as events occur (e.g., data is available in server), which implies that the observables that populate them can run in parallel.
	- Examples:
		- Zip two observables (result is generated when data is available in both)
		- Request (separate streams) are processed in parallel and asynchronously (e.g., observable event containing user ID when their session is created).
	- Abstraction - we don’t need to manage time (event stream unify synchronous and asynchronous processing).
	- Events are ubiquitous, more responsive and better decoupled
- Examples:
	- 
    
	- 

## 30 - Transforming programming
- Examples:
- Write us a program that lists the five longest files in a directory tree, where longest means “having the largest number of lines.”
-
- Assembly line - raw data in one end and the finished product (info) comes out the other.

### **Tip 49)** Programming is about code, but programs are about data
- Top-down: requirements + inputs/outputs
- |> pipeline operator (functional languages) = forward pipe or pipe - takes the value on its left and insert it a the first parameter of the function on its right. E.g.:
-
- Thinking in transformations does not require a particular language syntax: it is more a philosophy of design.

### **Tip 50)** Don’t hoard state; pass it
- Pipeline = data->code->data->code (data is a mighty river, a flow)
- Greatly reduce coupling - function can be used anywhere its parameters match the output of some other function.
- Error handling - inside or outside transformations.
	- Example representation: {:ok, result} or {:error, reason}
	- Errors are forwarded down the pipeline
	- Handling in the pipeline - defer running the pipeline functions until we know that previous steps in the pipeline were successful.
- Transformations transform programming - series of nested transformations - flatter designs
## 31 - Inheritance tax
- Common reasons to use:
- Don’t like typing - add common functionality from a base class
- Like types - express relationship between classes  - a Car is-a-kind-of vehicle
- Using inheritance to share code (don’t like typing)
	- Inheritance is coupling (child class coupled to parent, parent's parent AND the code that uses the child is also coupled to all the ancestors).
		- Change in parent class breaks every other class/code down in the hierarchy.
- Using inheritance to build types (like types)
	- Design diagrams - layer-upon-layer to express the smallest nuance of differentiation between classes.
	- Brittle, changes ripple up and down many layers.

### **Tip 51)** Don’t Pay Inheritance Tax
- Use Interfaces, protocols, traits - They can be used as types e.g., List<Locatable> can hold objects of that implement Locatable.

### **Tip 52)** Prefer interfaces to express polymorphism
- Delegation inheritance encourages developers to create classes whose objects have large number of methods (e.g., subclass makes use of a couple of methods from parent but still can call all).

### **Tip 53)** Delegate to services: Has-A Trumps Is-A
- Mixins, traits, categories, protocol extensions = create a set of functions, give the set a name, and extend a class or object with them. Result = class/object that combines the capabilities of the original and all its mixins. E.g.: class AccountForCustomer extends Account with Validation1, Validation2 (2 validation mixins)

### **Tip 54)** Use Mixins to Share Functionality
- Inheritance is Rarely the Answer - Interfaces/protocols, delegation, mixins - sharing type information, adding functionality, sharing methods.
## 32 - Configuration

### **Tip 55)** Parameterize your app using external configuration
- Keep the environment and customer specific values outside the app.
- Static configuration = flat files (JSON, YAML) or database tables.
- Configuration-As-A-Service - Store in service API (configuration changes can be made globally, specialized UI, configuration data becomes dynamic)
- Don’t write dodo-code (species that don’t adapt, die = dodo bird)
    

