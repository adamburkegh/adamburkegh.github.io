---
layout: post
tags: ["algorithms","Simondon","Nick Seaver","structured programming","technical culture", "reuse","Barad"]
---

What do we mean by algorithm? What do we want to achieve with the term?

The seemingly straightforward term, algorithm, has been a topic of much public discussion in recent years, well beyond the technical contexts where it was originally coined and used. This includes internet platforms trying to sell a service or explain themselves, legal cases, and insightful analysis from scholars in different disciplines about the social and power dynamics at work.

I published a paper, [Occluded Algorithms](https://doi.org/10.1177/2053951719858743), on these dynamics, how we now have two definitions of algorithm, and what we can miss when we substitute one for the other. In particular, I point to the history of "algorithm" as part of the intellectual project of structured programming, which is about building software in components understandable to the limited human brain. 

Using the structured programming definition, I argue algorithms are distinct, identifiable components of machinic infrastructure, but these components are less visible in an era of widespread code reuse. In contrast to much of the recent discussion about "algorithmic bias", algorithmic code is the least value-laden code, with social values much more often expressed in the data and harnesses around it. Both Barad and Simondon give useful concepts for understanding the nature of this "agential cut". I show examples of drawing this cut on code and how it connects to ideas in software engineering, from computer science advocates of modularity like Dijkstra, to professional practice ideas, such as Michael Feathers' "seams".

There is a second way of seeing algorithms: as a shorthand for a black box decision hidden by a computational interface. This isn't just a matter of non-techies mangling a technical term: there are lots of examples of technologists and technology companies switching back and forth between definitions, in confusion, or for their own purposes. Not coincidentially, this is often around system failures or questions of social policy.

The anthropologist Nick Seaver, observing this, proposes the clearest and strongest version of the second definition: [that algorithms are not specific technical objects, but just culture](https://doi.org/10.1177/2053951717738104). Seaver is a careful and sympathetic observer of technologists and organizations, and some of the best examples of this usage come from him. He's also quite right that scholars with different bases of expertise should not be shy about analysing and critiquing these systems. Nevertheless I think this "algorithms as culture" usage doesn't work well as a design tool. People are right to be skeptical about organizations blaming "The Algorithm", but naming entire systems as algorithms evokes and entrenches this black box view. 

Similarly, "ethics of algorithms" mostly propose parameterization and traceability in computational decisions, which is reinventing the structured programming project, while disintegrating its most critical term. To achieve shared design goals we need a shared design language.

This blog post roughly marks a one-year anniversary since the paper was out (and also marks _Big Data and Society_ getting its first impact factor), which seems as good an occassion as any to summarize the work on this new blog. A year later, I think it holds up pretty well, and can help parse out where the most safety-critical places in these sociotechnical systems are, in discussions where passionate well-meaning people often talk past one another.

There have been some good informal responses to the piece. Nick Seaver made some generous comments [on Twitter](https://twitter.com/npseaver/status/1151093454560288769). [Ed Summers](https://inkdroid.org/2019/07/19/algorithms/) had some further thoughts on how algorithms in code, and in society, define an inside/outside structure, shaping visibility and power accordingly.

---

_References_

Burke, A. (2019). Occluded algorithms. Big Data & Society, 6(2), 2053951719858743. https://doi.org/10.1177/2053951719858743

Seaver, N. (2017). Algorithms as culture: Some tactics for the ethnography of algorithmic systems: Big Data & Society. https://doi.org/10.1177/2053951717738104

