# Pathway Overview
### Table of Contents  
* [Introduction](https://github.com/CredentialEngine/pathways/blob/master/Overview.md#1-introduction)
* [Definition and Scope](https://github.com/CredentialEngine/pathways/blob/master/Overview.md#2-definition)
	* [Pathway](https://github.com/CredentialEngine/pathways/blob/master/Overview.md#21-pathway)
	* [Pathway Expression](https://github.com/CredentialEngine/pathways/blob/master/Overview.md#22-pathway-expression)
* [Use Cases](https://github.com/CredentialEngine/pathways/blob/master/Overview.md#3-use-cases)
* [Domain Model](https://github.com/CredentialEngine/pathways/blob/master/Overview.md#4-domain-model) 
	* [Agent](https://github.com/CredentialEngine/pathways/blob/master/Overview.md#41-agent)
	* [Pathway](https://github.com/CredentialEngine/pathways/blob/master/Overview.md#42-pathway)
	* [Pathway Component](https://github.com/CredentialEngine/pathways/blob/master/Overview.md#43-pathway-component)
	* [Component Condition](https://github.com/CredentialEngine/pathways/blob/master/Overview.md#44-component-condition)
	* [Rule Set](https://github.com/CredentialEngine/pathways/blob/master/Overview.md#45-rule-set)
* [Property and Classes Definitions](https://github.com/CredentialEngine/pathways/blob/master/Overview.md#5-property-and-class-definitions) 
  
### 1. Introduction 
  
###  2. Definition

#### 2.1 Pathway

>***In the context of Credential Engine, a pathway is comprised of structured sets of objectives and qualifying conditions defining points (milestones) along a route to fulfillment of a job, occupation or career. Qualifying conditions include homogeneous or heterogeneous sets of prescribed, preferred or recommended evidentiary artifacts such as competencies attained (knowledge, skills, abilities), relevant awards, other forms of recognition such as credentials earned and relevant experience.*** 

Candidate artifact classes currently include:
* Assessment
* Basic<sup>†</sup>
* Competency
* Co-Curricular Activity
* Course
* Credential<sup>††</sup>
* Extracurricular Activity
* Job
* Work Experience

*† = Type of artifact not covered by the enumerated set of artifact classes*
*†† = CTDL Credential subclasses*

The pathway's ecosystem is generally comprised of two broad classes:
1. **Individual Learner Pathway (ILP).** Pathways describing points along the personal journey a learner is pursuing or has pursued; and
2.  **Organizational Pathway (OP),** Pathways describing points along a prescribed or recommended route as defined by organizations, collaborations or institutions.

Credential Engine's focus is on the definition and description of OPs and not ILPs. While out of scope of the PWG, the importance of ILPs to OPs should not be underestimated or the need for close collaboration between developers of OP and ILP data models undervalued. A robust and dynamic pathways ecosystems will likely depend on ILP data, along with evolving workforce needs, to inform development of OPs. Thus, collaboration between the work of the PWG and other groups (e.g., IMS [Comprehensive Learner Record Work Group](https://www.imsglobal.org/activity/comprehensive-learner-record) is to make sure CE maximizes the potential for each class of pathway to inform and support the other.

Since the goal of the CE pathway work is to enable the representation of pathways developed by a broad array of  organizations for an equally broad array of OP purposes, the following are out of scope for the CE PWG work: 
1. Determining what constitutes a best practice for designing pathways.
2. Identifying how people/organizations should determine pathways.

#### 2.2 Pathway Expression

A *Pathway Expression* is a machine actionable encoding of either a single *Pathway* or an aggregation of logically related *Pathways* defining alternative paths that are bound together in a single expression. 

As defined, the basic building blocks of a *Pathway* form a simple directed graph as illustrated by the following figure where we see a *Pathway* pointing to a *Pathway Component* identified as the destination milestone or root node of the pathway (e.g., a bachelor degree in nursing) and a set of preceding *Pathway Components* defining earlier milestones back to an origin (e.g., a high school diploma).

![simple_directed_graph](https://user-images.githubusercontent.com/2939046/47941714-83b1aa00-deac-11e8-9678-8cff6faf2456.png)

However, a *Pathway Expression* may describe more complex circumstances such as alternative paths to the same destination, or a destination may be more diverse---e.g., a career cluster or a more general destination such as programming and software development (see, Illinois Pathways example below).  The following figure illustrates a pathway modeling of alternative paths to the same destination.

![alternatives_directed_graph](https://user-images.githubusercontent.com/2939046/47941705-7c8a9c00-deac-11e8-8fd1-72daffcf9699.png)

A *Pathway Expression* may define no single point of origin or destination but instead define an cluster of potential origins and destinations. (Note: no single root node defined)

![diverse_alternatives_directed_graph](https://user-images.githubusercontent.com/2939046/47942532-8e217300-deaf-11e8-938c-bd9bcb102c91.png)

### 3. Use Cases  

>1. **Education & Career Planning:** Support students and workers search and plan for career pathways including pathway options through stackable and latticed credentials and career clusters.
 >2. **Credential Discovery:** Find one or more types of credentials that best meet a person’s career and/or education goals along career and education pathways that provide the:
		a. best transfer value for credentials they have already earned; and
		b. potential to stack and build on other credentials.
>3. **Education & Career Transitions:** Identify education and career paths or progressions based on:
	     a. degree of transfer value; and
	     b. potential to stack and build on other credentials.
>4. **Competency Analysis:** Identify education and career paths in terms of the competencies that they require;
		a. represent current achievement of desired competencies based on competency alignments of held credentials.
		b. discover relevant credentials for each competency on a pathway/job profile from multiple providers.
  
### 4. Domain Model

![2018-10-25 pathway trial](https://user-images.githubusercontent.com/2939046/47950658-5992d300-df12-11e8-83e5-25ca82f1f0f1.png)

#### 4.1 Agent

#### 4.2 Pathway

#### 4.3 Pathway Component

#### 4.4 Component Condition

#### 4.5 Rule Set

### 5. Property and Class Definitions

The CE Pathway's domain model is currently comprised of the following:

* 14 CTDL classes
	* 1 existing class
	* 13 new classes
 * 41 CTDL properties
	 * 10 new properties
	 * 31 existing properties 

A complete listing of the defined properties and classes (terms) including their definitions can be found at [Pathway Terms](https://github.com/CredentialEngine/vocabularies/issues/546). 
