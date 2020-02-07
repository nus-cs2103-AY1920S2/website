<frontmatter>
title: "Schedule"
header: header.md
footer: footer.md
head: scheduleHead.md
pageNav: 1
</frontmatter>

{% import "common/topics.njk" as topics with context %}
{% from "admin/admin-tasks.mbdf" import show_weekly_admin_tasks with context %}

<!--
    {num: "1", day:"Aug 12"},
    {num: "2", day:"Aug 19"},
    {num: "3", day:"Aug 26"},
    {num: "4", day:"Sep 2"},
    {num: "5", day: "Sep 9" },
    {num: "6", day: "Sep 16" },
    {num: "7", day: "Sep 30" },
    {num: "8", day: "Oct 7" },
    {num: "9", day: "Oct 14" },
    {num: "10", day: "Oct 21" },
    {num: "11", day: "Oct 28" },
    {num: "12", day: "Nov 4" },
    {num: "13", day: "Nov 11" }
-->

{% set weeks = [
    {num: "1", day:"Jan 13"},
    {num: "2", day:"Jan 20"},
    {num: "3", day:"Jan 27"},
    {num: "4", day:"Feb 3"},
    {num: "5", day: "Feb 10" },
    {num: "6", day: "Feb 17" },
    {num: "7", day: "Mar 2" },
    {num: "8", day: "Mar 9" },
    {num: "9", day: "Mar 16" },
    {num: "10", day: "Mar 23" },
    {num: "11", day: "Mar 30" },
    {num: "12", day: "Apr 6" },
    {num: "13", day: "Apr 13" }
] %}

{#
-1: site not ready, lands in the module intro page
0: site ready but semester hasn't started, lands in the module intro page
14: site no longer used, lands in the module intro page
1..13: site is active, lands in the week's schedule page
#}
{% set current_week = "5" %}


{% set all_topics = [
{week: "1"},
  {name: "OOP"},
    {heading: "OOP: Classes & Objects"},
      {location: ["oop", "introduction", "what"]},
      {location: ["oop", "objects", "what"]},
      {location: ["oop", "objects", "abstraction"]},
      {location: ["oop", "objects", "encapsulation"]},
      {location: ["oop", "classes", "what"]},
      {location: ["cppToJava", "classes", "definingClasses"]},
      {location: ["cppToJava", "classes", "gettersAndSetters"]},
      {location: ["oop", "classes", "classLevelMembers"]},
      {location: ["cppToJava", "classes", "classLevelMembers"]},
      {location: ["oop", "classes", "enumerations"]},
      {location: ["cppToJava", "misc", "enums"]},
    {heading: "OOP Inheritance"},
      {location: ["oop", "inheritance", "what"]},
      {location: ["oop", "inheritance", "overloading"]},
      {location: ["oop", "inheritance", "overriding"]},
      {location: ["cppToJava", "inheritance", "basic"]},
    {heading: "OOP: Polymorphism"},
      {subheading: "Polymorphism"},
        {location: ["oop", "polymorphism", "what"]},
        {location: ["cppToJava", "inheritance", "polymorphism"]},
      {subheading: "Abstract Classes"},
        {location: ["oop", "inheritance", "abstractClasses"]},
        {location: ["cppToJava", "inheritance", "abstractClassesAndMethods"]},
      {subheading: "Interfaces"},
        {location: ["oop", "inheritance", "interfaces"]},
        {location: ["cppToJava", "inheritance", "interfaces"]},
      {subheading: "How Polymorphism Works"},
        {location: ["oop", "inheritance", "substitutability"]},
        {location: ["oop", "inheritance", "dynamicAndStaticBinding"]},
        {location: ["oop", "polymorphism", "how"]},
  {name: "Java"},
    {heading: "Java: Collections"},
      {location: ["cppToJava", "collections", "what"]},
      {location: ["cppToJava", "collections", "arrayListClass"]},
      {location: ["cppToJava", "collections", "hashMapClass"]},
    {heading: "Exception Handling"},
      {location: ["errorHandling", "introduction", "what"]},
      {location: ["errorHandling", "exceptions", "what"]},
      {location: ["cppToJava", "exceptions", "what"]},
      {location: ["errorHandling", "exceptions", "how"]},
      {location: ["cppToJava", "exceptions", "how"]},
      {location: ["errorHandling", "exceptions", "when"]},
{week: "2"},
  {name: "SE Intro"},
    {heading: "SE: Intro"},
      {location: ["softwareEngineering", "introduction", "prosAndCons"]},
  {name: "Implementation"},
    {heading: "IDEs: Basic Features"},
      {location: ["ides", "introduction", "what"]},
      {location: ["intellij", "projectSetup"]},
  {name: "Testing"},
    {heading: "Automated Testing of Text UIs"},
      {location: ["testing", "introduction", "what"]},
      {location: ["testing", "testingTypes", "regressionTesting", "what"]},
      {location: ["testing", "testAutomation", "what"]},
      {location: ["testing", "testAutomation", "testingTextUis"]},
  {name: "Revision Control"},
    {heading: "RCS: Revision History"},
      {location: ["revisionControl", "what"]},
      {location: ["revisionControl", "repositories"]},
      {location: ["gitAndGithub", "init"]},
      {location: ["revisionControl", "savingHistory"]},
      {location: ["gitAndGithub", "commit"]},
      {location: ["gitAndGithub", "ignore"]},
      {location: ["revisionControl", "usingHistory"]},
      {location: ["gitAndGithub", "tag"]},
      {location: ["gitAndGithub", "checkout"]},
      {location: ["gitAndGithub", "stash"]},
    {heading: "RCS: Remote Repos"},
      {location: ["revisionControl", "remoteRepositories"]},
      {location: ["gitAndGithub", "clone"]},
      {location: ["gitAndGithub", "pull"]},
      {location: ["gitAndGithub", "push"]},
{week: "3"},
  {name: "Implementation"},
    {heading: "Java"},
      {location: ["documentation", "tools", "javaDoc", "what"]},
      {location: ["documentation", "tools", "javaDoc", "how"]},
      {location: ["cppToJava", "misc", "fileAccess"]},
      {location: ["cppToJava", "misc", "packages"]},
      {location: ["cppToJava", "misc",  "jar"]},
    {heading: "Coding Standards"},
      {location: ["codeQuality", "introduction", "basic"]},
      {location: ["codeQuality", "followStandard", "introduction"]},
  {name: "Testing"},
    {heading: "Developer Testing"},
      {location: ["testing", "testingTypes", "developerTesting", "what"]},
      {location: ["testing", "testingTypes", "developerTesting", "why"]},
    {heading: "Unit Testing"},
      {location: ["testing", "testAutomation", "usingTestDrivers"]},
      {location: ["testing", "testAutomation", "tools"]},
      {location: ["testing", "testingTypes", "unitTesting", "what"]},
      {location: ["cppToJava", "junit", "basic"]},
      {location: ["testing", "testingTypes", "unitTesting", "stubs"]},
      {location: ["cppToJava", "junit", "intermediate"]},
  {name: "Project Management"},
    {heading: "RCS: Branching"},
      {location: ["revisionControl", "branching"]},
      {location: ["gitAndGithub", "branch"]},
      {location: ["gitAndGithub", "mergeConflicts"]},
    {heading: "RCS: Creating Pull Requests"},
      {location: ["gitAndGithub", "createPRs"]},
{week: "4"},
  {name: "Design"},
    {heading: "Design: Models"},
      {location: ["modeling", "introduction", "what"]},
      {location: ["modeling", "introduction", "how"]},
      {location: ["modeling", "introduction", "umlModels"]},
    {heading: "Class/Object Diagrams: Basics"},
      {location: ["modeling", "modelingStructures", "ooStructures"]},
      {location: ["modeling", "modelingStructures", "classDiagramsBasic"]},
      {location: ["modeling", "modelingStructures", "objectDiagrams"]},
      {location: ["uml", "miscellaneous", "objectVsClassDiagrams"]},
    {heading: "Class Diagrams: Intermediate-Level"},
      {location: ["uml", "notes", "notes"]},
      {location: ["uml", "notes", "constraints"]},
      {location: ["uml", "classDiagrams", "associationsAsAttributes", "what"]},
      {location: ["modeling", "modelingStructures", "classDiagramsIntermediate"]},
      {location: ["oop", "associations", "associationClasses"]},
  {name: "Implementation"},
    {heading: "Java: JavaFX"},
      {location: ["cppToJava", "misc", "javaFX"]},
    {heading: "Java: varargs"},
      {location: ["cppToJava", "misc", "varargs"]},
  {name: "Project Management"},
    {heading: "RCS: Managing Pull Requests"},
      {location: ["gitAndGithub", "managePRs"]},
  {name: "Quality Assurance"},
    {heading: "Code reviews"},
      {location: ["qualityAssurance", "codeReviews", "what"]},
    {heading: "Static Analysis"},
      {location: ["qualityAssurance", "staticAnalysis", "what"]},
{week: "5"},
  {name: "Requirements"},
    {heading: "Requirements: Intro"},
      {location: ["requirements", "introduction"]},
      {location: ["requirements", "nonFunctionalRequirements"]},
      {location: ["requirements", "quality"]},
      {location: ["requirements", "prioritizing"]},
    {heading: "Requirements: Gathering"},
      {location: ["gatheringRequirements", "brainstorming"]},
      {location: ["gatheringRequirements", "productSurveys"]},
      {location: ["gatheringRequirements", "observation"]},
      {location: ["gatheringRequirements", "userSurveys"]},
      {location: ["gatheringRequirements", "interviews"]},
      {location: ["gatheringRequirements", "focusGroups"]},
      {location: ["gatheringRequirements", "prototyping"]},
    {heading: "Requirements: Specifying"},
      {subheading: "Prose"},
        {location: ["specifyingRequirements", "prose", "what"]},
      {subheading: "Feature Lists"},
        {location: ["specifyingRequirements", "featureList", "what"]},
      {subheading: "User Stories"},
        {location: ["specifyingRequirements", "userStories", "introduction"]},
        {location: ["specifyingRequirements", "userStories", "details"]},
        {location: ["specifyingRequirements", "userStories", "usage"]},
      {subheading: "Glossary"},
        {location: ["specifyingRequirements", "glossary", "what"]},
      {subheading: "Supplementary Requirements"},
        {location: ["specifyingRequirements", "supplementaryRequirements", "what"]},
  {name: "Implementation"},
    {heading: "Code Quality"},
      {subheading: "Readability"},
        {location: ["codeQuality", "maximiseReadability", "introduction"]},
        {location: ["codeQuality", "maximiseReadability", "basic", "avoidLongMethods"]},
        {location: ["codeQuality", "maximiseReadability", "basic", "avoidDeepNesting"]},
        {location: ["codeQuality", "maximiseReadability", "basic", "avoidComplicatedExpressions"]},
        {location: ["codeQuality", "maximiseReadability", "basic", "avoidMagicNumbers"]},
        {location: ["codeQuality", "maximiseReadability", "basic", "makeCodeObvious"]},
        {location: ["codeQuality", "maximiseReadability", "intermediate", "structureCodeLogically"]},
        {location: ["codeQuality", "maximiseReadability", "intermediate", "dontTripReader"]},
        {location: ["codeQuality", "maximiseReadability", "intermediate", "practiceKISSing"]},
        {location: ["codeQuality", "maximiseReadability", "intermediate", "avoidPrematureOptimizations"]},
        {location: ["codeQuality", "maximiseReadability", "intermediate", "slapHard"]},
        {location: ["codeQuality", "maximiseReadability", "advanced", "makeHappyPathProminent"]},
      {subheading: "Naming"},
        {location: ["codeQuality", "nameWell", "introduction"]},
        {location: ["codeQuality", "nameWell", "basic", "nounsAndVerbsAsNames"]},
        {location: ["codeQuality", "nameWell", "basic", "useStandardWords"]},
        {location: ["codeQuality", "nameWell", "intermediate", "useNameExplain"]},
        {location: ["codeQuality", "nameWell", "intermediate", "notTooLongNorShort"]},
        {location: ["codeQuality", "nameWell", "intermediate", "avoidMisleadingNames"]},
      {subheading: "Unsafe Practices"},
        {location: ["codeQuality", "avoidShortcuts", "introduction"]},
        {location: ["codeQuality", "avoidShortcuts", "basic", "useDefaultBranch"]},
        {location: ["codeQuality", "avoidShortcuts", "basic", "dontRecycleVarsOrParams"]},
        {location: ["codeQuality", "avoidShortcuts", "basic", "avoidEmptyCatchBlocks"]},
        {location: ["codeQuality", "avoidShortcuts", "basic", "deleteDeadCode"]},
        {location: ["codeQuality", "avoidShortcuts", "intermediate", "minimiseVariableScope"]},
        {location: ["codeQuality", "avoidShortcuts", "intermediate", "minimiseCodeDuplication"]},
      {subheading: "Code Comments"},
        {location: ["codeQuality", "commentMinimally", "introduction"]},
        {location: ["codeQuality", "commentMinimally", "basic", "dontRepeatObvious"]},
        {location: ["codeQuality", "commentMinimally", "basic", "writeToReader"]},
        {location: ["codeQuality", "commentMinimally", "intermediate", "explainWhatWhyNotHow"]},
    {heading: "Refactoring"},
      {location: ["refactoring", "what"]},
      {location: ["intellij", "refactoring"]},
      {location: ["refactoring", "how"]},
      {location: ["refactoring", "when"]},
    {heading: "Assertions"},
      {location: ["errorHandling", "assertions", "what"]},
      {location: ["errorHandling", "assertions", "how"]},
      {location: ["errorHandling", "assertions", "when"]},
    {heading: "Java: streams"},
      {location: ["cppToJava", "misc", "streams"]},
  {name: "Project Management"},
    {heading: "Continuous Integration/Deployment"},
      {location: ["integration", "introduction", "what"]},
      {location: ["integration", "buildAutomation", "what"]},
      {location: ["integration", "buildAutomation", "continuousIntegrationDeployment"]},
{week: "6"},
  {name: "Design"},
    {heading: "Modeling: Sequence Diagrams"},
      {location: ["modeling", "modelingBehaviors", "sequenceDiagramsBasic"]},
      {location: ["modeling", "modelingBehaviors", "sequenceDiagramsIntermediate"]},
      {location: ["uml", "sequenceDiagrams", "referenceFrames"]},
      {location: ["uml", "sequenceDiagrams", "parallelPaths"]},
    {heading: "Architecture Diagrams"},
      {location: ["architecture", "introduction", "what"]},
      {location: ["architecture", "architectureDiagrams", "reading"]},
      {location: ["designApproaches", "multilevelDesign", "what"]},
  {name: "Implementation"},
    {heading: "IDEs: Basic Features"},
      {location: ["ides", "debugging", "what"]},
      {location: ["intellij", "debuggingBasic"]},
      {location: ["intellij", "codeNavigation"]},
    {heading: "Logging"},
      {location: ["errorHandling", "logging", "what"]},
      {location: ["errorHandling", "logging", "how"]},
  {name: "Documentation"},
    {heading: "Documentation Tools"},
      {subheading: "Markdown"},
        {location: ["documentation", "tools", "markdown", "what"]},
        {location: ["documentation", "tools", "markdown", "how"]},
      {subheading: "AsciiDoc"},
        {location: ["documentation", "tools", "asciiDoc", "what"]},
{week: "7"},
  {name: "Requirements"},
    {heading: "Requirements: Use Cases"},
        {location: ["specifyingRequirements", "useCases", "introduction"]},
        {location: ["specifyingRequirements", "useCases", "identifying"]},
        {location: ["specifyingRequirements", "useCases", "details"]},
        {location: ["specifyingRequirements", "useCases", "usage"]},
  {name: "Design"},
    {heading: "Design Principles: Basics"},
      {location: ["design", "introduction", "what"]},
      {subheading: "Abstraction"},
        {location: ["designFundamentals", "abstraction", "what"]},
      {subheading: "Coupling"},
        {location: ["designFundamentals", "coupling", "what"]},
        {location: ["designFundamentals", "coupling", "how"]},
        {location: ["designFundamentals", "coupling", "types"]},
      {subheading: "Cohesion"},
        {location: ["designFundamentals", "cohesion", "what"]},
        {location: ["designFundamentals", "cohesion", "how"]},
    {heading: "Basic Design Approaches"},
      {location: ["designApproaches", "topDownBottomUp", "what"]},
      {location: ["designApproaches", "agileDesign", "what"]},
  {name: "Implementation"},
    {heading: "IDEs: Intermediate Features"},
      {location: ["intellij", "productivityShortcuts"]},
    {heading: "Integration Approaches"},
      {location: ["integration", "approaches", "lateVsEarly"]},
      {location: ["integration", "approaches", "bigBangVsIncremental"]},
      {location: ["integration", "approaches", "topDownVsBottomUp"]},
  {name: "Project Management"},
    {heading: "Project Mgt: Scheduling and Tracking"},
      {location: ["projectPlanning", "milestones"]},
      {location: ["projectPlanning", "buffers"]},
      {location: ["projectPlanning", "issueTrackers"]},
      {location: ["projectPlanning", "workBreakdownStructure"]},
      {location: ["projectPlanning", "ganttCharts"]},
      {location: ["projectPlanning", "pertCharts"]},
      {location: ["teamwork", "teamStructures"]},
    {heading: "Project Mgt: Workflows"},
      {location: ["revisionControl", "forkingWorkflow"]},
      {location: ["gitAndGithub", "forkingWorkflow"]},
      {location: ["revisionControl", "drcsVsCrcs"]},
      {location: ["revisionControl", "featureBranchFlow"]},
      {location: ["revisionControl", "centralizedFlow"]},
{week: "8"},
  {name: "Design"},
    {heading: "%%[Revisiting] Drawing Class/Object Diagrams%%"},
      {location: ["modeling", "modelingStructures", "classDiagramsBasic"]},
      {location: ["modeling", "modelingStructures", "objectDiagrams"]},
      {location: ["uml", "miscellaneous", "objectVsClassDiagrams"]},
      {location: ["uml", "notes", "notes"]},
      {location: ["uml", "notes", "constraints"]},
      {location: ["uml", "classDiagrams", "associationsAsAttributes", "what"]},
      {location: ["modeling", "modelingStructures", "classDiagramsIntermediate"]},
      {location: ["oop", "associations", "associationClasses"]},
    {heading: "%%[Revisiting] Drawing Sequence Diagrams%%"},
      {location: ["modeling", "modelingBehaviors", "sequenceDiagramsBasic"]},
      {location: ["modeling", "modelingBehaviors", "sequenceDiagramsIntermediate"]},
      {location: ["uml", "sequenceDiagrams", "referenceFrames"]},
      {location: ["uml", "sequenceDiagrams", "parallelPaths"]},
  {name: "Testing Concepts"},
    {heading: "Testing: Types"},
      {subheading: "Integration Testing"},
        {location: ["testing", "testingTypes", "integrationTesting", "what"]},
        {location: ["testing", "testingTypes", "integrationTesting", "how"]},
      {subheading: "System Testing"},
        {location: ["testing", "testingTypes", "systemTesting", "what"]},
        {location: ["testing", "testAutomation", "testingGuis"]},
      {subheading: "Acceptance Testing"},
        {location: ["testing", "testingTypes", "acceptanceTesting", "what"]},
        {location: ["testing", "testingTypes", "acceptanceTesting", "acceptanceVsSystemTesting"]},
      {subheading: "Alpha/Beta Testing"},
        {location: ["testing", "testingTypes", "alphaBetaTesting", "what"]},
      {subheading: "Exploratory vs Scripted Testing"},
        {location: ["testing", "testingTypes", "exploratoryVsScriptedTesting", "what"]},
        {location: ["testing", "testingTypes", "exploratoryVsScriptedTesting", "when"]},
    {heading: "Testing: Intermediate Concepts"},
      {subheading: "Dependency Injection"},
        {location: ["testing", "dependencyInjection", "what"]},
        {location: ["testing", "dependencyInjection", "how"]},
      {subheading: "Testability"},
        {location: ["testing", "introduction", "testability"]},
      {subheading: "Test Coverage"},
        {location: ["testing", "testCoverage", "what"]},
        {location: ["testing", "testCoverage", "how"]},
      {subheading: "TDD"},
        {location: ["testing", "tdd", "what"]},
{week: "9"},
    {name: "Modeling"},
      {heading: "OO Domain Models"},
        {location: ["modeling", "modelingStructures", "objectOrientedDomainModels"]},
      {heading: "Activity Diagrams"},
        {location: ["modeling", "modelingBehaviors", "activityDiagrams"]},
        {location: ["modeling", "modelingBehaviors", "activityDiagramsIntermediate"]},
    {name: "Design"},
      {heading: "Design principles"},
        {location: ["principles", "singleResponsibilityPrinciple"]},
        {location: ["principles", "openClosedPrinciple"]},
        {location: ["principles", "separationOfConcernsPrinciple"]},
        {location: ["principles", "liskovSubstitutionPrinciple"]},
        {location: ["principles", "lawOfDemeter"]},
        {location: ["principles", "interfaceSegregationPrinciple"]},
        {location: ["principles", "dependencyInversionPrinciple"]},
        {location: ["principles", "solidPrinciples"]},
        {location: ["principles", "yagniPrinciple"]},
        {location: ["principles", "dryPrinciple"]},
        {location: ["principles", "brooksLaw"]},
      {heading: "Conceptualizing a Design"},
        {location: ["modeling", "modelingASolution", "introduction"]},
        {location: ["modeling", "modelingASolution", "basic"]},
        {location: ["modeling", "modelingASolution", "intermediate"]},
  {name: "Project Management"},
    {heading: "SDLC Process Models"},
      {location: ["processModels", "introduction", "what"]},
      {location: ["processModels", "introduction", "sequentialModels"]},
      {location: ["processModels", "introduction", "iterativeModels"]},
      {location: ["processModels", "introduction", "agileModels"]},
      {location: ["processModels", "exampleProcessModels", "scrum"]},
      {location: ["processModels", "exampleProcessModels", "xp"]},
      {location: ["processModels", "exampleProcessModels", "unifiedProcess"]},
      {location: ["processModels", "more", "cmmi"]},
      {location: ["processModels", "summary", "recap"]},
  {name: "Documentation"},
    {heading: "Writing Developer Documents"},
      {subheading: "Type of Developer Docs"},
        {location: ["documentation", "introduction", "what"]},
      {subheading: "Guideline: Aim for Comprehensibility"},
        {location: ["documentation", "guidelines", "aimForComprehensibility", "what"]},
        {location: ["documentation", "guidelines", "aimForComprehensibility", "how"]},
      {subheading: "Guideline: Describe Top-Down"},
        {location: ["documentation", "guidelines", "goTopDown", "what"]},
        {location: ["documentation", "guidelines", "goTopDown", "why"]},
        {location: ["documentation", "guidelines", "goTopDown", "how"]},
      {subheading: "Guideline: Minimal but Sufficient"},
        {location: ["documentation", "guidelines", "documentMinimally", "what"]},
        {location: ["documentation", "guidelines", "documentMinimally", "how"]},
{week: "10"},
  {name: "Design"},
    {heading: "Design Patterns"},
      {subheading: "Introduction"},
        {location: ["designPatterns", "introduction", "what"]},
        {location: ["designPatterns", "introduction", "format"]},
      {subheading: "Singleton pattern"},
        {location: ["designPatterns", "singleton", "what"]},
        {location: ["designPatterns", "singleton", "implementation"]},
        {location: ["designPatterns", "singleton", "evaluation"]},
      {subheading: "Facade pattern"},
        {location: ["designPatterns", "facade", "what"]},
      {subheading: "Command pattern"},
        {location: ["designPatterns", "command", "what"]},
      {subheading: "Abstraction Occurrence pattern"},
        {location: ["designPatterns", "abstractionOccurrence", "what"]},
  {name: "Implementation"},
    {heading: "Defensive Programming"},
      {location: ["errorHandling", "defensiveProgramming", "what"]},
      {location: ["errorHandling", "defensiveProgramming", "compulsoryAssociations"]},
      {location: ["errorHandling", "defensiveProgramming", "1to1Associations"]},
      {location: ["errorHandling", "defensiveProgramming", "referentialIntegrity"]},
      {location: ["errorHandling", "defensiveProgramming", "when"]},
      {location: ["errorHandling", "designByContract", "what"]},
  {name: "Quality Assurance"},
    {heading: "Test Cases: Intro"},
      {location: ["testCaseDesign", "introduction", "what"]},
      {location: ["testCaseDesign", "introduction", "positiveVsNegative"]},
      {location: ["testCaseDesign", "introduction", "blackVsGlass"]},
      {location: ["testCaseDesign", "more", "testingUseCases"]},
    {heading: "Test Cases: Equivalence Partitioning"},
      {location: ["testCaseDesign", "equivalencePartitions", "what"]},
      {location: ["testCaseDesign", "equivalencePartitions", "basic"]},
      {location: ["testCaseDesign", "equivalencePartitions", "intermediate"]},
    {heading: "Test Cases: Boundary Value Analysis"},
      {location: ["testCaseDesign", "boundaryValueAnalysis", "what"]},
      {location: ["testCaseDesign", "boundaryValueAnalysis", "how"]},
{week: "11"},
  {name: "Design"},
    {heading: "More Design Patterns"},
      {location: ["designPatterns", "modelViewController", "what"]},
      {location: ["designPatterns", "observer", "what"]},
      {location: ["designPatterns", "more", "otherDesignPatterns"]},
      {location: ["designPatterns", "more", "combiningDesignPatterns"]},
      {location: ["designPatterns", "more", "usingDesignPatterns"]},
      {location: ["designPatterns", "more", "vsPrinciples"]},
      {location: ["designPatterns", "more", "otherTypesOfPatterns"]},
    {heading: "Architectural Styles"},
      {location: ["architecture", "architecturalStyles", "introduction", "what"]},
      {location: ["architecture", "architecturalStyles", "nTier", "what"]},
      {location: ["architecture", "architecturalStyles", "clientServer", "what"]},
      {location: ["architecture", "architecturalStyles", "eventDriven", "what"]},
      {location: ["architecture", "architecturalStyles", "transactionProcessing", "what"]},
      {location: ["architecture", "architecturalStyles", "serviceOriented", "what"]},
      {location: ["architecture", "architecturalStyles", "more", "moreStyles"]},
      {location: ["architecture", "architecturalStyles", "more", "usingStyles"]},
      {location: ["architecture", "architectureDiagrams", "drawing"]},
  {name: "Quality Assurance"},
    {heading: "Test Cases: Combining Multiple Inputs"},
      {location: ["testCaseDesign", "combiningTestInputs", "why"]},
      {location: ["testCaseDesign", "combiningTestInputs", "combinationStrategies"]},
      {location: ["testCaseDesign", "combiningTestInputs", "heuristicValid"]},
      {location: ["testCaseDesign", "combiningTestInputs", "heuristicInvalid"]},
      {location: ["testCaseDesign", "combiningTestInputs", "mix"]},
    {heading: "Other QA Techniques"},
      {location: ["qualityAssurance", "introduction", "what"]},
      {location: ["qualityAssurance", "introduction", "validationVsVerification"]},
      {location: ["qualityAssurance", "formalVerification", "what"]},
  {name: "Implementation"},
    {heading: "Reuse"},
      {subheading: "APIs"},
        {location: ["reuse", "introduction", "what"]},
        {location: ["reuse", "introduction", "when"]},
      {subheading: "Libraries"},
        {location: ["reuse", "libraries", "what"]},
        {location: ["reuse", "libraries", "how"]},
        {location: ["reuse", "apis", "what"]},
      {subheading: "Frameworks"},
        {location: ["reuse", "frameworks", "what"]},
        {location: ["reuse", "frameworks", "frameworksVsLibraries"]},
      {subheading: "Platforms"},
        {location: ["reuse", "platforms", "what"]},
    {heading: "Cloud Computing"},
      {location: ["reuse", "cloudComputing", "what"]},
      {location: ["reuse", "cloudComputing", "services"]},
  {name: "Documentation"},
    {heading: "Other UML Models"},
      {location: ["modeling", "modelingStructures", "deploymentDiagrams"]},
      {location: ["modeling", "modelingStructures", "componentDiagrams"]},
      {location: ["modeling", "modelingStructures", "packageDiagrams"]},
      {location: ["modeling", "modelingStructures", "compositeStructureDiagrams"]},
      {location: ["modeling", "modelingBehaviors", "timingDiagrams"]},
      {location: ["modeling", "modelingBehaviors", "interactionOverviewDiagrams"]},
      {location: ["modeling", "modelingBehaviors", "communicationDiagrams"]},
      {location: ["modeling", "modelingBehaviors", "stateMachineDiagrams"]},
{week: "12"},
{week: "13"}
]%}


{% macro show_week_pagetop(week_num, category) %}

{% set week = weeks[week_num - 1] %}

{% set categories = {
  notices: {name: "Summary", file: "index", icon: icon_announcement, pagenav: 4},
  topics: {name: "Topics", file: "topics", icon: icon_book, pagenav: 3},
  project: {name: "Project", file: "project", icon: icon_project, pagenav: 4},
  tutorial: {name: "Tutorial", file: "tutorial", icon: icon_tutorial, pagenav: 4},
  admin: {name: "Admin Info", file: "admin", icon: icon_info, pagenav: 4}
} %}

<frontmatter>
title: "Week {{ week.num }} - {{ categories[category].name }}"
header: header.md
footer: footer.md
head: scheduleHead.md
pageNav: {{ categories[category].pagenav }}
</frontmatter>

<nav>
<ul class="pagination mt-2">
{%- set previous_status = " disabled" if week_num == 1 else "" -%}
{%- set next_status = " disabled" if week_num == 13 else "" -%}
<li class="page-item{{ previous_status }}"><a class="page-link" href="../week{{ (week_num - 1) }}/"><md>:glyphicon-chevron-left: **Previous Week**</md></a></li>
<li class="page-item">&nbsp;&nbsp;&nbsp;</li>
{% for c,v in categories %}
  {%- set is_active = " active" if categories[category] == v else "" -%}
  <li class="page-item{{ is_active }}"><a class="page-link" href="{{v.file}}.html">{{ v.icon }} {{v.name}}</a></li>
</li>
{% endfor %}
<li class="page-item">&nbsp;&nbsp;&nbsp;</li><li class="page-item{{ next_status }}"><a class="page-link" href="../week{{ (week_num + 1) }}/"><md>**Next Week** :glyphicon-chevron-right:</md></a></li>
</ul>
</nav>

<p/>

# Week {{ week.num }} <small><small>%%[{{ week.day }}]%% - {{ categories[category].name }}</small></small>

{% endmacro %}


{% macro show_week_summary(week_num) %}

<span id="summary">
<div class="container">
  <div class="row">
  <div class="col-sm border-right border-bottom">

{{ topics.show_week_schedule_main(week_num, all_topics, "", is_toc=true, is_flat=true) }}

<panel type="seamless" header="%%Full ToC%%">
  <include src="topics.md#toc" optional />
</panel>

  </div>
  <div class="col-sm border-bottom">

**Admin:**
<include src="admin.md#summary" optional/>
<include src="project-{{ module | lower }}.mbdf#summary" optional/>

  </div>
  </div>
</div>
</span>
<br>
{% endmacro %}

{% macro show_project_summary(ip_file=false, tp_file=false, milestone=false) %}
<div id="summary" class="lead border-bottom border-left ml-3 mb-3 pl-2" style="color: purple;">

{% if ip_file %}
**iP:**
<include src="../../admin/{{ ip_file }}#summary" />
{% endif %}
{% if tp_file %}
**tP:** {% if milestone %}<span class="border rounded text-success border-success pr-1 pl-1">:fas-tag: **{{ milestone }}**</span>{% endif %}
<include src="../../admin/{{ tp_file }}#summary" />
{% endif %}
</div>

{% endmacro %}


{% macro show_week_index_page(week_num) %}
<div class="website-content">
{{ show_week_pagetop(week_num, "notices") }}

<include src="notices-{{ module | lower }}.mbdf" optional />

{{ show_week_summary(week_num) }}
</div>
{% endmacro %}


{% macro show_week_admin_page(week_num) %}
<div class="website-content">
{{ show_week_pagetop(week_num, "admin") }}

{% if week_num == "1" %}
<box type="info" dismissible>

Admin info relevant to the week will appear in this tab.
</box>
{% endif %}

{{ show_weekly_admin_tasks(week_num) }}
</div>
{% endmacro %}


{% macro show_week_topics_page(week_num) %}
<div class="website-content">
{{ show_week_pagetop(week_num, "topics") }}

{% if week_num == "1" %}
<box type="info" dismissible>

* Topics allocated to the week will appear in this tab.
* If the lecture is in the 2nd half of the week (i.e., Wednesday 12 noon or later), the lecture in week `N` will cover topics allocated to the week `N+1` e.g., **Lecture 1 will cover Week 2 topics**, and so on.
</box>
{% endif %}
{{ topics.show_week_schedule(week_num, all_topics) }}
</div>
{% endmacro %}


{% macro show_week_tutorial_page(week_num) %}
<div class="website-content">
{{ show_week_pagetop(week_num, "tutorial") }}

{% if week_num == "1" %}
<box type="info" dismissible>

Information relevant to the week's tutorial will appear in this tab.
</box>
{% endif %}
<include src="tutorial-{{ module | lower }}.mbdf" optional />
</div>
{% endmacro %}


{% macro show_week_project_page(week_num) %}
<div class="website-content">
{{ show_week_pagetop(week_num, "project") }}

{% if week_num == "1" %}
<box type="info" dismissible>

Project-related information relevant to the week will appear in this tab.
</box>
{% endif %}
<include src="project-{{ module | lower }}.mbdf" optional />
</div>
{% endmacro %}


<!-- ============================= page content ============================================ -->

{% set week_to_show = "1" if current_week in ["-1", "0", "14"] else current_week %}
<include src="week{{ week_to_show }}/index.md" />
