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
	* [Rule Set and Rule Set Profile](https://github.com/CredentialEngine/pathways/blob/master/Overview.md#45-rule-set-and-rule-set-profile)
* [Term Definitions](https://github.com/CredentialEngine/pathways/blob/master/Overview.md#5-term-definitions)
* [Pathways Work Group Members](https://github.com/CredentialEngine/pathways/blob/master/Overview.md#6-pathways-work-group-members)
* [Example Encodings](https://github.com/CredentialEngine/pathways/blob/master/Overview.md#6-example-encodings)
* [Submit Comments](https://github.com/CredentialEngine/pathways/blob/master/Overview.md#7-submit-comments)
  
### 1. Introduction

In this *Pathway Overview*, we outline the current *Pathway Work Group* (PWG) proposal for a new CTDL Pathway specification. We will be in the consensus period for the propsal between the 2018 November 30 joint meeting of the PWG and the TAG and the presentations and discussion of the propsal with the other CE advisory groups on 10 January 2019. Input into the process has been significant through the engagement of the We anticipate that there will be additional refinements during the consensus period due to the additional input. If you have any comments regarding this *Consensus Draft*, please see Section 8. Submit Comments for links to the PWG and TAG discussion forums.
  
###  2. Definitions

#### 2.1 Pathway

>***In the context of Credential Engine, a pathway is comprised of structured sets of objectives and qualifying conditions defining points (milestones) along a route to fulfillment of a job, occupation or career. Qualifying conditions include homogeneous or heterogeneous sets of prescribed, preferred or recommended evidentiary artifacts such as competencies attained (knowledge, skills, abilities), relevant awards, other forms of recognition such as credentials earned and relevant experience.*** 

Candidate artifact classes currently include:
* Assessment
* Basic<sup>†</sup>
* Competency
* Co-Curricular Activity
* Course
* Credential
* Extracurricular Activity
* Job
* Work Experience

*† = Type of artifact not covered by the enumerated set of artifact classes*

The pathway's ecosystem is generally comprised of two broad classes:
1. **Individual Learner Pathway (ILP).** Pathways describing points along the personal journey a learner is pursuing or has pursued; and
2. **Organizational Pathway (OP),** Pathways describing points along a prescribed or recommended route as defined by organizations, collaborations or institutions.

Credential Engine's focus is on the definition and description of OPs and not ILPs. While out of scope of the PWG, the importance of ILPs to OPs should not be underestimated or the need for close collaboration between developers of OP and ILP data models undervalued. A robust and dynamic pathways ecosystems will likely depend on ILP data, along with evolving workforce needs, to inform development of OPs. Thus, collaboration between the work of the PWG and other groups (e.g., IMS [Comprehensive Learner Record Work Group](https://www.imsglobal.org/activity/comprehensive-learner-record) is to make sure CE maximizes the potential for each class of pathway to inform and support the other.

Since the goal of the CE pathway work is to enable the representation of pathways developed by a broad array of  organizations for an equally broad array of OP purposes, the following are out of scope for the CE PWG work: 
1. Determining what constitutes a best practice for designing pathways.
2. Identifying how people/organizations should determine pathways.

#### 2.2 Pathway Expression

A *Pathway Expression* is an informal notion of a machine actionable encoding of either a single *Pathway* or an aggregation of logically related *Pathways* defining alternative paths that are bound together in a single expression. 

As defined, the basic building blocks of a *Pathway* form a simple (RDF) directed graph as illustrated by the following figure where we see a *Pathway* pointing to a *Pathway Component* identified as the destination milestone or root node of the pathway (e.g., a bachelor degree in nursing) and a set of preceding *Pathway Components* defining earlier milestones back to an origin (e.g., a high school diploma).

![simple_directed_graph](https://user-images.githubusercontent.com/2939046/48304790-89bf1080-e4d4-11e8-9c3b-2a5ae24093ae.png)

However, a *Pathway Expression* may describe more complex circumstances such as alternative paths to the same destination, or a destination may be more diverse---e.g., a career cluster or a more general destination such as programming and software development (see, Illinois Pathways example below).  The following figure illustrates a pathway modeling of alternative paths to the same destination.

![alternatives_directed_graph](https://user-images.githubusercontent.com/2939046/48304822-27b2db00-e4d5-11e8-89a2-dac028bfe86a.png)

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
  
### 4. Conceptual Model

The CE pathways conceptual module is comprised of six classes: `Agent`, `Pathway`, `PathwayComponent`, `ComponentCondition`, `RuleSetProfile` and `RuleSet`. These classes and the primary relationships between them are illustrated below.

![2018-11-26 pathway trial](https://user-images.githubusercontent.com/2939046/49047753-4f6c9900-f18d-11e8-88a6-4dbfe32998d1.png)

Each class is defined as follows:

| Class       | Description   |
| ------------- |-------------|
|Agent|Organization or person that acts or has the power to act.Entity that serves as a defined point along the route of a Pathway.|
|Pathway|Entity comprised of structured sets of objectives and qualifying conditions defining points along a route to fulfillment of a job, occupation or career. Pathway entity represents a pathway as a whole and frequently includes a reference to an instance of PathwayComponent that serves as the root or destination node of the pathway.|
|PathwayComponent|A PathwayComponent describes an objective and its completion requirements through reference to one or more instances of ComponentCondition.|
|ComponentCondition|Entity that describes what must be done to complete one PathwayComponent [or part thereof] as determined by the issuer of the Pathway. A ComponentCondition references a single RuleSet entity with values ascertained through application of that RuleSet.|
|RuleSet|Entity that identifies the rules by which other PathwayComponent instances satisfy a PathwayComponent objective. In order to meet varying circumstances, there will likely be more than one recognized RuleSet.|
|RuleSetProfile|Entity defining the application of a RuleSet to a particular ComponentCondition.|

For the remainder of this *Overview*, we'll illustrate each class of entity using snippets of JSON-LD encoding of a pathway description based on the image below of a transfer pathway for an Associate of Science Degree in Computer Science from Bakersfield College to the California State University. The pathway moves from left to right covering the four terms of a 2-year community college program. The upper half of the image represents the "core" cources for the degree. The horizontal lines between courses represents the course prerequisite linking structure. 

The bottom half of the figure represents general education courses. Unlike the top half, there is no apparent prerequisite structure. Note that the bottom right node in the figure presents a set of alternative history and philosophy courses from which a student is expected to pick one. Note that several other general education components also present such an alternative. We'll address how these kinds of choices are handled below in the section on the model's `ComponentCondition`.

<img width="750" alt="ccc bakersfield-1" src="https://user-images.githubusercontent.com/2939046/47951186-7cc18080-df1a-11e8-8cad-7136a9b3bee0.png">


#### 4.1 Agent

The Pathway's model does not define any properties for the `Agent` class and assumes that appropriate agents defined within relevant contexts will be referenced from the `Pathway` entity as `ownerBy` the `Pathway`. For example, an instance of the CTDL `CredentialOrganization` class could use an `ctdl:owns` property to reference one of its pathways. In like fashion, that `Pathway` instance could reference its owner via `ctdl:ownedBy`--as illustrated in the JSON-LD code snippet in the following section.

#### 4.2 Pathway

The `Pathway` class describes the pathway as a whole including (but not limited to) name and description of the pathway, reference to its owner, and identifies a root (destination) `PathwayComponent` where such a component is present (see discussion below in `PathwayComponent`).

```
{
   "@type": "Pathway",
   "@id": "https://credentialengineregistry.org/pathways/e9a210a8-a77c-41af-b594-4543ef4c2b08",
   "name": "Associate of Science Degree: Computer Science",
   "description": "Transfer pathway for the Bakersfield College Associate of Science Degree: Computer Science to the California State University",
   "hasRootComponent": "https://credentialengineregistry.org/pathways/719cfee7-d380-4ebd-89ca-f6c143d8a3d5",
   "source": "https://programmap.bakersfieldcollege.edu/academics/interest-clusters/4/programs/Computer_Science-ASSOCIATE_IN_SCIENCE_FOR_TRANSFER",
   "ownedBy": "https://www.bakersfieldcollege.edu"
}
```

#### 4.3 Pathway Component

The `PathwayComponent` class is a superclass identifying a family of subclasses that define specific `PathwayComponent` sub-types. The `PathwayComponent` represents individual milestones along a pathway's journey. The `PathwayComponents` for a particular `Pathway` may be comprised of instances of a single subclass identified in the table below or a mix of the subclasses.

| Subclass       | Description   |
| ------------- |-------------|
| AssessmentComponent|Direct, indirect, formative, and summative evaluation or estimation of the nature, ability, or quality of an entity, performance, or outcome of an action.|
|BasicComponent|General purpose entity for describing a sub-class of PathwayComponent not otherwise covered by the enumerated subclasses.|
|CocurricularComponent|Activities, programs, and informal learning experiences such as a civic or service activity outside the classroom that supplement and complement what is being learned in the classroom.|
|CompetencyComponent|Description of measurable or observable knowledge, skills, and abilities necessary to successful performance of a person in a given context. Competency is broadly defined to include assertions of academic, professional, occupational, vocational and life goals, outcomes, and standards, however labeled.|
|CourseComponent|Structured sequence of one or more educational activities that aims to develop a prescribed set of knowledge, competence or ability of learners.|
|CredentialComponent|Qualification, achievement, personal or organizational quality, or aspect of an identity typically used to indicate suitability.|
|ExtracurricularComponent|Entity describing an activity that may be offered or provided by a school, college, or other organization that may not be connected to a course or academic program.|
|JobComponent|Entity describing a specific job or occupation.|
|WorkExperienceComponent|Entity describing training experience a person gains while working in a specific job or occupation; frequently unpaid.|

While all of the subclasses share basic descriptive properties, each has additional properties particular to the subclass. While a basic set of properties are set out in the [Pathway Terms](https://github.com/CredentialEngine/vocabularies/issues/546) document, additional properties will be added as experience is gained describing existing pathways.  

Relationships between `PathwayComponents` in a `Pathway` are of two types: (1) simple binary relationships expressed as simple assertions in RDF---e.g., `PathwayComponent`===`prerequisite`===>`PathwayComponent`; and (2) complex relationships expressed through use of the `ComponentCondition` class (see section 4.4)--e.g., where the required condition is to pick a specified number of `PathwayComponents` from an array of available choices.

The following JSON-LD code snippet illustrates a `PathwayComponent` of the subclass `CourseComponent` for the course "Programming Concepts and Methology II" with a simple `prerequisite` assertion.

```
{
   "@type": "CourseComponent",
   "@id": "https://credentialengineregistry.org/pathways/11360165-b900-41e3-9b5b-7be2ef7198b5",
   "name": "Programming Concepts and Methology II",
   "creditUnitType": "http://purl.org/ctdl/vocabs/creditUnit/DegreeCredit",
   "creditUnitValue": 3.0,
   "courseCode": "COMP B12",
   "programTerm": "2nd Term",
   "programLevel": "Core",
   "prerequisite": "https://credentialengineregistry.org/pathways/1f8d3d06-3953-4bd8-8750-7dc5e9a062eb"         
}
```

A *Pathway Expression* may or may not define a single point of origin or destination `PathwayComponent`. The latter may occur where the `Pathway` defines an aggregation of logically related *Pathways* defining alternative path choices that are bound together in a single *pathway expression*. 

#### 4.4 Component Condition

The `ComponentCondition` class "... describes what must be done to complete one `PathwayComponent` (or part thereof) as determined by the issuer of the `Pathway`". An instance of `ComponentCondition` must reference an instance of  `RuleSet` defining the 'algorithm' or process to be applied by the `ComponentCondition` --- e.g., one `RuleSet` might define the constraints on picking a `CourseComponent` from an array of such components while another `RuleSet` might set a level of confidence (or other constraint) that must be met before a `WorkExperienceComponent` satisfies the conditions. 

While a `PathwayComponent` may have more than one `ComponentCondition`, each `ComponentCondition` may be associated with only one `RuleSet`. Initially, we are using an extension of a simple, but widely applicable "count rule" ruleset (by Badgr/IMS CLR) that defines the constraints on picking a number of `PathwayComponent` instances that is less than or equal to an enumerated array of such components. We have extended the count rule here to also include being able to set a minimum and maximum of required components to be selected from the array (e.g., a minimum of 3 and a maximum of 5 out of those available).  Development of more complex `RuleSets` will occur as experience requires. 

The following JSON-LD example code snippet illustrates an instance of `CourseComponent` with a `ComponentCondition` that uses the "count rule" to pick one `PathwayComponent` from an array of two such candidate (target) components. Note that the `RuleSet` has been identified by an example URI--uniquely identifying it globally.


```
{
   "@type": "CourseComponent",
   "@id": "https://credentialengineregistry.org/pathways/5c364f83-8826-4e39-ab4a-8b656924f254",
   "programTerm": "3rd Term",
   "creditUnitValue": 3.0,
   "hasCondition": {
       "@type": "ComponentCondition",
       "description": "Selection of one course from PHIL B9 or ENGL B28",
       "hasRuleSet": {
           "@type": "RuleSetProfile",
           "ruleSetType": "https://credentialengineregistry.org/ruleSets/IMS-83f05f51-618b-44f3-806c-066365254a8b",
           "countRuleType": "https://credentialengineregistry.org/ruleSets/IMS-83f05f51-618b-44f3-806c-066365254a8b/RequiredNumber",
           "requiredNumber": 1
       },
       "targetComponent": [
           "https://credentialengineregistry.org/pathways/38567f64-e2ce-4883-8521-08e70da7a5be", 
           "https://credentialengineregistry.org/pathways/bae6587a-8506-4817-832a-04bf21177e48"
       ]
    }
}
```
#### 4.5 Rule Set and Rule Set Profile

In Section 4, we defined a `RuleSet` as an entity that "identifies the rules by which other PathwayComponent instances may satisfy a `PathwayComponent` objective". The `RuleSetProfile` identifies the particular `RuleSet` used by the `ComponentCondition` and resolves any variables in the rules to reflect the circumstances of a *particular* `ComponentCondition`. For example, with the "count rule"--defined in a `RuleSet`, you may be required to indicate the number `PathwayComponents` to select from an array of `PathwayComponents` that satisfies the rule. It is in the `RuleSetProfile` that the number satisfyting the rule is declared. 

### 5. Term Definitions

The CE Pathway's domain model is currently comprised of the following:

* 14 CTDL classes
	* 1 existing class
	* 13 new classes
 * 41 CTDL properties
	 * 10 new properties
	 * 31 existing properties 

A complete listing of the defined properties and classes (terms) including their definitions can be found at [Pathway Terms](https://github.com/CredentialEngine/vocabularies/issues/546). 

### 6. Pathways Work Group Members

* Jeff Bohrer, IMS Global Learning Consortium
* Amie Bloomfield, NOCTI and Nocti Business Solutions
* Carla Casilli, LA Counts
* Caryn Chaden, DePaul University
* Deb Everheart,	Cengage
* John Foster, NOCTI
* Jonathan Furr, Education Systems Center at NIU
* Bill Guest, Metrics Reporting, Inc.
* Amy Heitzman, UPCEA
* Joshua Hester, ITCC/Kaplan Professional
* Lesley Hirsch, New Jersey Department of Labor and Workforce Development
* Laurel Hogue, University of Central Missouri
* Chris Houston, Capella University/IMS
* Shawn Hulsizer, CAEL
* Alexander Jackl, Bardic Systems, Inc.
* Mark Leuba, IMS Global Learning Consortium
* Ronald Mitchell Virgil Careers
* Jane Oates, Working Nation
* Nate Otto, Concentric Sky
* Rodney Parks, Elon University
* David Ramsay, New Jersey Department of Labor and Workforce Development
* Fritz Ray, Eduworks
* Art Recesso, University System of Georgia
* Alma Salazar, Los Angeles Area Chamber of Commerce
* Samantha Sanders, Career and Technical Education
* Gregory Sedrick, Tennessee Board of Regents
* Mary Anne Sheahan, Vermont Talent Pipeline / Vermont Business Roundtable
* Bob Sheets, GWU Institute of Public Policy
* Roy Swift, workcred

### 7. Example Encodings

A full JSON-LD encoding of the Bakersfield College pathway used above can be [found here](https://github.com/CredentialEngine/vocabularies/blob/master/Pathway-Examples/Bakersfield_AS_CS_pathway-CSU_transfer.json).

### 8. Submit Comments

Comments on this proposal can be made through either the [Technical Advisory Group (TAG) Google Group forum](https://groups.google.com/forum/?fromgroups#!forum/credentialenginetech), or the [Pathway Working Group (DWG) Google Group forum](https://groups.google.com/a/credentialengine.org/forum/#!forum/credential-engine-pathways-work-group).

