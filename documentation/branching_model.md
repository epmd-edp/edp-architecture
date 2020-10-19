# Branching Model and Version Numbering Principles

Get acquainted with the branching model and its types, explore the release steps, and the principles of the versioning:  
 
- [General Provisions](#general_provisions)
- [Release Steps](#release_steps)
- [Build Versioning](#build_versioning)

## General Provisions <a name="general_provisions"></a>

To number the service releases, the standard 4-digit numbering should be used: **`major.minor.maintenance-<build type>-build`**.
 
Find below the description of every character:
 
* major - changes rarely with the significant changes of functionality in a product, library, service, etc. The API contracts 
(_e.g. addresses, data composition_) can be changed only with an adjustment of this version;
* minor - increases when a new, relatively minor functionality is added between large releases;
* maintenance - is meant to track the hot-fixes - the critical fixes that cannot be stored for the next release;
* build type -  is meant to indicate the purpose of a build;
    * snapshot - an iterative build of new changes;
    * rc - release candidate;
    * hotfix - a set of changes for the previous release;
* build - an internal numbering, non-advertised for external consumers, incremented by a build system each time or connected 
to the commit from which the release has been built.

The project uses a branching model that specifies the following branch types:
 
* master -  an integration branch where code is prepared for the next release;
* release/* - a branch of a regular major release (with every Version.Major or Version.Minor change - 1st and 2nd digits 
are added) that is generated from master and returned to master when ready, thereby, the branch is not deleted. 
* feature/* - branches that contain a code with new functionality. These branches are generated from master and returned 
to master when ready. As soon as the merge process is completed, the branches will be deleted from the central repository.  

_**INFO**: Every branch is tagged with the build number._
 
## Release Steps <a name="release_steps"></a>

Inspect the following standard points and release steps that should be presented/performed:
 
1. A new branch will be created with the `release-<version>` name on the EDP admin page of a specific service;
2. A developer should change the service version from `<version>-SNAPSHOT` to `<version>-RC` in the release branch;
3. A developer should increment a minor service version in the master branch, thus starting to work on the preparing for 
the new release;
4. A developer should create a new pipeline (_on the EDP admin page in the Continuous Delivery section_) and define:
    
    a. A pipeline name displayed the release version that will be tested;
    
    b. Applications that indicate a list of the installed on the circuit applications. Pay attention to select the correct 
    release branch for every application; 
    
    c. Stages that display a number of environments created for the current release (e.g. dev and test);
5. It is possible to deploy service into the EPAM Delivery platform and to debug the release as well.
 
_**INFO**: When finished working on the release, it is necessary to:_
* _Delete the created pipelines;_
* _Merge the **`release-<version>`** branch with the **`master`** branch._

## Build Versioning <a name="build_versioning"></a>
 
Any commit that has passed the code-review process is stored in the Git repository. 
The changes in the repository status trigger the Jenkins job that builds a project, launches the tests, etc. After the 
successful execution, the current commit will be marked with the `<>-<>-<>` label. As a result, this build becomes available for 
deployment to the EDP stages. It becomes possible to use this build in order to pass it through the stages created in the 
CD pipeline.
 
>_**NOTE**: The JIRA tickets without the Fix Version label won`t be transferred into the QA testing status. 
When creating a bug, the current version and the stage (where the bug was received) should be indicated in the 
Environment field by using the same naming as in the Fix Version field._

Find below the standard points and main steps that should be presented/performed:
 
1. After the JIRA ticket is completed and the code-review process is successfully passed, a developer sets the Resolved status 
 for the task. The **Fix Version** field remains empty;
2. The team leader of the development team performs the deployment to the stage and checks the build functionality where the 
 tasks from the previous point are stored;
3. After the successful passing of the verification on the dev stage:
    
    a. All tasks with the status Resolved will be updated by the build version that has been already transferred to the dev stage, 
 e.g. `qr-codes / <> - <> - <>`;
 
    b. All these tasks will be transferred into the QA testing status;
    
    c. The build will be marked as available for deployment into the next pipeline stage.

>_**NOTE**: After the deployment to the dev stage was performed and the developers checked the functionality, 
>a special mark will be added identifying that the current build is suitable for deploying on the test stage and so on._