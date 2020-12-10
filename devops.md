# DevOps

## Devops

developers - like change

operations team - like stability

DevOps \(DEVelopment OPeration\) – это набор **практик** для повышения эффективности процессов разработки \(Development\) и эксплуатации \(Operation\) программного обеспечения \(ПО\) за счет их непрерывной интеграции и активного **взаимодействия профильных специалистов** с помощью инструментов **автоматизации**.

Rapidly, frequently and reliably:

* building
* testing
* releasing

Culture:

* new operation tools
* agile engineering practices
* **increased collaboration** between development and operations

Aim:

* establish effective communication between development and operations teams
* automate process of source control checking, code review, code quality, change control
* CI, CD and cont. monitoring are provided
* make infrastructure as a code
* cover system with monitoring

## Practices:

### CI

* merge code into central repo
* automated tests and builds are run
* goal: find address box quicker, improve software quality, reduce time it takes to validate and release updates

### CD

* code changes are auto build, tested and prepared for release to prod
* expands CI by deploying code changes to test env and/or prod env after build stage
* deployment ready build artifact that passed auto test process

### Automation

* automation platform helps to describe entire technology stack as executable code
* helps to standartize dev, test and prod envs
* effectively deploy and manage cloud resources
* eliminate error pron and time consuming manual tasks
* improve cooperation between development and operations
* implement auto release pipelines
* enables velocity, scale, consistency and feedback

### Version Control

* software to track code changes
* store many, show 1 version at a time

### Configuration Management

* sysadmin use code to automate operating system and host config
* use of code make config changes repeatable and standartised
* no manual configuring of many OS, apps or server software

### Monitoring and Logging

* monitor organisations, metrics, logs to see how app and infrastructure performance impacts the experience of their products and user?? WTF
* capture, categorize and analyze data and logs generated by app and infrastructure =&gt; can see how changes impact users
* moniting matter as services should be online 24/7, app and update frequency increases

### Comminication and collaboration

* rely on collaboration
* main cultural aspect of devops
* automation physically bring together workflows and responsibilities of dev and ops teams
* chat apps
* issue or project tracking systems
* wikis
* other \(marketing, sales\) can collaborate more closely with the help of these tools

## Infrastructure as a code

a type of IT setup wherein developers or operations teams automatically manage and provision the technology stack for an application through software, rather than using a manual process to configure discrete hardware devices and operating systems. Infrastructure as code is sometimes referred to as programmable or software-defined infrastructure.

* describe tech stack with executable code
* the concept of managing operations env in the same way you do other code for general release
* no manual changes or scripts to make infrastructure adjustments
* IAAC != infrastructure automation, it's wider
* apply devops practices to automation scripts to ensure they are free of errors, able to be redeployed on multiple servers, can be rolled back in case of problems, can be engaged by both ops and dev teams.
* code systems: ansible, puppet - accessible for anyone with knowledge of modern code techniques and structures

Cloud services:

* private cloud: all by customer from storage, hardware, network, virtualization configs to OS,  middleware, data and app
* Infrastructure as a service: customer manages only OS, middleware, data and app; cloud provider all other
* platform as a service: customer manages only data, middleware and app; from OS to hardware - cloud responsibility
* software as a service: cloud manages everything

## CI

software development practice that engages developers to regularly merge changes to central repo with further auto build process and auto tests

Goals:

* find and fix mistakes, bugs as early as possible
* improve product quality
* reduce time between changes made and releases

**CI Principles**:

* managed central repo
* integrate changes as often as possible
* build every commit
* builds are self tested
* store very build
* have a history of builds
* use multiple envs - sorted by code stabulity running on them

### Git

* VCS: svn, mercurial, perforce
* multiple branches
* branch: feature, version or option
* distributed development
* decentralisation
* treansactional approach to changes
* ease of spreading changes: patches or comissions
* branch management

Workflows:

* mainline
* git flow
* github flow
* gitlab flow

#### Mainline

all work on main branch

#### github flow

* deployable master branch
* short-lived feature branches
* merge into master after review

#### gitlab flow

* CI optimized
* env specific branches for prod or preprod, ready for deploy

**Branching strategy**: define number of bracnhes and their functions

Improve quality

* design review
* code review
* testing
* one code, others look for bugs; use many quality methods

### CI pipeline

* VCS =&gt; source code
* build =&gt; package
* code test =&gt; test reports
* publish =&gt; verified packages

Artifact - file or package to deliver developers work result - jar, war, zip, exe, deb, rpm

Artifact repo - store all kinds of artifacts

* maven repo
* nexus/ artifactory

## CD

* dev env: unique for each developer
* QA - quality assurance - and testing \(гарантия качества\)
* all tests passed =&gt; build recommended for prod
* build should pass **Stage** / UAT - identical to prod env to avoid env dependent bugs
* then prod

software development practice when code changes are auto collected, tested and become ready for release in prod

* extends CI with deployment of builds to test or stage envs
* outcome - artifact ready for prod

### CD principles

* every successfull change can go to prod
* all steps automated
* test coverage as full as possible including unit tests, acceptance tests, performance/stability tests
* works best with canary releases: это метод, позволяющий снизить риск внедрения новой версии программного обеспечения в производство путем медленного развертывания изменений на небольшом подмножестве пользователей, прежде чем распространять их на всю инфраструктуру.

### CD pipeline

* deploy =&gt; code deploy to QA env
* QA tests =&gt; Test reports
* stage =&gt; release candidate

### Deployment

* automated: all steps are triggered by commit and no manual steps to deploy at all
* repeatable: each successfull build result stored; deploy any artifact to any env
* reliable: artifact can be retrieved from artifact repo; backups for everything

### Cont. deployment \(CDD\)

plus one step to CD: auto deploy to prod

* deploy =&gt; production

every change passed from pipeline is released to customers

## Docker

application container platform; makes use of linux cgroups and network namespaces

* cross platform
* deliveres app with its env
* high mobolity
* isolation: app and resourses are isolated
* own resourses isolated from other containers
* each app only uses resourses assigned to it
* complete control over traffic flow
* container can't see processes of other container
* container gets its' set of resources from processing to network stacks
* docker build: Build an image from a Dockerfile
* docker run: run container
* docker ps \(-a\)
* docker image rm

## Jenkins

* open source for CI/CD
* monitor VCS and start and monitor build system on changes
* provide reports and notifications
* CI: autorun test on non dev machine when code is pushed
* plugins
* written in java

## Sonar

manage code quality of app

* easy to add new languages support through plugins
* manages 7 steps of code quality:
* architecture & design
* duplications
* unit tests
* potential bugs
* complexity
* coding rules
* comments
* Jenkins builds code
* Sonar runs after each build
* alert thresholds can break the build

## Puppet

* open source systems managements tool
* centralising and automating config management
* CM tool to describe infrastructure as a code
* tools to automate testing, promotion and delivery of infrastructure changes with jenkins
* tools to deploy and manage jenkins itself
* jenkins jobs can be managed through infrastructure code ensuring jenkins is configured as intended

## Ansible

alternative for Puppet

* jenkins is only process orchestrator but not shell executor

## Chef

* infrastructure automation

## CI/CD pros & cons

Pros:

* automation eliminates human factor
* reduce time for product development and support
* visibility of all processes

Cons:

* more time & effort to automate everything and make tests
* highly qualified people to do it
* more work to define pipelines
