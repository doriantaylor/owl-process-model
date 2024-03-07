<div class="section" about="#" typeof="owl:Ontology">

# A Process Model Ontology

Author  
<a href="http://doriantaylor.com/person/dorian-taylor#me"
rel="dct:creator"><span property="foaf:name">Dorian Taylor</span></a>

Created  
July 22, 2009

Updated  
February 6, 2014

April 6, 2017

March 8, 2020

Namespace URI  
<a href="https://vocab.methodandstructure.com/process-model#" about="#"
rel="sh:namespace vann:preferredNamespaceUri"><code>https://vocab.methodandstructure.com/process-model#</code></a>

Preferred Namespace Prefix  
`pm`

<div class="section">

<span property="rdfs:comment">This vocabulary encodes a model for
expressing generic business processes. Its purpose is to provide a
language and exchange format for software applications designed to
facilitate project management.</span> This vocabulary extends [the IBIS
vocabulary](https://vocab.methodandstructure.com/ibis#) in the natural
fashion that once we have framed an issue and decided to solve it, we
must then specify a method, nominate a person responsible, and allocate
time and material resources to carry out the solution.

![](https://vocab.methodandstructure.com/process-model-example)

<div class="section">

## Goal, Task, Target

In deliberate contravention to the received wisdom of management gurus
and their airport books, as well as countless project management and
to-do applications, this vocabulary separates the concept of an abstract
goal from the task of achieving it. It likewise separates these two
concepts from the stipulation of a budget and/or deadline. Finally, it
separates a concrete task from the abstract method by which it is
completed.

By separating these concepts into distinct logical objects, we gain new
capabilities:

1.  Budgets and deadlines become subordinate to the real availability of
    people, materials, equipment, and methods to achieve stated goals.
2.  We can record unintended consequences, both negative and positive,
    of carrying out tasks.
3.  The development of a *method* to carry out a given task is itself
    promoted to a first-order task.
4.  We can generate a library of methods, with statistics on people,
    time and costs, to inform future allocations of tasks and targets.

</div>

This process model vocabulary connects and extends the following
vocabularies:

-   <a href="https://vocab.methodandstructure.com/ibis#"
    rel="owl:imports">The IBIS (bis) Vocabulary</a>
-   <a href="http://purl.org/NET/c4dm/event.owl#" rel="owl:imports">The
    Event Ontology</a>
-   <a href="http://www.w3.org/2004/02/skos/core#" rel="owl:imports">Simple
    Knowledge Organization System</a>

</div>

</div>

<div class="section">

## Classes

The classes in this vocabulary are refined as follows:

![](https://vocab.methodandstructure.com/process-model-classes)

The central concepts,
[pm:Goal](https://vocab.methodandstructure.com/process-model#Goal) and
[pm:Task](https://vocab.methodandstructure.com/process-model#Task),
extend the [ibis:Issue](https://vocab.methodandstructure.com/ibis#Issue)
and [ibis:Position](https://vocab.methodandstructure.com/ibis#Position)
types, so that goals, tasks and targets can be mixed into, as well as
graduated from, generic collaborative argumentation and decision-making
sessions. Likewise, the
[pm:Action](https://vocab.methodandstructure.com/process-model#Action)
class extends
<a href="http://motools.sourceforge.net/event/event.html#term_Event"
rel="dct:references">ev:Event</a> so that actions and tasks can be mixed
in with generic events on a timeline.

<div id="State" class="section" about="[pm:State]" typeof="owl:Class">

### State

A State can be understood as a snapshot of a system at a given time,
such as before or after an event.

A State is distinct from a particular instant, but it is analogous to
it. At the time of observation, a State is either true or false.

Subclass of:  
<a href="http://www.w3.org/2004/02/skos/core#Concept"
rel="rdfs:subClassOf">skos:Concept</a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="Goal" class="section" about="[pm:Goal]" typeof="owl:Class">

### Goal

A Goal extends a State by way of being explicitly desired by an Agent.

A Goal is not actionable itself, although Tasks, which are Actions, must
achieve at least one Goal. At the time of observation, a Goal, like its
superclass, State, is either true or false. This entails that a Goal is
not expressed in terms of quantitative results or deadlines. That is the
job of a Target.

Subclass of:  
<a href="https://vocab.methodandstructure.com/process-model#State"
rel="rdfs:subClassOf">pm:State</a>

<a href="https://vocab.methodandstructure.com/ibis#Issue"
rel="rdfs:subClassOf">ibis:Issue</a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="Target" class="section" about="[pm:Target]" typeof="owl:Class">

### Target

A Target connects an abstract Goal to a specific Task, budget and
deadline.

The logical separation of a Target from a Goal makes it possible to
speak of a Goal in abstract terms, and generate several equivalent
candidate Tasks, each with one or more candidate Methods, which may
achieve it.

Subclass of:  
<a href="https://vocab.methodandstructure.com/process-model#Goal"
rel="rdfs:subClassOf">pm:Goal</a>

Properties:  
<a href="https://vocab.methodandstructure.com/process-model#anchors"
rev="rdfs:domain">pm:anchors</a>

<a href="https://vocab.methodandstructure.com/process-model#initiates"
rev="rdfs:domain">pm:initiates</a>

<a href="https://vocab.methodandstructure.com/process-model#budget"
rev="rdfs:domain">pm:budget</a>

<a href="https://vocab.methodandstructure.com/process-model#due"
rev="rdfs:domain">pm:due</a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="Action" class="section" about="[pm:Action]" typeof="owl:Class">

### Action

An Action specializes an Event in that it is performed by (at least one)
real, living Person.

Subclass of:  
<a href="http://purl.org/NET/c4dm/event.owl#Event"
rel="rdfs:subClassOf">ev:Event</a>

Disjoint with:  
<a href="https://vocab.methodandstructure.com/process-model#State"
rel="owl:disjointWith">pm:State</a>

Properties:  
<a href="https://vocab.methodandstructure.com/process-model#context"
rev="rdfs:domain">pm:context</a>

<a href="https://vocab.methodandstructure.com/process-model#dependency"
rev="rdfs:domain">pm:dependency</a>

<a href="https://vocab.methodandstructure.com/process-model#performer"
rev="rdfs:domain">pm:performer</a>

<a href="https://vocab.methodandstructure.com/process-model#outcome"
rev="rdfs:domain">pm:outcome</a>

<a href="https://vocab.methodandstructure.com/process-model#variant"
rev="rdfs:domain">pm:variant</a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="Method" class="section" about="[pm:Method]" typeof="owl:Class">

### Method

A method specifies an abstract sequence of events.

This class is provisional. It isn't entirely clear that we need a
distinct Method class, since Tasks and the like could be appropriated as
prototypes of methods.

Subclass of:  
<a href="https://vocab.methodandstructure.com/process-model#Action"
rel="rdfs:subClassOf">pm:Action</a>

Disjoint with:  
<a href="https://vocab.methodandstructure.com/process-model#State"
rel="owl:disjointWith">pm:State</a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="Task" class="section" about="[pm:Task]" typeof="owl:Class">

### Task

A Task specializes an Action in that it has one or more Goals, and
connects a Method of execution with a responsible Person who will carry
it out.

Since pm:Task is a descendant of ev:Event, we can use the ev:time
relation to specify a time:Interval to record the time taken to complete
a task.

Subclass of:  
<a href="https://vocab.methodandstructure.com/process-model#Action"
rel="rdfs:subClassOf">pm:Action</a>

<a href="https://vocab.methodandstructure.com/ibis#Position"
rel="rdfs:subClassOf">ibis:Position</a>

Properties:  
<a href="https://vocab.methodandstructure.com/process-model#achieves"
rev="rdfs:domain">pm:achieves</a>

<a href="https://vocab.methodandstructure.com/process-model#method"
rev="rdfs:domain">pm:method</a>

<a href="https://vocab.methodandstructure.com/process-model#responsible"
rev="rdfs:domain">pm:responsible</a>

<a href="https://vocab.methodandstructure.com/process-model#recipient"
rev="rdfs:domain">pm:recipient</a>

<a href="https://vocab.methodandstructure.com/process-model#status"
rev="rdfs:domain">pm:status</a>

<a href="https://vocab.methodandstructure.com/process-model#subtask"
rev="rdfs:domain">pm:subtask</a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

</div>

<div class="section">

## Properties

The properties in this vocabulary are refined as follows. For brevity,
properties that have no inheritance path have been omitted from this
image:

![](https://vocab.methodandstructure.com/process-model-properties)

<div id="achieves" class="section" about="[pm:achieves]"
typeof="owl:ObjectProperty">

### achieves

The purpose of a task is to achieve a goal. All tasks specified in this
vocabulary must also specify the goal they are intended to achieve.

Domain:  
<a href="https://vocab.methodandstructure.com/process-model#Task"
rel="rdfs:domain">pm:Task</a>

Range:  
<a href="https://vocab.methodandstructure.com/process-model#Goal"
rel="rdfs:range">pm:Goal</a>

Sub-property of:  
<a href="https://vocab.methodandstructure.com/process-model#outcome"
rel="rdfs:subPropertyOf">pm:outcome</a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="anchors" class="section" about="[pm:anchors]"
typeof="owl:ObjectProperty">

### anchors

By anchoring a Goal to a Target, we give it a concrete budget and
deadline.

Domain:  
<a href="https://vocab.methodandstructure.com/process-model#Task"
rel="rdfs:domain">pm:Target</a>

Range:  
<a href="https://vocab.methodandstructure.com/process-model#Goal"
rel="rdfs:range">pm:Goal</a>

Sub-property of:  
<a href="https://vocab.methodandstructure.com/ibis#specializes"
rel="rdfs:subPropertyOf">ibis:specializes</a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="budget" class="section" about="[pm:budget]"
typeof="owl:DatatypeProperty">

### budget

All Targets require a quantitative budget.

It is not clear, prior to implementation, if we should keep the budget
as a raw quantity, or create some kind of resource envelope object.

Domain:  
<a href="https://vocab.methodandstructure.com/process-model#Task"
rel="rdfs:domain">pm:Target</a>

Range:  
<a href="http://www.w3.org/TR/xmlschema-2/#decimal" rel="rdfs:range"
resource="http://www.w3.org/2001/XMLSchema#decimal">xsd:decimal</a>

Cardinality:  
1

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="context" class="section" about="[pm:context]"
typeof="owl:ObjectProperty">

### context

The context of an Action is a State.

The pm:context and pm:outcome properties can be used to chain pm:Actions
together.

Domain:  
<a href="https://vocab.methodandstructure.com/process-model#Action"
rel="rdfs:domain">pm:Action</a>

Range:  
<a href="https://vocab.methodandstructure.com/process-model#State"
rel="rdfs:range">pm:State</a>

Sub-property of:  
<a href="http://purl.org/NET/c4dm/event.owl#factor"
rel="rdfs:subPropertyOf">ev:factor</a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="dependency" class="section" about="[pm:dependency]"
typeof="owl:ObjectProperty">

### dependency

A State the Action depends on to be actionable.

Domain:  
<a href="https://vocab.methodandstructure.com/process-model#Action"
rel="rdfs:domain">pm:Action</a>

Range:  
<a href="https://vocab.methodandstructure.com/process-model#State"
rel="rdfs:range">pm:State</a>

Sub-property of:  
<a href="https://vocab.methodandstructure.com/ontology/ibis/1#suggests"
rel="rdfs:subPropertyOf">ibis:suggests</a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="desires" class="section" about="[pm:desires]"
typeof="owl:ObjectProperty">

### desires

A foaf:Agent may desire a Goal.

Domain:  
<a href="http://xmlns.com/foaf/0.1/Agent"
rel="rdfs:domain">foaf:Agent</a>

Range:  
<a href="https://vocab.methodandstructure.com/process-model#Goal"
rel="rdfs:range">pm:Goal</a>

Sub-property of:  
<a href="https://vocab.methodandstructure.com/ibis#endorses"
rel="rdfs:subPropertyOf">ibis:endorses</a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="due" class="section" about="[pm:due]"
typeof="owl:DatatypeProperty">

### due

All Targets must have a due date.

Domain:  
<a href="https://vocab.methodandstructure.com/process-model#Task"
rel="rdfs:domain">pm:Target</a>

Range:  
<a href="http://www.w3.org/TR/xmlschema-2/#dateTime" rel="rdfs:range"
resource="http://www.w3.org/2001/XMLSchema#dateTime">xsd:dateTime</a>

Cardinality:  
1

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="initiates" class="section" about="[pm:initiates]"
typeof="owl:ObjectProperty owl:FunctionalProperty">

### initiates

A valid target must initiate exactly one task to carry it out.

Domain:  
<a href="https://vocab.methodandstructure.com/process-model#Target"
rel="rdfs:domain">pm:Target</a>

Range:  
<a href="https://vocab.methodandstructure.com/process-model#Task"
rel="rdfs:range">pm:Task</a>

Cardinality:  
1

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="method" class="section" about="[pm:method]"
typeof="owl:ObjectProperty">

### method

All Tasks must identify an associated Method which will be used to
complete them.

Domain:  
<a href="https://vocab.methodandstructure.com/process-model#Task"
rel="rdfs:domain">pm:Task</a>

Range:  
<a href="https://vocab.methodandstructure.com/process-model#Method"
rel="rdfs:range">pm:Method</a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="outcome" class="section" about="[pm:outcome]"
typeof="owl:ObjectProperty">

### outcome

All Actions have an outcome, which is some kind of State.

Domain:  
<a href="https://vocab.methodandstructure.com/process-model#Action"
rel="rdfs:domain">pm:Action</a>

Range:  
<a href="https://vocab.methodandstructure.com/process-model#State"
rel="rdfs:range">pm:State</a>

Sub-property of:  
<a href="http://purl.org/NET/c4dm/event.owl#product"
rel="rdfs:subPropertyOf">ev:product</a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="performer" class="section" about="[pm:performer]"
typeof="owl:ObjectProperty">

### performer

A performer is a real, live (at the time of performance) person who
performs a task.

Sub-property of:  
<a href="http://purl.org/NET/c4dm/event.owl#agent"
rel="rdfs:subPropertyOf">ev:agent</a>

Domain:  
<a href="https://vocab.methodandstructure.com/process-model#Action"
rel="rdfs:domain">pm:Action</a>

Range:  
<a href="http://xmlns.com/foaf/0.1/Person"
rel="rdfs:range">foaf:Person</a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="responsible" class="section" about="[pm:responsible]"
typeof="owl:ObjectProperty">

### responsible

The person responsible for a task may not be the one performing it, but
they are the one accountable for its completion.

Sub-property of:  
<a href="http://purl.org/NET/c4dm/event.owl#agent"
rel="rdfs:subPropertyOf">ev:agent</a>

Domain:  
<a href="https://vocab.methodandstructure.com/process-model#Task"
rel="rdfs:domain">pm:Task</a>

Range:  
<a href="http://xmlns.com/foaf/0.1/Person"
rel="rdfs:range">foaf:Person</a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="recipient" class="section" about="[pm:recipient]"
typeof="owl:ObjectProperty">

### recipient

A recipient of a task is a (real, live at the time of receipt) person
who receives and approves its product or products.

Domain:  
<a href="https://vocab.methodandstructure.com/process-model#Task"
rel="rdfs:domain">pm:Task</a>

Range:  
<a href="http://xmlns.com/foaf/0.1/Person"
rel="rdfs:range">foaf:Person</a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="status" class="section" about="[pm:status]"
typeof="owl:ObjectProperty">

### status

The status of a Task at any instant is a State.

Domain:  
<a href="https://vocab.methodandstructure.com/process-model#Task"
rel="rdfs:domain">pm:Task</a>

Range:  
<a href="https://vocab.methodandstructure.com/process-model#State"
rel="rdfs:range">pm:State</a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="subtask" class="section" about="[pm:subtask]"
typeof="owl:ObjectProperty">

### subtask

This property narrows the domain and range of ev:sub_event to Tasks.

Domain:  
<a href="https://vocab.methodandstructure.com/process-model#Task"
rel="rdfs:domain">pm:Task</a>

Range:  
<a href="https://vocab.methodandstructure.com/process-model#Task"
rel="rdfs:range">pm:Task</a>

Sub-property of:  
<a href="http://purl.org/NET/c4dm/event.owl#sub_event"
rel="rdfs:subPropertyOf">ev:sub_event</a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="variant" class="section" about="[pm:variant]"
typeof="owl:ObjectProperty">

### variant

A variant is an alternate method of performing the same action.

Domain:  
<a href="https://vocab.methodandstructure.com/process-model#Action"
rel="rdfs:domain">pm:Action</a>

Range:  
<a href="https://vocab.methodandstructure.com/process-model#Action"
rel="rdfs:range">pm:Action</a>

Sub-property of:  
<a href="http://purl.org/NET/c4dm/event.owl#sub_event"
rel="rdfs:subPropertyOf">ev:sub_event</a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

</div>

<div class="section">

## Individuals

Currently, the only individuals defined by this vocabulary are those
common, reusable States which can be used as values for
[pm:status](https://vocab.methodandstructure.com/process-model#status).
Most other statuses, such as whether a Task has a responsible person
assigned or a valid Method, should be able to be derived from other
data.

<div id="ABORTED" class="section" about="[pm:ABORTED]"
typeof="pm:State">

### ABORTED

The task is aborted.

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="COMPLETE" class="section" about="[pm:COMPLETE]"
typeof="pm:State">

### COMPLETE

The task is complete.

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="IN-PROGRESS" class="section" about="[pm:IN-PROGRESS]"
typeof="pm:State">

### IN-PROGRESS

The task is in progress.

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="STALLED" class="section" about="[pm:STALLED]"
typeof="pm:State">

### STALLED

The task is stalled.

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

</div>
