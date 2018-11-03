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
* Credential
* Extracurricular Activity
* Job
* Work Experience

*† = Type of artifact not covered by the enumerated set of artifact classes*

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

![diverse_alternatives_directed_graph](https://user-images.githubusercontent.com/2939046/47952505-b059d600-df2d-11e8-8a4e-ba21c7899edd.png)

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

![2018-11-03 pathway trial](https://user-images.githubusercontent.com/2939046/47950833-5d742480-df15-11e8-85dd-4f348bf05d30.png)

@@@

<img width="1153" alt="ccc bakersfield-1" src="https://user-images.githubusercontent.com/2939046/47951186-7cc18080-df1a-11e8-8cad-7136a9b3bee0.png">

@@@

<img width="1171" alt="ccc bakersfleld-2" src="https://user-images.githubusercontent.com/2939046/47951190-7f23da80-df1a-11e8-82a1-f8a5b31d3d68.png">

#### 4.1 Agent

#### 4.2 Pathway

@@@

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

@@@


#### 4.3 Pathway Component


Subtypes of PathwayComponent include:

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
|WorkExperienceComponent|Entity describing training experience a person (student) gains while working in a specific job or occupation; frequently unpaid.|

@@@

```
{
   "@type": "Course",
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

#### 4.4 Component Condition

The `ComponentCondition` class "... describes what must be done to complete one `PathwayComponent` (or part thereof) as determined by the issuer of the `Pathway`". An instance of `ComponentCondition` must reference an instance of  `RuleSet` defining the 'algorithm' or process to be applied by the `ComponentCondition` --- e.g., one `RuleSet` might define the constraints on picking a `CourseComponent` from an array of such components while another `RuleSet` might set a level of confidence (or other constraint) that must be met before a `WorkExperienceComponent` satisfies the conditions. 

While a `PathwayComponent` may have more than one `ComponentCondition`, each `ComponentCondition` may be associated with only one `RuleSet`. Initially, there is a single, simple, but robust "count rule" ruleset (defined by Badgr/IMS) that defines the constraints on picking one or more or all `PathwayComponent` instances from an array of such component instances. Development of more complex `RuleSets` will occur as experience dictates. 

The following JSON-LD example code snippet illustrates an instance of `CourseComponent` with a `ComponentCondition` that uses the "count rule" to pick one `PathwayComponent` from an array of two such components. Note that the `RuleSet` has been identified by an example URI--uniquely identifying it globally.


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
           "@type": "RuleSet",
           "ruleSetType": "http://examplePathways.org/ruleSets/IMS-83f05f51-618b-44f3-806c-066365254a8b",
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


### 5. Property and Class Definitions

The CE Pathway's domain model is currently comprised of the following:

* 14 CTDL classes
	* 1 existing class
	* 13 new classes
 * 41 CTDL properties
	 * 10 new properties
	 * 31 existing properties 

A complete listing of the defined properties and classes (terms) including their definitions can be found at [Pathway Terms](https://github.com/CredentialEngine/vocabularies/issues/546). 
