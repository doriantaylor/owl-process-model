<div about="#" typeof="owl:Ontology">

Author  
<a href="http://doriantaylor.com/person/dorian-taylor#me"
rel="dct:creator"><span property="foaf:name">Dorian Taylor</span></a>

Version  
0.2.1

Created  
July 22, 2009

Updated  
February 6, 2014

April 6, 2017

March 8, 2020

April 9, 2025

June 10, 2025

Namespace URI  
<a href="https://vocab.methodandstructure.com/process-model#" about="#"
rel="sh:namespace vann:preferredNamespaceUri"><code>https://vocab.methodandstructure.com/process-model#</code></a>

Preferred Namespace Prefix  
`pm`

<span property="rdfs:comment">This vocabulary encodes a model for
expressing generic business processes. Its purpose is to provide a
language and exchange format for software applications designed to
facilitate project management.</span> This vocabulary extends [the IBIS
vocabulary](https://vocab.methodandstructure.com/ibis#) in the natural
fashion that once we have framed an issue and decided to solve it, we
must then specify a method, nominate a person responsible, and allocate
time and material resources to carry out the solution.

</div>

<div id="ch-description" class="section" about="#ch-description">

## Goal, Task, Target

<figure>
<img src="https://vocab.methodandstructure.com/process-model-classes" />
</figure>

In deliberate contravention to the received wisdom of management gurus
and their airport books, as well as countless project management and
to-do applications, this vocabulary separates the concept of a
*qualitative* goal from the task of achieving it. It likewise separates
these two concerns from the allocation of *quantitative* resources, such
as time and money. Finally, it separates a concrete task from the
abstract method by which it is completed.

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

<div id="ch-classes" class="section" about="#ch-classes">

## Classes

The classes in this vocabulary are refined as follows:

<figure>
<img src="https://vocab.methodandstructure.com/process-model-example" />
</figure>

The central concepts,
[`pm:Goal`](https://vocab.methodandstructure.com/process-model#Goal)
(which further refines to
[`pm:Target`](https://vocab.methodandstructure.com/process-model#Target))
and
[`pm:Task`](https://vocab.methodandstructure.com/process-model#Task),
extend the
[`ibis:Issue`](https://vocab.methodandstructure.com/ibis#Issue) and
[`ibis:Position`](https://vocab.methodandstructure.com/ibis#Position)
types, so that goals, tasks and targets can be mixed into, as well as
graduated from, generic collaborative argumentation and decision-making
sessions. Likewise, the
[`pm:Action`](https://vocab.methodandstructure.com/process-model#Action)
class extends <a href="https://www.w3.org/TR/prov-o/#Activity"
rel="dct:references"><code>prov:Activity</code></a> and
<a href="http://motools.sourceforge.net/event/event.html#term_Event"
rel="dct:references"><code>ev:Event</code></a> so that actions and tasks
can be mixed in with generic events on a timeline.

<div id="Goal" class="section" about="[pm:Goal]" typeof="owl:Class">

### `Goal`

A `pm:Goal` extends an `ibis:Issue` by way of being explicitly desired
by a `foaf:Agent`.

A `pm:Goal` is not actionable itself, although a `pm:Task`, which is a
`pm:Action`, must achieve at least one `pm:Goal`. At the time of
observation, `pm:Goal`, like its superclass, `ibis:Issue`, is *binary*:
either resolved or unresolved. This entails that a `pm:Goal` is not
expressed in terms of quantitative results or deadlines. That is the job
of a `pm:Target`.

Subclass of:  
<a href="https://vocab.methodandstructure.com/ibis#Issue"
rel="rdfs:subClassOf"><code>ibis:Issue</code></a>

Properties:  
<a href="https://vocab.methodandstructure.com/process-model#achieved-by"
rev="rdfs:domain"><code>pm:achieved-by</code></a>

<a href="https://vocab.methodandstructure.com/process-model#wanted-by"
rev="rdfs:domain"><code>pm:wanted-by</code></a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="Target" class="section" about="[pm:Target]" typeof="owl:Class">

### `Target`

A `pm:Target` connects a *qualitative* `pm:Goal` to a specific
`pm:Task`, and a concrete, *quantitative* allocation of resources.

The reason why `pm:Target` is distinct from `pm:Goal` is because we can
imagine more than one competing candidate `pm:Task` with different cost
and effort profiles. Without this information, any goal—or target, for
that matter—is merely aspirational. A target is therefore intended to
marry a particular goal to a particular concrete strategy for achieving
it.

Subclass of:  
<a href="https://vocab.methodandstructure.com/process-model#Goal"
rel="rdfs:subClassOf"><code>pm:Goal</code></a>

Properties:  
<a href="https://vocab.methodandstructure.com/process-model#anchors"
rev="rdfs:domain"><code>pm:anchors</code></a>

<a href="https://vocab.methodandstructure.com/process-model#budget"
rev="rdfs:domain"><code>pm:budget</code></a>

<a href="https://vocab.methodandstructure.com/process-model#due"
rev="rdfs:domain"><code>pm:due</code></a>

<a href="https://vocab.methodandstructure.com/process-model#initiates"
rev="rdfs:domain"><code>pm:initiates</code></a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="Action" class="section" about="[pm:Action]" typeof="owl:Class">

### `Action`

A `pm:Action` specializes an `ev:Event` in that it is performed by (at
least one) real, living `foaf:Person`.

Subclass of:  
<a href="https://www.w3.org/TR/prov-o/#Activity" rel="rdfs:subClassOf"
resource="prov:Activity"><code>prov:Activity</code></a>

<a href="https://motools.sourceforge.net/event/event.html#term_Event"
rel="rdfs:subClassOf" resource="ev:Event"><code>ev:Event</code></a>

Disjoint with:  
<a href="https://vocab.methodandstructure.com/ibis#State"
rel="owl:disjointWith"><code>ibis:State</code></a>

Properties:  
<a href="https://vocab.methodandstructure.com/process-model#context"
rev="rdfs:domain"><code>pm:context</code></a>

<a href="https://vocab.methodandstructure.com/process-model#dependency"
rev="rdfs:domain"><code>pm:dependency</code></a>

<a href="https://vocab.methodandstructure.com/process-model#performer"
rev="rdfs:domain"><code>pm:performer</code></a>

<a href="https://vocab.methodandstructure.com/process-model#outcome"
rev="rdfs:domain"><code>pm:outcome</code></a>

<a href="https://vocab.methodandstructure.com/process-model#variant"
rev="rdfs:domain"><code>pm:variant</code></a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="Method" class="section" about="[pm:Method]" typeof="owl:Class">

### `Method`

A method specifies an abstract sequence of events.

This class is provisional. It isn't entirely clear that we need a
distinct `pm:Method` class, since `pm:Tasks` and the like could be
appropriated as prototypes of methods.

Subclass of:  
<a href="https://vocab.methodandstructure.com/process-model#Action"
rel="rdfs:subClassOf"><code>pm:Action</code></a>

Disjoint with:  
<a href="https://vocab.methodandstructure.com/ibis#State"
rel="owl:disjointWith"><code>ibis:State</code></a>

Properties:  
<a href="https://vocab.methodandstructure.com/process-model#instance"
rev="rdfs:domain"><code>pm:instance</code></a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="Task" class="section" about="[pm:Task]" typeof="owl:Class">

### `Task`

A `pm:Task` specializes a `pm:Action` in that it has one or more
`pm:Goal`, and connects a `pm:Method` of execution with a responsible
`foaf:Person` who will carry it out.

Since `pm:Task` is a descendant of `ev:Event`, we can use the ev:time
relation to specify a time:Interval to record the time taken to complete
a task.

Subclass of:  
<a href="https://vocab.methodandstructure.com/process-model#Action"
rel="rdfs:subClassOf"><code>pm:Action</code></a>

<a href="https://vocab.methodandstructure.com/ibis#Position"
rel="rdfs:subClassOf"><code>ibis:Position</code></a>

Properties:  
<a href="https://vocab.methodandstructure.com/process-model#achieves"
rev="rdfs:domain"><code>pm:achieves</code></a>

<a href="https://vocab.methodandstructure.com/process-model#method"
rev="rdfs:domain"><code>pm:method</code></a>

<a href="https://vocab.methodandstructure.com/process-model#responsible"
rev="rdfs:domain"><code>pm:responsible</code></a>

<a href="https://vocab.methodandstructure.com/process-model#recipient"
rev="rdfs:domain"><code>pm:recipient</code></a>

<a href="https://vocab.methodandstructure.com/process-model#status"
rev="rdfs:domain"><code>pm:status</code></a>

<a href="https://vocab.methodandstructure.com/process-model#subtask"
rev="rdfs:domain"><code>pm:subtask</code></a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

</div>

<div id="ch-properties" class="section" about="#ch-properties">

## Properties

The properties in this vocabulary are refined as follows:

<figure>
<img
src="https://vocab.methodandstructure.com/process-model-properties" />
</figure>

<div id="sec-domain-state" class="section">

### State-Related

<div id="contextualizes" class="section" about="[pm:contextualizes]"
typeof="owl:ObjectProperty">

#### `contextualizes`

An `ibis:State` lends context to a `pm:Action`.

Domain:  
<a href="https://vocab.methodandstructure.com/ibis#State"
rel="rdfs:domain"><code>ibis:State</code></a>

Range:  
<a href="https://vocab.methodandstructure.com/process-model#Action"
rel="rdfs:range"><code>pm:Action</code></a>

Inverse of:  
<a href="https://vocab.methodandstructure.com/process-model#context"
rel="owl:inverseOf"><code>pm:context</code></a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="process" class="section" about="[pm:process]"
typeof="owl:ObjectProperty">

#### `process`

When an `ibis:State` is the outcome of a `pm:Action`.

Domain:  
<a href="https://vocab.methodandstructure.com/ibis#State"
rel="rdfs:domain"><code>ibis:State</code></a>

Range:  
<a href="https://vocab.methodandstructure.com/process-model#Action"
rel="rdfs:range"><code>pm:Action</code></a>

Sub-property of:  
<a href="https://www.w3.org/TR/prov-o/#wasGeneratedBy"
rel="rdfs:subPropertyOf"
resource="prov:wasGeneratedBy"><code>prov:wasGeneratedBy</code></a>

Inverse of:  
<a href="https://vocab.methodandstructure.com/process-model#outcome"
rel="owl:inverseOf"><code>pm:outcome</code></a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

</div>

<div id="sec-domain-goal" class="section">

### Goal-Related

<div id="achieved-by" class="section" about="[pm:achieved-by]"
typeof="owl:ObjectProperty">

#### `achieved-by`

A `pm:Goal` is achieved by at least one candidate `pm:Task`.

Domain:  
<a href="https://vocab.methodandstructure.com/process-model#Goal"
rel="rdfs:domain"><code>pm:Goal</code></a>

Range:  
<a href="https://vocab.methodandstructure.com/process-model#Task"
rel="rdfs:range"><code>pm:Task</code></a>

Sub-property of:  
<a href="https://www.w3.org/TR/skos-reference/#semantic-relations"
rel="rdfs:subPropertyOf"
resource="skos:semanticRelation"><code>skos:semanticRelation</code></a>

Inverse of:  
<a href="https://vocab.methodandstructure.com/process-model#achieves"
rel="owl:inverseOf"><code>pm:achieves</code></a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="anchored-by" class="section" about="[pm:anchored-by]"
typeof="owl:ObjectProperty">

#### `anchored-by`

A `pm:Goal` is anchored to reality by a `pm:Target`.

Domain:  
<a href="https://vocab.methodandstructure.com/process-model#Goal"
rel="rdfs:domain"><code>pm:Goal</code></a>

Range:  
<a href="https://vocab.methodandstructure.com/process-model#Task"
rel="rdfs:range"><code>pm:Target</code></a>

Sub-property of:  
<a href="https://vocab.methodandstructure.com/ibis#generalizes"
rel="rdfs:subPropertyOf"><code>ibis:generalizes</code></a>

Inverse of:  
<a href="https://vocab.methodandstructure.com/process-model#anchors"
rel="owl:inverseOf"><code>pm:anchors</code></a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="expires" class="section" about="[pm:expires]"
typeof="owl:DatatypeProperty">

#### `expires`

This serves as a hard expiry date for a given `pm:Goal`, such that after
it elapses, any valuation ascribed to the goal goes to zero.

You would use `pm:expires` (ideally in conjunction with `pm:valuation`)
to express a window of opportunity.

Domain:  
<a href="https://vocab.methodandstructure.com/process-model#Goal"
rel="rdfs:domain">pm:Goal</a>

Range:  
<a href="http://www.w3.org/TR/xmlschema-2/#dateTime" rel="rdfs:range"
resource="xsd:dateTime"><code>xsd:dateTime</code></a>

Cardinality:  
`1`

See also:  
<a href="https://www.youtube.com/watch?v=fiSjxr8xG6A"
rel="rdfs:seeAlso">Timing test for methodology talk</a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="valuation" class="section" about="[pm:valuation]"
typeof="owl:DatatypeProperty">

#### `valuation`

A `pm:Goal` can be ascribed a quantity that represents, in some
unspecified unit, the marginal, potentially discounted value of
achieving the goal.

This property is provisional, and if it remains, will be relegated to a
computed outcome from some depreciation function, which has yet to be
defined.

Domain:  
<a href="https://vocab.methodandstructure.com/process-model#Goal"
rel="rdfs:domain"><code>pm:Goal</code></a>

Range:  
<a href="http://www.w3.org/TR/xmlschema-2/#decimal" rel="rdfs:range"
resource="xsd:decimal"><code>xsd:decimal</code></a>

Cardinality:  
`1`

See also:  
<a href="https://vocab.methodandstructure.com/process-model#ARQ"
rel="rdfs:seeAlso"><code>pm:ARQ</code></a>

<a href="https://www.youtube.com/watch?v=fiSjxr8xG6A"
rel="rdfs:seeAlso">Timing test for methodology talk</a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="wanted-by" class="section" about="[pm:wanted-by]"
typeof="owl:ObjectProperty">

#### `wanted-by`

The identifying feature of a `pm:Goal` is that somebody wants it to
happen.

Domain:  
<a href="https://vocab.methodandstructure.com/process-model#Goal"
rel="rdfs:domain"><code>pm:Goal</code></a>

Range:  
<a href="http://xmlns.com/foaf/spec/#term_Agent" rel="rdfs:range"
resource="foaf:Agent"><code>foaf:Agent</code></a>

Sub-property of:  
<a href="https://vocab.methodandstructure.com/ibis#endorsed-by"
rel="rdfs:subPropertyOf"><code>ibis:endorsed-by</code></a>

Inverse of:  
<a href="https://vocab.methodandstructure.com/process-model#wants"
rel="owl:inverseOf"><code>pm:wants</code></a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

</div>

<div id="sec-domain-target" class="section">

### Target-Related

<div id="anchors" class="section" about="[pm:anchors]"
typeof="owl:ObjectProperty">

#### `anchors`

By anchoring a `pm:Goal` to a `pm:Target`, we give it a concrete budget
and deadline.

Domain:  
<a href="https://vocab.methodandstructure.com/process-model#Task"
rel="rdfs:domain"><code>pm:Target</code></a>

Range:  
<a href="https://vocab.methodandstructure.com/process-model#Goal"
rel="rdfs:range"><code>pm:Goal</code></a>

Sub-property of:  
<a href="https://vocab.methodandstructure.com/ibis#specializes"
rel="rdfs:subPropertyOf"><code>ibis:specializes</code></a>

Inverse of:  
<a href="https://vocab.methodandstructure.com/process-model#anchored-by"
rel="owl:inverseOf"><code>pm:anchored-by</code></a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="budget" class="section" about="[pm:budget]"
typeof="owl:DatatypeProperty">

#### `budget`

Every `pm:Target` has to have a quantitative budget of resources
assigned to it. It need not be denominated in currency (e.g. it could be
person-hours).

Domain:  
<a href="https://vocab.methodandstructure.com/process-model#Target"
rel="rdfs:domain"><code>pm:Target</code></a>

Range:  
<a href="http://www.w3.org/TR/xmlschema-2/#decimal" rel="rdfs:range"
resource="xsd:decimal"><code>xsd:decimal</code></a>

Sub-property of:  
<a href="https://vocab.methodandstructure.com/process-model#valuation"
rel="rdfs:subPropertyOf"><code>pm:valuation</code></a>

Cardinality:  
`1`

See also:  
<a href="https://vocab.methodandstructure.com/process-model#ARQ"
rel="rdfs:seeAlso"><code>pm:ARQ</code></a>

<a href="https://www.youtube.com/watch?v=fiSjxr8xG6A"
rel="rdfs:seeAlso">Timing test for methodology talk</a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="due" class="section" about="[pm:due]"
typeof="owl:DatatypeProperty">

#### `due`

The due date of a `pm:Target` is a conventional deadline.

I am contemplating changing this to `pm:expires` to refer to the
value-based process model.

Domain:  
<a href="https://vocab.methodandstructure.com/process-model#Target"
rel="rdfs:domain">pm:Target</a>

Range:  
<a href="http://www.w3.org/TR/xmlschema-2/#dateTime" rel="rdfs:range"
resource="xsd:dateTime"><code>xsd:dateTime</code></a>

Sub-property of:  
<a href="https://vocab.methodandstructure.com/process-model#expires"
rel="rdfs:subPropertyOf"><code>pm:expires</code></a>

Cardinality:  
`1`

See also:  
<a href="https://www.youtube.com/watch?v=fiSjxr8xG6A"
rel="rdfs:seeAlso">Timing test for methodology talk</a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="initiates" class="section" about="[pm:initiates]"
typeof="owl:ObjectProperty owl:FunctionalProperty">

#### `initiates`

A valid `pm:Target` must initiate exactly one `pm:Task` to carry it out.

Domain:  
<a href="https://vocab.methodandstructure.com/process-model#Target"
rel="rdfs:domain"><code>pm:Target</code></a>

Range:  
<a href="https://vocab.methodandstructure.com/process-model#Task"
rel="rdfs:range"><code>pm:Task</code></a>

Sub-property of:  
<a href="https://vocab.methodandstructure.com/ibis#response"
rel="rdfs:subPropertyOf"><code>ibis:response</code></a>

Inverse of:  
<a
href="https://vocab.methodandstructure.com/process-model#initiated-by"
rel="owl:inverseOf"><code>pm:initiated-by</code></a>

Cardinality:  
`1`

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

</div>

<div id="sec-domain-action" class="section">

### Action-Related

<div id="context" class="section" about="[pm:context]"
typeof="owl:ObjectProperty">

#### `context`

A `pm:Action` may have an `ibis:State` as a context.

The `pm:context` and `pm:outcome` properties can be used to chain one
`pm:Action` to another.

Domain:  
<a href="https://vocab.methodandstructure.com/process-model#Action"
rel="rdfs:domain"><code>pm:Action</code></a>

Range:  
<a href="https://vocab.methodandstructure.com/ibis#State"
rel="rdfs:range"><code>ibis:State</code></a>

Sub-property of:  
<a href="https://www.w3.org/TR/skos-reference/#semantic-relations"
rel="rdfs:subPropertyOf"
resource="skos:semanticRelation"><code>skos:semanticRelation</code></a>

<a href="https://www.w3.org/TR/prov-o/#used" rel="rdfs:subPropertyOf"
resource="prov:used"><code>prov:used</code></a>

<a href="https://motools.sourceforge.net/event/event.html#term_factor"
rel="rdfs:subPropertyOf" resource="ev:factor"><code>ev:factor</code></a>

Inverse of:  
<a
href="https://vocab.methodandstructure.com/process-model#contextualizes"
rel="owl:inverseOf"><code>pm:contextualizes</code></a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="dependency" class="section" about="[pm:dependency]"
typeof="owl:ObjectProperty">

#### `dependency`

An `ibis:State` the `pm:Action` depends on to be actionable.

Domain:  
<a href="https://vocab.methodandstructure.com/process-model#Action"
rel="rdfs:domain"><code>pm:Action</code></a>

Range:  
<a href="https://vocab.methodandstructure.com/ibis#State"
rel="rdfs:range"><code>ibis:State</code></a>

Sub-property of:  
<a href="https://vocab.methodandstructure.com/ibis#suggests"
rel="rdfs:subPropertyOf"><code>ibis:suggests</code></a>

Inverse of:  
<a
href="https://vocab.methodandstructure.com/process-model#dependency-of"
rel="owl:inverseOf"><code>pm:dependency-of</code></a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="involves" class="section" about="[pm:involves]"
typeof="owl:ObjectProperty">

#### `involves`

A `pm:Action` may involve one or more `foaf:Agent`.

Domain:  
<a href="https://vocab.methodandstructure.com/process-model#Action"
rel="rdfs:domain"><code>pm:Action</code></a>

Range:  
<a href="http://xmlns.com/foaf/spec/#term_Agent" rel="rdfs:range"
resource="foaf:Agent"><code>foaf:Agent</code></a>

Inverse of:  
<a href="https://vocab.methodandstructure.com/process-model#involved-in"
rel="owl:inverseOf"><code>pm:involved-in</code></a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="method" class="section" about="[pm:method]"
typeof="owl:ObjectProperty">

#### `method`

A `pm:Action` can identify an associated `pm:Method` which will be used
to complete it.

Domain:  
<a href="https://vocab.methodandstructure.com/process-model#Action"
rel="rdfs:domain"><code>pm:Action</code></a>

Range:  
<a href="https://vocab.methodandstructure.com/process-model#Method"
rel="rdfs:range"><code>pm:Method</code></a>

Inverse of:  
<a href="https://vocab.methodandstructure.com/process-model#instance"
rel="owl:inverseOf"><code>pm:instance</code></a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="outcome" class="section" about="[pm:outcome]"
typeof="owl:ObjectProperty">

#### `outcome`

Every `pm:Action` has an outcome, which is some kind of `ibis:State`.

Sub-property of:  
<a href="https://www.w3.org/TR/prov-o/#generated"
rel="rdfs:subPropertyOf"
resource="prov:generated"><code>prov:generated</code></a>

<a href="https://motools.sourceforge.net/event/event.html#term_product"
rel="rdfs:subPropertyOf"
resource="ev:product"><code>ev:product</code></a>

Domain:  
<a href="https://vocab.methodandstructure.com/process-model#Action"
rel="rdfs:domain"><code>pm:Action</code></a>

Range:  
<a href="https://vocab.methodandstructure.com/ibis#State"
rel="rdfs:range"><code>ibis:State</code></a>

Inverse of:  
<a href="https://vocab.methodandstructure.com/process-model#outcome"
rel="owl:inverseOf"><code>pm:outcome</code></a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="performer" class="section" about="[pm:performer]"
typeof="owl:ObjectProperty">

#### `performer`

A performer is a real, live (at the time of performance) person who
performs a task.

Domain:  
<a href="https://vocab.methodandstructure.com/process-model#Action"
rel="rdfs:domain"><code>pm:Action</code></a>

Range:  
<a href="http://xmlns.com/foaf/spec/#term_Person" rel="rdfs:range"
resource="foaf:Person"><code>foaf:Person</code></a>

Sub-property of:  
<a href="https://vocab.methodandstructure.com/process-model#involves"
rel="rdfs:subPropertyOf"><code>pm:involves</code></a>

<a href="https://www.w3.org/TR/prov-o/#wasAttributedTo"
rel="rdfs:subPropertyOf"
resource="prov:wasAttributedTo"><code>prov:wasAttributedTo</code></a>

<a href="https://motools.sourceforge.net/event/event.html#term_agent"
rel="rdfs:subPropertyOf" resource="ev:agent"><code>ev:agent</code></a>

Inverse of:  
<a href="https://vocab.methodandstructure.com/process-model#performs"
rel="owl:inverseOf"><code>pm:performs</code></a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="variant" class="section" about="[pm:variant]"
typeof="owl:ObjectProperty owl:SymmetricProperty">

#### `variant`

A variant is an alternate method of performing the same action.

Domain:  
<a href="https://vocab.methodandstructure.com/process-model#Action"
rel="rdfs:domain"><code>pm:Action</code></a>

Range:  
<a href="https://vocab.methodandstructure.com/process-model#Action"
rel="rdfs:range"><code>pm:Action</code></a>

Sub-property of:  
<a href="https://www.w3.org/TR/skos-reference/#semantic-relations"
rel="rdfs:subPropertyOf"
resource="skos:related"><code>skos:related</code></a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

</div>

<div id="sec-domain-method" class="section">

### Method-Related

<div id="instance" class="section" about="[pm:instance]"
typeof="owl:ObjectProperty">

#### `instance`

A `pm:Action` is an instance of a `pm:Method`.

Domain:  
<a href="https://vocab.methodandstructure.com/process-model#Method"
rel="rdfs:domain"><code>pm:Method</code></a>

Range:  
<a href="https://vocab.methodandstructure.com/process-model#Action"
rel="rdfs:range"><code>pm:Action</code></a>

Inverse of:  
<a href="https://vocab.methodandstructure.com/process-model#method"
rel="owl:inverseOf"><code>pm:method</code></a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

</div>

<div id="sec-domain-task" class="section">

### Task-Related

<div id="achieves" class="section" about="[pm:achieves]"
typeof="owl:ObjectProperty">

#### `achieves`

The purpose of a task is to achieve a goal. Every `pm:Task` specified in
this vocabulary must also specify the `pm:Goal` they are intended to
achieve.

Domain:  
<a href="https://vocab.methodandstructure.com/process-model#Task"
rel="rdfs:domain"><code>pm:Task</code></a>

Range:  
<a href="https://vocab.methodandstructure.com/process-model#Goal"
rel="rdfs:range"><code>pm:Goal</code></a>

Sub-property of:  
<a href="https://www.w3.org/TR/skos-reference/#semantic-relations"
rel="rdfs:subPropertyOf"
resource="skos:semanticRelation"><code>skos:semanticRelation</code></a>

<a href="https://vocab.methodandstructure.com/process-model#outcome"
rel="rdfs:subPropertyOf"><code>pm:outcome</code></a>

Inverse of:  
<a href="https://vocab.methodandstructure.com/process-model#achieved-by"
rel="owl:inverseOf"><code>pm:achieved-by</code></a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="initiated-by" class="section" about="[pm:initiated-by]"
typeof="owl:ObjectProperty owl:InverseFunctionalProperty">

#### `initiated-by`

This connects a selected `pm:Task` to the `pm:Target` that initiated it.

Domain:  
<a href="https://vocab.methodandstructure.com/process-model#Task"
rel="rdfs:domain"><code>pm:Task</code></a>

Range:  
<a href="https://vocab.methodandstructure.com/process-model#Target"
rel="rdfs:range"><code>pm:Target</code></a>

Sub-property of:  
<a href="https://vocab.methodandstructure.com/ibis#responds-to"
rel="rdfs:subPropertyOf"><code>ibis:responds-to</code></a>

Inverse of:  
<a href="https://vocab.methodandstructure.com/process-model#initiates"
rel="owl:inverseOf"><code>pm:initiates</code></a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="recipient" class="section" about="[pm:recipient]"
typeof="owl:ObjectProperty">

#### `recipient`

A recipient of a task is a (real, live at the time of receipt) person
who receives and approves its product or products.

Domain:  
<a href="https://vocab.methodandstructure.com/process-model#Task"
rel="rdfs:domain"><code>pm:Task</code></a>

Range:  
<a href="http://xmlns.com/foaf/spec/#term_Person" rel="rdfs:range"
resource="foaf:Person"><code>foaf:Person</code></a>

Inverse of:  
<a
href="https://vocab.methodandstructure.com/process-model#responsible-for"
rel="owl:inverseOf"><code>pm:responsible-for</code></a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="responsible" class="section" about="[pm:responsible]"
typeof="owl:ObjectProperty">

#### `responsible`

The person responsible for a task may not be the one performing it, but
they are the one accountable for its completion.

Sub-property of:  
<a href="https://motools.sourceforge.net/event/event.html#term_agent"
rel="rdfs:subPropertyOf" resource="ev:agent"><code>ev:agent</code></a>

Domain:  
<a href="https://vocab.methodandstructure.com/process-model#Task"
rel="rdfs:domain"><code>pm:Task</code></a>

Range:  
<a href="http://xmlns.com/foaf/spec/#term_Person" rel="rdfs:range"
resource="foaf:Person"><code>foaf:Person</code></a>

Inverse of:  
<a
href="https://vocab.methodandstructure.com/process-model#responsible-for"
rel="owl:inverseOf"><code>pm:responsible-for</code></a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="status" class="section" about="[pm:status]"
typeof="owl:ObjectProperty">

#### `status`

The status of a Task at any instant is a State.

Domain:  
<a href="https://vocab.methodandstructure.com/process-model#Task"
rel="rdfs:domain"><code>pm:Task</code></a>

Range:  
<a href="https://vocab.methodandstructure.com/ibis#State"
rel="rdfs:range"><code>ibis:State</code></a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="subtask" class="section" about="[pm:subtask]"
typeof="owl:ObjectProperty">

#### `subtask`

This property narrows the domain and range of `ev:sub_event` to
`pm:Task`.

Domain:  
<a href="https://vocab.methodandstructure.com/process-model#Task"
rel="rdfs:domain"><code>pm:Task</code></a>

Range:  
<a href="https://vocab.methodandstructure.com/process-model#Task"
rel="rdfs:range"><code>pm:Task</code></a>

Sub-property of:  
<a href="https://vocab.methodandstructure.com/ibis#generalizes"
rel="rdfs:subPropertyOf"><code>ibis:generalizes</code></a>

<a
href="https://motools.sourceforge.net/event/event.html#term_sub_event"
rel="rdfs:subPropertyOf"
resource="ev:sub_event"><code>ev:sub_event</code></a>

Inverse of:  
<a href="https://vocab.methodandstructure.com/process-model#supertask"
rel="owl:inverseOf"><code>pm:supertask</code></a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="supertask" class="section" about="[pm:supertask]"
typeof="owl:ObjectProperty">

#### `supertask`

Domain:  
<a href="https://vocab.methodandstructure.com/process-model#Task"
rel="rdfs:domain"><code>pm:Task</code></a>

Range:  
<a href="https://vocab.methodandstructure.com/process-model#Task"
rel="rdfs:range"><code>pm:Task</code></a>

Sub-property of:  
<a href="https://vocab.methodandstructure.com/ibis#specializes"
rel="rdfs:subPropertyOf"><code>ibis:specializes</code></a>

Inverse of:  
<a href="https://vocab.methodandstructure.com/process-model#subtask"
rel="owl:inverseOf"><code>pm:subtask</code></a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

</div>

<div class="section">

### Agent-Related

<div id="involved-in" class="section" about="[pm:involved-in]"
typeof="owl:ObjectProperty">

#### `involved-in`

A `foaf:Agent` may be involved in a `pm:Task`

Domain:  
<a href="https://vocab.methodandstructure.com/process-model#Task"
rel="rdfs:domain"><code>pm:Task</code></a>

Range:  
<a href="http://xmlns.com/foaf/spec/#term_Agent" rel="rdfs:range"
resource="foaf:Agent"><code>foaf:Agent</code></a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="performs" class="section" about="[pm:performs]"
typeof="owl:ObjectProperty">

#### `performs`

Domain:  
<a href="http://xmlns.com/foaf/spec/#term_Person" rel="rdfs:domain"
resource="foaf:Person"><code>foaf:Person</code></a>

Range:  
<a href="https://vocab.methodandstructure.com/process-model#Action"
rel="rdfs:range"><code>pm:Action</code></a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="recipient-of" class="section" about="[pm:recipient-of]"
typeof="owl:ObjectProperty">

#### `recipient-of`

Domain:  
<a href="http://xmlns.com/foaf/spec/#term_Person" rel="rdfs:domain"
resource="foaf:Person"><code>foaf:Person</code></a>

Range:  
<a href="https://vocab.methodandstructure.com/process-model#Task"
rel="rdfs:range"><code>pm:Task</code></a>

Inverse of:  
<a href="https://vocab.methodandstructure.com/process-model#recipient"
rel="owl:inverseOf"><code>pm:recipient</code></a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="responsible-for" class="section" about="[pm:responsible-for]"
typeof="owl:ObjectProperty">

#### `responsible-for`

Domain:  
<a href="http://xmlns.com/foaf/spec/#term_Person" rel="rdfs:domain"
resource="foaf:Person"><code>foaf:Person</code></a>

Range:  
<a href="https://vocab.methodandstructure.com/process-model#Task"
rel="rdfs:range"><code>pm:Task</code></a>

Inverse of:  
<a href="https://vocab.methodandstructure.com/process-model#responsible"
rel="owl:inverseOf"><code>pm:responsible</code></a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="wants" class="section" about="[pm:wants]"
typeof="owl:ObjectProperty">

#### `wants`

A `foaf:Agent` may want a `pm:Goal`.

Domain:  
<a href="http://xmlns.com/foaf/spec/#term_Agent" rel="rdfs:domain"
resource="foaf:Agent"><code>foaf:Agent</code></a>

Range:  
<a href="https://vocab.methodandstructure.com/process-model#Goal"
rel="rdfs:range"><code>pm:Goal</code></a>

Sub-property of:  
<a href="https://vocab.methodandstructure.com/ibis#endorses"
rel="rdfs:subPropertyOf"><code>ibis:endorses</code></a>

Inverse of:  
<a href="https://vocab.methodandstructure.com/process-model#wanted-by"
rel="owl:inverseOf"><code>pm:wanted-by</code></a>

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

</div>

</div>

<div id="ch-individuals" class="section" about="#ch-individuals">

## Data Types

<div id="ARQ" class="section" about="[pm:ARQ]" typeof="rdfs:Datatype">

#### `ARQ`

This is a stand-in datatype for an <span class="dfn">abstract resource
quantity</span>. Its purpose is to differentiate from `xsd:decimal`,
which is indistinguishable from other real numbers.

An abstract resource quantity can mean anything you want: dollars,
practitioner-hours, something else entirely. Treat it as the base unit
of account for resource planning decisions.

Subclass of:  
<a href="https://www.w3.org/TR/xmlschema11-2/#decimal"
rel="rdfs:subClassOf"
resource="xsd:decimal"><code>xsd:decimal</code></a>

See also:  
<a href="https://en.wikipedia.org/wiki/Unidade_real_de_valor"
rel="rdfs:seeAlso">Unidade real de valor</a> (URV), a “non-monetary
reference currency” introduced in the 1990s to curb hyperinflation in
Brazil.

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

</div>

<div id="ch-individuals" class="section" about="#ch-individuals">

## Individuals

Currently, the only individuals defined by this vocabulary are those
common, reusable States which can be used as values for
[pm:status](https://vocab.methodandstructure.com/process-model#status).
Most other statuses, such as whether a Task has a responsible person
assigned or a valid Method, should be able to be derived from other
data.

<div id="ABORTED" class="section" about="[pm:ABORTED]"
typeof="ibis:State">

### `ABORTED`

The task is aborted.

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="COMPLETE" class="section" about="[pm:COMPLETE]"
typeof="ibis:State">

### `COMPLETE`

The task is complete.

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="IN-PROGRESS" class="section" about="[pm:IN-PROGRESS]"
typeof="ibis:State">

### `IN-PROGRESS`

The task is in progress.

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="STALLED" class="section" about="[pm:STALLED]"
typeof="ibis:State">

### `STALLED`

The task is stalled.

<a href="https://vocab.methodandstructure.com/process-model#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

</div>

<div id="ch-references" class="section" about="#ch-references">

## References

This process model vocabulary connects and extends the following
vocabularies:

- <a href="https://vocab.methodandstructure.com/ibis#"
  rel="owl:imports">The IBIS (bis) Vocabulary</a>
- <a href="https://www.w3.org/TR/prov-o/" rel="owl:imports"
  resource="http://www.w3.org/ns/prov#">PROV-O: The PROV Ontology</a>
- <a href="https://motools.sourceforge.net/event/event.html"
  rel="owl:imports" resource="http://purl.org/NET/c4dm/event.owl#">The
  Event Ontology</a>
- <a href="https://www.w3.org/TR/skos-reference/" rel="owl:imports"
  resource="http://www.w3.org/2004/02/skos/core#">Simple Knowledge
  Organization System</a>

</div>
