Oladapo Oyelaja  
02 September 2026

# A Declarative Interval-Scoped Notation System for Hybrid Continuous-Discrete Streams

I have been programming since I was eight or nine, and over the years, I have become accustomed to thinking about problems not only in terms of whether a solution works, but also by the means of which it does. That distinction followed me into an AP Calculus BC class, where I found myself trying to rationalize the assignments placed in front of me. The reasoning and intentions behind the processes seemed reasonable, but the methods by which they were conveyed did not. “That works, but there’s surely a better way to convey this,” I thought to myself repeatedly.  
Mathematical Notation and Programming Languages are identical ontological pursuits: they are man’s attempt to abstract the world around us. Stripped of their instruments and representations, both disciplines perform the same fundamental operation–standardizing the irreducible complexity of reality and distilling chaos into coherent, deterministic structures. Why, then, do two fields confronting the same fundamental problem–continuity, or rather, continuous change–arrive at such different solutions? Mathematics traditionally approaches the problem through increasingly sophisticated abstractions, extending algebra with limits, calculus and analysis to describe what cannot be captured by algebra alone. Computer science faces the inverse problem, attempting to represent a continuous world within inherently discrete computational machinery. One constructs abstractions capable of reasoning about continuity; the other approximates continuity through discrete representations.  
Yet perhaps this divergence is itself a consequence of the notational formalisms through which we represent these phenomena. If both fields ultimately confront the same tension between continuous phenomena and discrete representation, perhaps there exists a lower-level notational framework from which both approaches can be derived. Such a framework would not only bridge mathematics and computer science, but potentially reveal their respective formalisms as different expressions of a deeper underlying structure.

# I. Architecture and Primitives

The proposed syntactic dictionary of the aforementioned notation is as follows:

* The subscript *t* serves as a universal anchor for continuous change. Although most intuitively interpreted as time, it is not inherently temporal and may represent any continuous trajectory or axis of progression.  
* “Streams”, denoted by curly brackets, are sequential abstractions defined over *t*. A stream may originate at any point along *t*, trace a continuous path, and yield a value upon evaluation at any point along that path.  
* “Gradients” (⇒) are operators that denote an infinitesimal relationship between points along *t*.  
  * The gradient operator may be omitted entirely to represent purely discrete points in time. When the gradient (⇒) is absent, the state does not trace a continuous path over an interval; instead, it evaluates strictly at a single, isolated coordinate along the axis of progression. This allows the notation to seamlessly mix both continuous trajectories and instantaneous, discrete events within the same framework.

The logical behavior of the proposed notation is governed by the following rules:

* A stream is a passive path until it is explicitly queried. It does not actively push updates; instead, it outputs a value only when evaluated at a specific point along the progression axis.  
* Precedence within a stream is strictly ordered, such that each successive entry of *t* supersedes its predecessors in cases of overlap. This behavior is analogous to the cascading precedence model of CSS, where competing declarations are resolved according to an established order of precedence.  
* Streams expose structural discontinuities explicitly rather than enforcing mandatory continuity. While successive states can transition seamlessly when boundaries match, this notation allows for deliberate gaps along the progression axis. Because each evaluation window is strictly bound to its declared coordinates, any discontinuity or unhandled interval becomes immediately visible and structurally apparent rather than hidden within the system logic.  
* Nested streams exhibit top-down temporal encapsulation, meaning that inner sub-streams automatically inherit the evaluation boundaries of their parent wrapper. Rather than declaring independent lifetimes–or assuming none exist–the operational windows of these child components are structurally bound by the outer interval context, preventing them from outliving or escaping their parent scope.  
* To guarantee total temporal coverage, the final transition must act as a terminal sink that explicitly routes the progression toward an infinite horizon (∞ₜ). This exhaustive termination structure ensures the system never enters an undefined or open-ended future state once all discrete structural changes are completed.

# II. Case Study: Ball Kinematics and State Transitions

| velocity(xₜ, v) { 	\[xₜ ⇒ xₜ \+ ∞ₜ\] : v, } mass(xₜ, m) { 	\[xₜ ⇒ xₜ \+ ∞ₜ\] : m, } ball(xₜ) { 	\[xₜ ⇒ xₜ \+ 2ₜ\] : { 		velocity(xₜ, falling), 	}, 	\[xₜ \+ 2ₜ\] : { 		velocity(xₜ, stopped), 	}, 	\[xₜ \+ 2ₜ ⇒ xₜ \+ ∞ₜ\] : { 		velocity(xₜ, speed), 		mass(xₜ, empty), 	}, } |
| :---- |

# III. Behavioral Breakdown and Evaluation Logic

It is important to note a few distinctive emergent properties as illustrated in the aforementioned case study:

* Top-Down Scope Inheritance: The nested **velocity** and **mass** streams do not require independent timeline tracking. By placing them inside the curly brackets following the “**:**” operator, they automatically inherit the exact boundary context defined by their parent interval container.  
* Discrete Event Isolation: In the second block, the gradient operator (⇒) is completely omitted from the interval brackets, leaving only the isolated coordinate “\[xₜ \+ 2ₜ\].” This explicitly denotes an instantaneous, discrete change (the impact) rather than a continuous duration.  
* Pronounced Discontinuities: Because the structural layout maps intervals directly to nested blocks, the sudden jump from a continuous “velocity(xₜ, falling)” state to a discrete “velocity(xₜ, stopped)” state is physically exposed on the page. Any unhandled gaps or discontinuities are immediately exposed on the page, allowing the reader’s cognitive architecture to serve as a low-overhead neurobiological compiler.  
* Absolute Horizon Exhaustion: The final block uses the infinite horizon “∞ₜ” to act as a terminal sink. By setting the final state to run forever, it ensures that as the progression axis continues, the properties remain stably defined and the framework never crashes into an unhandled future.

# IV. System Scalability and Machine Convergence

Unlike traditional notations that separate human readability from machine execution, this framework introduces a unified semantic layer. The container syntax serves a single source of truth capable of being compiled simultaneously by both human cognitive faculties and machine architectures:

* The Obsolescence of Conditional Branching (No “If/Then”): Traditional conditional branching (“if/then” statements) and piecewise mathematical functions are artificial mechanisms born out of linear system limitations; in physical reality, conditional gates and piecewise divisions do not exist. A physical entity never pauses mid-trajectory to evaluate an algebraic inequality or check a binary logic gate. Instead, nature operates seamlessly across a continuous, parallel timeline driven entirely by absolute temporal geography and structural placement. Piecewise math acts as a hacky, manual patch–shattering a unified physical object into a fragmented list of disconnected formulas. By contrast, this framework structures logic purely through explicit coordinate containment. Changes occur automatically by spatial placement along the progressional axis rather than by executing conditional tests. By removing both code branch gates and piecewise math fragmentations, the system mirrors the natural, uninterrupted flow of reality.  
* Symmetrical Parsing: The explicit boundary declarations and bracket nesting remove structural ambiguity entirely. This allows an automated compiler to parse the timeline and execute underlying arithmetic directly from the visual layout, matching the exact state tracking occurring in the reader’s brain.  
* Infinite Scale via Layered Abstraction: As systems grow in complexity, the framework does not break down or require complex logic overrides. Instead, users can abstract and complexify the model infinitely by nesting sub-streams and composite wrappers deeper within the existing layout rules, maintaining a clean visual architecture at any scale.

# IV.C. Limitations and Future Work

As currently conceptualized, this declarative framework functions as an optimized architectural blueprint rather than a deployed computational environment. To mature this notation into a fully realized modelling framework, several critical limitations must be systematically addressed in future developments:

* Formal Grammar Development: The notation currently relies on human cognitive facilities to act as the processing engine. The immediate next phase of this research requires defining a formal context-free grammar to allow software compilers to algorithmically parse the layout blocks and execute calculations directly from the visual syntax.  
* Non-Linear Feedback Loops: While the system handles parallel continuous streams and chronological overrides effortlessly, further rules must be established to model complex, multi-variable feedback loops and infinite recursive states without cluttering the visual clarity of the container blocks.  
* Cognitive Load Boundaries: Although the notation explicitly minimizes visual overhead for standard hybrid systems, empirical testing is required to determine the exact structural threshold where highly dense, industrial-scale variables might reintroduce cognitive friction.

# V. Conclusion

Traditional, over-engineered mathematical notation frequently misapplies the law of abstraction within the human cognitive landscape. When a notation system prioritizes dense algebraic syntax over structural clarity, it fails to optimize for the processing constraints of the human mind. The resulting cognitive overhead manifests as literal runtime errors in the reader’s internal compiler–their brain–resulting in a pervasive state of cognitive perplexity.  
The declarative, interval-scoped framework introduced in this paper offers a profound resolution by operating as a universal algebraic state machine. By unifying continuous mathematical trajectories with discrete state boundaries inside explicit, layout driven containers, the framework renders traditional conditional logic (if/then) completely obsolete. It treats logic not as a series of conditional gates, but as structural geography along a universal axis of progression.  
Because this syntax abstracts state transition down to pure placement and chronological priority, its modeling capabilities are entirely domain-agnostic. Whether applied to the kinetic velocities of physics, the sequential execution of computer science architectures, or the shifting truth values of philosophical systems, the framework serves as a single, symmetrical source of truth for both machine computation and human intuition. By shifting the cognitive burden from active syntax parsing to immediate visual pattern recognition, this framework allows both the biological brain and the silicon processor to compile the complexities of a changing universe with minimal friction.

# Acknowledgements & Conceptual Independence

The interval-scoped notation, container block syntax and temporal priority rules presented throughout this research were conceptualized and developed independently from first principles. The framework was engineered as a direct alternative response to the visual overhead, hidden discontinuities, and structural ambiguities encountered within traditional calculus pedagogy. Because this notation was designed from scratch to optimize cognitive clarity, it was developed entirely without referencing or drawing from existing computer science, programmatic, or formal algebraic language architectures.
