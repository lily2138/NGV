# Automotive SPICE 4.1 â€” Annex B: Information Item Characteristics (Reference Extract)

> Source: VDA QMC "Automotive SPICE PAM 4.1" (public preview PDF), Annex B, pp.122-152.
> Extracted verbatim (OCR via pdftotext -layout) for offline reference by the aspice-cl2-auditor skill.
> Use this to look up the expected content/characteristics of a specific information item (work product type) referenced by an ID such as `13-19 Review evidence` or `08-56 Schedule`.
> Per the source text: "It is not intended to use the listed characteristics as a checklist." Use it as guidance on what a well-formed work product of that type typically contains, not as a pass/fail checklist.

Annex B Information Item Characteristics

The characteristics of the information items are defined using the schema in table B.1. See section
3.3.2 on the definition and explanation on how to interpret information items and their characteristics.

Information item  An identifier number for the information item which is used to reference the information
identifier        item.
Information item
name              Provides an example of a typical name associated with the information item
                  characteristics. This name is provided as an identifier of the type of information item the
Information item  practice or process might produce. These information items would be expected to be
characteristics   part of work products in a project or organization, see also Section 3.3.2. Therefore, the
                  structure of the information items varies.

                  Information items characteristic provide:

                       · Purpose and scope of an information item as description

                       · Items and elements that it typically identifies
                       · Characteristics that can be included

                       · Examples of the characteristics, events when characteristics are observable
                       · References to norms, standards and practitioners
                  The assessor may use these in evaluating the samples provided by the organizational
                  unit. It is not intended to use the listed characteristics as a checklist. Some
                  characteristics may be contained in other work products, as it would be found
                  appropriate in the assessed organization.

                  Table B.1 -- Structure of information item characteristics (IIC) table

ID     Name                      Characteristics
01-03  Software component
                                  See definition in section 0.
01-50  Integrated software        Identifies:

01-52  Configuration item list           · The Software element in the software architecture
                                              above the software unit level, or an implementation
© VDA Quality Management Center               of such a software element.

                                  Includes:
                                         · Design model element, or executable source code
                                              such as libraries, modules, services or scripts.

                                  A functional executable software which has been integrated
                                  from multiple software components.
                                  Identifies:

                                         · All configured software elements
                                  Includes:

                                         · Application parameter
                                  Examples and references:

                                         · Simulator with stubbing
                                         · Object code
                                  List of configurable items under configuration control.
                                  Identifies:
                                         · Name of configuration item
                                         · Work products
                                         · Unique reference to the configuration item
                                  Includes:

                                                                                                          122
ID     Name                        Characteristics
01-53  Trained ML model
01-54  Hyperparameter                      · Configuration item attributes and properties

02-01  Commitment / agreement       Resulting output machine learning (ML) model of the ML
                                    training process
03-03  Benchmarking data
03-04  Customer satisfaction data   Identifies:
                                           · Set of weights optimized during the training

                                    Includes:
                                           · Software representing the ML architecture
                                           · Set of hyperparameters

                                    Settings or configurations that are used to control the learning
                                    process of a machine learning model.

                                    Identifies:
                                           · Description
                                           · Initial value
                                           · Value of the results of the ML training

                                    Includes:
                                           · Number of epochs
                                           · Scaling of network (number of layers or neurons per
                                                layer)

                                    Examples and references:
                                           · Learning rate of training, Loss function

                                    Mutual arrangement between two or more parties regarding
                                    terms of a transaction or relationship.

                                    Identifies:
                                           · All involved parties
                                           · Purpose of the collaboration
                                           · Definitions
                                           · Confidentiality
                                           · Termination conditions

                                    Includes:
                                           · Timings and durations
                                           · Resources, for example people and equipment
                                           · Efforts
                                           · Facilities
                                           · Responsibilities

                                    Data resulting out of performance measurement to establish a
                                    comparison of performance values.

                                    Identifies:
                                           · Measurement of current performance
                                           · Historical and current values
                                           · Criteria and information to be benchmarked

                                    Includes:
                                           · References to metric
                                           · References to their purpose, for example: goals,
                                                process, product or involved market

                                    Active and passive feedback information of a customer.

                                    Identifies:
                                           · Related products and services

© VDA Quality Management Center    123
ID     Name                       Characteristics
03-06  Process performance
       information                        · Mechanism to collect data, for example field
03-50                                          performance, survey, interview, meeting minutes,
03-51  Verification measure data               product demo
       Machine Learning data set
                                   Includes:
                                          · Notes
                                          · Observations
                                          · Trend data
                                          · Opportunities
                                          · Level of customer satisfaction

                                   Measurements about quantitative or qualitative measurable
                                   indicators, that match information for performance evaluation.

                                   Identifies:
                                          · Measurement metrics for the calculation of the
                                               quantitatively or qualitatively measurable indicators
                                          · Efforts
                                          · Time
                                          · Data

                                   Includes:
                                          · Performance level definition, for example usage of
                                               defined capacity, agreements.
                                          · Targets definitions, for example throughput
                                          · Utilization data of resources, for example up time,
                                               service outage time
                                          · Time schedules
                                          · Task completion criteria, for example: job run time
                                          · Quality of process and work products, for example
                                               non conformances ratio

                                       References and Examples:
                                          · Process performance respective deliveries, service
                                               level, operational performance

                                   Data recorded during the execution of a verification measure.

                                   Identifies:
                                          · Logging data, for example raw data or tool generated
                                               output
                                          · Values of measurements and calculations
                                          · Protocols of simulations
                                          · Review data

                                   Includes:
                                          · Finding records

                                   Selection of data for machine learning training and validation,
                                   or test of a machine learning model.

                                   Identifies:
                                          · Patterns
                                          · Relationships
                                          · Features

                                   Includes:
                                          · Annotations and labels
                                          · ML Training and Validation Data Set
                                          · ML Test Data Set

© VDA Quality Management Center   124
ID     Name                      Characteristics
03-53  ML data
03-54  Hardware production data   Data used for machine learning, attributed by metadata.
04-02  Domain architecture
                                  Identifies:
04-04  Software architecture             · Unique ID
                                         · Attributes
                                         · Data characteristics, for example audio recordings,
                                              sensor data, pictures and videos
                                         · Data created by an algorithm

                                  Includes:
                                         · Data created by processing of other data, for
                                              example added noise, changed colors or merged
                                              pictures

                                  Data used and created during hardware production.

                                  Identifies:
                                         · Layout data, e.g., in GERBER format
                                         · Test coverage

                                  Includes:
                                         · Bill of material

                                  Examples and References:
                                         · In semiconductor development, layout data can be
                                              mask data, for example in GDS2 format.

                                  High-level design and structure specific to a domain.

                                  Identifies:
                                         · Domain model(s) tailored from
                                         · Asset specifications
                                         · Definition of boundaries and relationships with other
                                              domains, for example within a Domain Interface
                                              Specification
                                         · Domain vocabulary
                                         · Domain representation standard

                                  Includes:
                                         · Justifying rationale for the chosen architecture
                                         · Functions and features
                                         · Capability and concepts of the domain

                                  High-level design and structure of a software.

                                  Identifies:
                                         · Overall software structure
                                         · Functional behavior of the software components
                                         · Nonfunctional characteristics
                                         · Settings for application parameters
                                         · Technical characteristics of interfaces, for example
                                              application programming interface (API)
                                         · Dynamic behavior within different states and
                                              operating modes, for example: start-up, shutdown,
                                              calibration
                                         · Timing definitions for example slices, cycle times
                                         · Priorities, for example of processes and threats
                                         · Events handling, for example interrupts with their
                                              priorities

© VDA Quality Management Center  125
ID     Name                      Characteristics
04-05  Software detailed design
04-06  System architecture        Includes:
                                         · Justifying rationale for the chosen architecture
04-51  ML architecture                   · Explanatory annotations, for example with natural
                                              language, for single elements, diagrams or models.

                                  Internal structure and behavior of software elements.

                                  Identifies:
                                         · Control flows
                                         · Format of input/output data
                                         · Algorithms
                                         · Data structures
                                         · Variables

                                  Includes:
                                         · Justifying rationale for the chosen design
                                         · Interfaces
                                         · Explanatory annotations
                                         · Elements of semi-formal language, for example UML,
                                              SysML

                                  Examples and references:
                                         · Expression in formal or semi-formal language may
                                              be used in model based developed design.

                                  High level design and structure of a system.

                                  Identifies:
                                         · Overview of the system structure
                                         · System elements
                                         · Behavior of system elements, for example operation
                                              modes, calibration sequences, performance.
                                         · Behavior with the environment
                                         · Interfaces between system elements and
                                              environment
                                         · Hardware-software interfaces, for example input-
                                              output pins of microcontrollers
                                         · Parameters, for example of resource and
                                              performance characteristics
                                         · Domain specific engineering references, for example
                                              mechanical engineering evaluations for thermal
                                              influence.

                                  Includes:
                                         · Justifying rationale for the chosen architecture
                                         · References to underlying architecture, for example
                                              Hardware architecture (04-52), Software architecture
                                              (04-06), or an ML-architecture (04-51)

                                  Examples and references:
                                         · Vehicle wiring overview with identification of wiring
                                              technologies, control units and wireless interfaces for
                                              connectivity.

                                  High-level design and structure of a machine learning system.

                                  Identifies:
                                         · Overall structure of the ML-based software element

© VDA Quality Management Center  126
ID     Name                      Characteristics
04-52  Hardware architecture
04-53  Hardware detailed design          · Elements including an ML model and other ML
04-54  Hardware schematics                    architectural elements

                                         · Interfaces within the ML-based software element
                                         · Interfaces to other software elements
                                         · Resource consumption objectives

                                  Includes:
                                         · Justifying rationale for the chosen architecture
                                         · Details of the ML model like used layers, activation
                                              functions, loss function, and backpropagation
                                         · Hyperparameter ranges and initial values for training
                                         · References to ML requirements

                                  High-level design and structure of physical components in an
                                  electronic device system.

                                  Identifies:
                                         · Overall hardware structure
                                         · Hardware components
                                         · Own developed and supplied hardware components
                                         · Hardware component interfaces

                                  Includes:
                                         · Justifying rationale for the chosen architecture
                                         · Relationship and dependency between hardware
                                              components
                                         · Specifics for hardware variants
                                         · Power supply, thermal and grounding concepts

                                  Examples and references:
                                         · Integrated circuits (IC) components placement is
                                              documented on "floorplan" architecture document.

                                  Internal structure and behavior of hardware subsystems.

                                  Identifies:
                                         · Interconnections between the hardware parts
                                         · Interfaces of the hardware parts

                                  Includes:
                                         · Dynamic behavior in modes of operation and internal
                                              states, for example in power-up and power-down
                                              sequences.
                                         · Timing specifications, for example frequencies and
                                              delays
                                         · Technologies and their characteristics, for example
                                              modulations and filter settings.
                                         · Justifying rationale for the chosen design
                                         · References to datasheets, application notes
                                         · Constraints for layout

                                  Detailed diagrams of components and connections of a
                                  hardware system.

                                  Identifies:
                                         · Hardware parts
                                         · Connections of the hardware parts

                                  Includes:

© VDA Quality Management Center  127
ID     Name                        Characteristics
04-55  Hardware layout
                                           · Identification information of hardware parts and
04-56  Hardware element interface               variants.

06-04  Training material            Physical arrangement of components on a circuit board or
06-50  Integration sequence         within a device.
       instruction
                                    Identifies:
                                           · Placement of the hardware parts
                                           · Manufacturing data, for example circuit paths, testing
                                                points
                                           · material specific adaptations
                                           · Shapes, masks, labels
                                           · layout identification

                                    Includes:
                                           · Justifying rationale for the chosen design

                                    Examples and references:
                                           · Printed circuit boards (PCB) layouts include vias,
                                                different layers
                                           · Soldering mask

                                    Description of interactions between different physical
                                    components within a hardware system.

                                    Identifies:
                                           · Electrical interconnections
                                           · Thermal interfaces
                                           · Electrical characteristics
                                           · Signal tolerance
                                           · Performance needs, for example bandwidth

                                    Includes:
                                           · Definition of output, input, type
                                           · heat dissipation
                                           · communication parameters
                                           · signal parameters

                                    Examples and references:
                                           · Standardized interfaces and protocols like SPI, I2C,
                                                CAN.

                                    Resources created or used to support learning.

                                    Identifies:
                                           · Knowledge for operation, maintenance or
                                                development of systems.
                                           · Area of application

                                    Includes:
                                           · Course listings and availability
                                           · Procedures
                                           · Guidance
                                           · Training identification information

                                    Workflow definition to combine, assemble or connect different
                                    systems or components into an integrated configuration.

                                    Identifies:
                                           · Physical elements, for example hardware,
                                                mechanical and wiring elements.

© VDA Quality Management Center    128
ID     Name                      Characteristics

06-51  Tailoring guideline               · Software
                                         · Application parameters
06-52  Backup and recovery               · Sequences and order of integration
       mechanism information             · Preconditions

07-04  Process metric             Includes:
                                         · Safety instructions
07-51  Measurement result                · Recovery or fallback procedures
                                         · Verification activities
© VDA Quality Management Center
                                  Set of rules to adapt processes, methods, documentation, or
                                  requirements to a specific project, product, or organizational
                                  context.

                                  Identifies:
                                         · Criteria for tailoring
                                         · Proceeding of tailoring
                                         · Approval conditions
                                         · Integrity and consistency needs of the defined
                                              process

                                  Includes:
                                         · Tailoring matrix
                                         · Tailoring triggers
                                         · Assets of the defined process

                                  Processes and tools used to create backups of data and
                                  restore it in case of loss or corruption.

                                  Identifies:
                                         · Description and confirmation of backup and recovery
                                              mechanisms
                                         · References to corresponding procedures or
                                              regulations

                                         · Measurements about the process' performance:
                                         - ability to produce sufficient work products
                                         - adherence to the process
                                         - time it takes to perform process
                                         - defects related to the process

                                         · Measures the impact of process change
                                         · Measures the efficiency of the process

                                  Outcome of gathering qualitative or quantitative data.

                                  Identifies:
                                         · Data sources
                                         · Data ownership
                                         · Evaluation and measurement workflow
                                         · Conformity requirements, for example on data
                                              protection
                                         · Approval and acceptance criteria

                                  Includes:
                                         · Benchmarking needs
                                         · Copyright
                                         · Metric references, for example to process, project or
                                              quality metric

                                                                                                          129
ID     Name                         Characteristics
07-61  Quantitative process metric
                                     Examples and References:
07-62  Process analysis technique           · Quality metrics could be identified in survey of the
07-63  Process control limits                    end customer, for example for usability, reliability and
07-64  Process measurement data                  efficiency.
08-53  Scope of work                        · Field failure measurement for performance of 5D
                                                 cycle time.
                                            · Project metrics for project management, for example
                                                 resource utilization against plan.

                                     Quantitative evaluation of measurable relationships and
                                     characteristics of a process.

                                     Identifies:
                                            · Measurable indicators
                                            · Relationship of the quantitatively measurable
                                                 indicators
                                            · Trend evaluation

                                     Includes:
                                            · Process elements and descriptions
                                            · Repositories and tools, for example to store historical
                                                 data

                                     Examples and References:
                                            · Information needs derived from business goals.

                                     Workflow description to control process within specific limits.

                                     Identifies:
                                            · Calculation specification, for example statistic
                                                 algorithm
                                            · Mathematical references
                                            · Data structure

                                     Includes:
                                            · Frequency of data collection

                                     Boundaries used to monitor and manage a process.

                                     Identifies:
                                            · Quantitative control limits
                                            · Relevant process metrics

                                     Data collected across process instances.

                                     Identifies:
                                            · Attributes of data, for example timestamps
                                            · Relation to process measurement metrics
                                            · Storage and retrieval
                                            · Controls over access

                                     Definition of tasks, responsibilities and deliverables of a
                                     project or program.

                                     Identifies:
                                            · Deliverables and their intended use
                                            · Functional descriptions
                                            · Deliveries and delivery dates
                                            · Milestones
                                            · Work products
                                            · Activities

© VDA Quality Management Center     130
ID     Name                          Characteristics
08-54
08-55  Feasibility analysis                · Out of scope definitions
08-56  Risk measure                        · Acceptance requirements

08-57                                Includes
                                           · Customer and market information
                                           · Applicable standards and legal requirements
                                           · Reuse options
                                           · Integration of third-party deliveries

                                     An evaluation of the ability to achieve the project objectives
                                     within available time and resources.

                                     Identifies:
                                           · Available resources
                                           · Efforts, for example variable and fixed duration
                                                 activities

                                     Includes:
                                           · Dependencies to supporting and shared resources
                                           · Technical evaluation
                                           · Recovery options
                                           · Critical path analysis

                                     Quantitative or qualitative value to express the level of a risk.

                                     Identifies:
                                           · Risk to be mitigated, avoided, or shared (transferred)
                                           · Related activities
                                           · Criteria for success or failure of activities
                                           · Frequency of monitoring

                                     Includes:
                                           · Exposure and detectability information
                                           · Originator
                                           · Alternative treatment options
                                           · Risk justifications, for example as claims

       Schedule                      A plan that defines the times and sequences for events, tasks,
                                     or activities.
       Validation measure selection
       set                           Identifies:
                                            · Activities
                                            · Timing requirements, for example start and due
                                                 dates
                                            · Dependencies between activities
                                            · Critical path

                                     Includes:
                                            · Progress evaluation, for example completion of
                                                 individual activities
                                            · Scheduled resources
                                            · Input data
                                            · Evaluation of resource workload
                                            · Shared resources

                                     A set of validation measures selected for a specific purpose.

                                     Identifies:
                                            · Validation measures

© VDA Quality Management Center                       131
ID     Name                      Characteristics

08-58  Verification measure              · Scope of their application, for example a variant,
       selection set                          regression or a subcomponent

08-59  Validation measure         Includes:
                                         · Identification of the validation measures
08-60  Verification measure              · Criteria for re-validation, for example in the case of
                                              changes
© VDA Quality Management Center          · Dependencies

                                  A set of verification measures selected for a specific purpose.

                                  Identifies:
                                         · Verification measures
                                         · Scope of their application, for example a product
                                              variant, regression or a subcomponent

                                  Includes:
                                         · Identification of the verification measures
                                         · Criteria for re-verification, for example in the case of
                                              changes
                                         · Dependencies

                                  Tool or method used to ensure the accuracy and reliability of a
                                  measurement or test under realistic conditions to validate the
                                  intended use.

                                  Identifies:
                                         · Description of test scope
                                         · Measurement to be performed during the test
                                         · Test steps description
                                         · Pass/fail criteria, for example from end user survey

                                  Includes:
                                         · Simulation scenarios
                                         · Emulation
                                         · Entry criteria
                                         · Techniques and resources
                                         · Validation environment setup and configuration
                                         · Sequences

                                  Tool or method used to ensure the accuracy and reliability of a
                                  measurement or test under specified conditions to verify
                                  specified functionality.

                                  Identifies:
                                         · Description of test scope, for example fault injection
                                              safety case
                                         · Classifications, for example black-box or grey-box
                                              test
                                         · Measurement to be performed during the test, for
                                              example an optical inspection
                                         · Test steps description
                                         · Pass/fail criteria, for example from end user survey

                                  Includes:
                                         · Simulation scenarios
                                         · Emulation
                                         · Entry criteria
                                         · Equivalence classes and boundary values

                                                                                                          132
ID     Name                       Characteristics
08-61  Resource allocation
                                          · Calculations and mathematical functions
08-62  Communication matrix               · Techniques and resources, for example review
08-63  Process monitoring method
08-64  ML test approach                        verification
                                          · Verification environment setup and configuration
                                          · Sequences

                                   Distribution of resources to tasks and locations.

                                   Identifies:
                                          · Resources identification information
                                          · Tasks
                                          · Locations
                                          · Timing needs
                                          · Roles
                                          · Restrictions of availability

                                   Includes:
                                          · Workload evaluation
                                          · Physical and material resources

                                   Examples and references:
                                          · Resource allocation for a test team, for example
                                               persons, tool licenses, test hardware

                                   Relationships and dependencies of an organization to
                                   manage communication.

                                   Identifies:
                                          · Affected internal and external stakeholders
                                          · Roles
                                          · Contact information
                                          · Definition of affected interfaces between
                                               stakeholders
                                          · Communication subject

                                   Includes:
                                          · Communication means and frequency
                                          · Documentation needs of the communication, for
                                               example type of record.

                                   Documentation of workflow to measure and to control
                                   boundaries of a process.

                                   Identifies:
                                          · Methods of analysis
                                          · Measurements
                                          · Criteria for monitoring
                                          · Boundaries and limits of measures

                                   Includes:
                                          · Measurement frequency and technology

                                   Approach describing criteria and activities to test ML models.

                                   Identifies:
                                          · ML test scenarios
                                          · Distribution of data characteristics, for example
                                               gender of persons or weather conditions
                                          · Related ML requirements
                                          · Pass/fail criteria
                                          · Entry and exit criteria

© VDA Quality Management Center   133
ID     Name                         Characteristics
08-65
       ML training and validation         · Environment setup and configuration
08-66  approach                          Includes:
10-00
       Measures against deviations           · References, for example with test data set
10-50  in quantitative process
       analysis                     Approach describing method for evaluating a trained ML
       Process description          model using data to confirm its accuracy and for the intended
                                    task.
       Role description
                                    Identifies:
                                          · Entry and exit criteria
                                          · Approaches for hyperparameter tuning / optimization
                                          · Approach for data set creation and modification

                                    Includes:
                                          · Training environment setup and configuration
                                          · Resources
                                          · Provision of input data
                                          · Storage of output data
                                          · Methods to control robustness, for example random
                                                dropout

                                    Definition of corrective measures for quantitative process
                                    control.

                                    Identifies:
                                          · Corrective measures
                                          · Implementation boundaries
                                          · Causes of variation
                                          · Timing requirements
                                          · Evaluation requirements, for example data filtering.

                                    Description of a standard or a defined process.

                                    Identifies:
                                          · Scope, purpose and intended use
                                          · Activities including their description and
                                                dependencies
                                          · Entry and exit criteria such as input information
                                                needed and expected outputs for activities
                                          · Templates
                                          · Guidance documents, for example guidelines, work
                                                instructions, standards or method descriptions

                                    Includes:
                                          · Roles assigned to process activities, for example as
                                                RASIC or to work products
                                          · Sequence and interaction of activities within the
                                                process
                                          · Sequence and interaction of the process to other
                                                processes
                                          · Tailoring guidelines

                                    Definition of a process role.

                                    Identifies:
                                          · Name/identifier
                                          · Assigned activities, for example as RASIC
                                          · Responsibilities
                                          · Authorities

© VDA Quality Management Center                      134
ID     Name                           Characteristics
10-51  Qualification method
       description                             · Required competencies, skills, and experience
10-52
11-03  Process resource and             Includes:
       infrastructure description              · Reference to qualification methods

       Release note                     Description of a qualification method for human resources.

                                        Identifies:
                                               · Competence category, for example product, process
                                                    or tools
                                               · Management level and title
                                               · Subject specific needs
                                               · Name
                                               · Required level of knowledge, for example to
                                                    standards and norms
                                               · Type of method, for example as formal training, on
                                                    the job, mentoring or coaching

                                        Includes:
                                               · Reference to courses and training material

                                        Description of a non-human resource.

                                        Identifies:
                                               · Facilities
                                               · Tools and licenses
                                               · Networks
                                               · Services, for example by internal or external
                                                    providers
                                               · Samples

                                        Includes:
                                               · Evidence for tool qualification if relevant, for example
                                                    within safety critical usage.

                                   Documentation of content provided in the release.

                                        Identifies:
                                               · Set of functionalities provided in the release
                                               · Limitations in relation to the committed scope
                                               · Known non-conformities
                                               · Application parameters
                                               · Configurations and variants
                                               · Unique name and version of the release.
                                               · Additional or removed functionalities
                                               · Changed or improved functionalities
                                               · Documentation of resolved non-conformities

                                        Includes:
                                               · Intended area and environment of usage
                                               · Impact to other components linked to the release
                                               · Upstream or downstream compatibility of delivered
                                                    release
                                               · Copyright and license information
                                               · Result of verification and validation measures
                                               · Approval for delivery of the release by responsible
                                                    roles
                                               · Dependencies to other linked products, for example
                                                    hardware revision.

© VDA Quality Management Center    135
ID     Name                      Characteristics
11-04  Product release package
                                  Set of Elements delivered in the product release.
11-05  Software unit              Identifies:

11-06  Integrated system                 · Physical components
                                         · Elements necessary for intended use
11-50  Deployed ML model
                                         · Warnings and alerts
12-03  Reuse candidate                   · Application Parameters

© VDA Quality Management Center   Includes:
                                         · Documentation to maintain or service the product
                                         · Information for the user, for example installation and
                                              setup instruction within a manual.

                                  Software element not decomposed to a lower level.
                                  Identifies:

                                         · Single functions
                                         · Set of functions

                                  Includes:
                                         · Intended use and defined functionality, for example
                                              within a specification or an agreement

                                  Examples and References:

                                        · Representation of a software element at the lowest

                                              level in a conceptual model.

                                  Set of elements composed from
                                  different units or integrated sub-systems.
                                  Identifies:

                                         · The intended use
                                         · Boundaries, for example application parameters

                                  Includes:
                                         · All configured elements, for example references to
                                              requirements specification

                                  Deployed ML model
                                  Identifies:

                                         · The source code derived from the trained ML model
                                              that shall be executed in the target system.

                                  Examples and references:
                                         · It may differ from the trained ML model which often
                                              requires powerful hardware and uses interpretative
                                              languages.
                                         · The deployed ML model is usually written in
                                              programming languages like C/C++.

                                  Description of a product that might be reused.

                                  Identifies:
                                         · Name of the product
                                         · Person responsible for the product
                                         · Reuse goals and objectives
                                         · List of reuse assets
                                         · Issues/risks of reusing the product
                                         · Person responsible for the qualification of the product
                                              to be reused
                                         · Type of the product's provision, for example storage
                                              location or delivery details

                                                                                                          136
ID     Name                      Characteristics
13-06  Delivery evidence
13-07  Problem                    Includes:
                                         · Specific requirements
13-08  Baseline
13-09  Meeting support evidence   Evidence of items shipped or electronically delivered to
                                  customer.

                                  Identifies:
                                         · Receiver
                                         · Delivery address
                                         · Delivery date
                                         · Acknowledgment of receipt

                                  Includes:
                                         · Identification information

                                  Description of an issue.

                                  Identifies:
                                         · Submitter
                                         · Version it was identified
                                         · Classification, for example criticality, urgency or
                                              relevance
                                         · Project phase in which problem is recorded
                                         · Owner
                                         · Status
                                         · Technical root cause
                                         · Potential effects on other systems
                                         · Expected closure date

                                  Includes:
                                         · Identification
                                         · References to other affected domains, subprojects,
                                              or programs
                                         · Relationships to dependencies like changes,
                                              preventive measures or other problems

                                  A coherent set of work products which are consistent and
                                  complete and may serve as basis for next process steps
                                  and/or delivery. A baseline must be unique and not changed
                                  any more.

                                  Identifies:
                                         · All work products belonging to the baseline
                                         · References using the configuration item properties

                                  Includes:
                                         · Name
                                         · Version
                                         · State

                                  Agenda and minutes of a meeting.

                                  Identifies:
                                         · Name
                                         · Purpose
                                         · Date and place held
                                         · Attendees
                                         · Outcomes, decisions

                                  Includes:

© VDA Quality Management Center  137
ID     Name                      Characteristics
13-13  Product release approval
13-14  Progress status                   · Reference to previous minutes
                                         · Open issues
13-16  Change request                    · Action points including responsibilities and due dates
                                         · Next meeting

                                  Evidence of approval for a product release.

                                  Identifies:
                                         · Release date
                                         · Name and role of approver
                                         · Intended customer
                                         · Restrictions and limitations for usage

                                  Includes:
                                         · Delivery / shipping address
                                         · Release information of what is to be shipped or
                                              delivered
                                         · If applicable, supplier approval evidence(s)

                                  Set of indicators to document the achievements created by
                                  performing process activities according to the committed work
                                  to the former phase.

                                  Identifies:
                                         · Status of work activities, for example in respect to a
                                              plan
                                         · Evidence of the committed outcome
                                         · Fulfilment of criteria within the state model
                                         · Limitations of outcome or achievements in respect to
                                              the committed objectives, for example deviations of
                                              performed verification

                                  Includes:
                                         · Timing references, for example in relation to
                                              schedule, milestones
                                         · Efforts

                                  Examples and references:
                                         · Status of actual quality against planned quality

                                  Request to change scope or impacts on planned activities or
                                  outcomes.
                                  Identifies:

                                         · Scope and purpose of the change activities
                                         · Originator of the change
                                         · Impacted operation environment
                                         · Process performance
                                         · Environment of usage for the process outcome
                                         · Infrastructure or resources
                                         · Documentation needs

                                  Includes:
                                         · Impacted outcomes and achievements
                                         · Process objectives
                                         · Approval for implementation of a change
                                         · Limitations to be considered
                                         · Criteria to verify the fulfillment of the implementation

© VDA Quality Management Center  138
ID     Name                      Characteristics
13-18
       Quality conformance        Documents the fulfillment of quality related criteria.
       evidence                   Identifies:

13-19  Review evidence                   · Process performance
                                         · Work product compliance
13-24  Validation results                · Verification criteria
                                         · Process outcomes
13-50  ML test results                   · Achievements
                                         · Success factors
© VDA Quality Management Center          · Performance objectives
                                  Includes:
                                         · References to quality activities
                                         · Data collected

                                         · Measurement and calculation

                                  A proof to demonstrate a structured check of a work product
                                  or a process has taken place.

                                  Identifies:
                                         · Name and version of the review object
                                         · Names and roles of the people who performed the
                                              review
                                         · Date
                                         · Status
                                         · Review criteria, for example review method,
                                              coverage, justification
                                         · Non-conformances found
                                         · Improvement suggestions

                                  Includes:
                                         · Documents considered, for example checklists,
                                              guidelines, work instructions
                                         · Time spent
                                         · Applicable standards

                                  Documented evidence confirming whether the end product
                                  meets the intended use expectations.

                                  Identifies:
                                         · Data, logs, feedback, or documentation
                                         · Measures passed
                                         · Measures not passed
                                         · Measures not executed
                                         · Rationale, for example security claims
                                         · Information about the execution (date, participants,
                                              etc.)
                                         · Abstraction or summary of results

                                  Results of ML test activities
                                  Identifies:

                                         · Test data and logs
                                         · Test data with correct results
                                         · Test data with incorrect results
                                         · Test data not executed, and a rationale
                                  Includes:
                                         · Information about the test execution (date, partici-

                                              pants, model version etc.)

                                                                                                          139
ID     Name                      Characteristics
13-51  Consistency evidence
                                        · Abstraction or summary of ML test results
13-52  Communication evidence
                                  Evidence of information to be semantically coherent along
13-53  Qualification evidence     relevant artifacts, ensuring completeness, purpose and
                                  maturity of processes, tasks and products throughout their
© VDA Quality Management Center   lifecycle.

                                  Identifies:
                                         · Traceability information, for example hyperlinks, re-
                                              pository location or editorial references.
                                         · Naming conventions
                                         · Relevant artifacts
                                         · Revision and revision history information
                                         · Change documentation and analysis information

                                  Includes:
                                         · Meta-information, for example database identifiers,
                                              notes in Git commits comments

                                  Examples and References:

                                        · Evidence of Definition of Done (DoD) adherence.

                                  Evidence of interpersonal communication.

                                  Identifies:
                                         · Scope of information
                                         · Need for feedback, for example an expected confir-
                                              mation within one week
                                         · Meta data, for example time when communication
                                              was done or how information was distributed.

                                  Includes:
                                         · Personal information
                                         · Work-flows, for example within tools

                                  Examples and References:
                                         · E-mails and other forms of memos
                                         · Verbal statements
                                         · Meeting minutes, for example in standups
                                         · Electronic media, for example webcasts, blog posts,
                                              intranet forum
                                         · Chat protocols
                                         · Wiki pages
                                         · Photo protocol

                                  Evidence that the products for reuse are qualified for the
                                  intended use of the deliverable.

                                  Identifies:
                                         · Qualification checklist
                                         · Passed items
                                         · Failed items
                                         · Pending items
                                         · Problems identified during qualification
                                         · Recommendation of actions
                                         · Conclusions of qualification

                                  Includes:
                                         · Risk analysis
                                         · Approval
                                         · Applicable standards

                                                                                                          140
ID     Name                      Characteristics
13-55
       Process resource and       Documentation that the required resources for performing the
       infrastructure             defined process are made available, allocated, used and
       documentation              maintained.

14-01  Change history             Identifies:
                                         · Information on availability, allocation and usage of
14-02  Corrective action                      resources
                                         · Facilities
14-10  Work package                      · Tools and corresponding licenses
                                         · Networks
© VDA Quality Management Center          · Services
                                         · Needs for samples, for example prototype protection

                                  Includes:
                                         · Maintenance information, if applicable

                                  Structured, chronological record of modifications made to an
                                  object (document, file, software component, etc.) over its
                                  lifecycle.

                                  Identifies:
                                         · Version information about changed object
                                         · Date of change
                                         · Description of change
                                         · Originator

                                  Activity required to resolve a problem.

                                  Identifies:
                                         · Initial problem description
                                         · Ownership of activity
                                         · Definition of solution(s)
                                         · Series of actions

                                  Includes:
                                         · Timing needs, for example required closure or
                                              analysis date
                                         · Status indicator
                                         · Further activities needed, for example a follow up
                                              audit.

                                  Activities required to be performed in order to complete a set
                                  of work.

                                  Identifies:
                                         · Activities to be performed
                                         · Ownership, for example to a specific domain like
                                              verification.
                                         · Dependencies to other activities and work products
                                         · Input and output work products
                                         · Required information

                                  Includes:
                                         · Estimation of efforts and duration

                                  Examples and References:
                                         · Work package can be a statement of work document,
                                              for example to outsource activities to an engineering
                                              service.

                                                                                                          141
ID     Name                        Characteristics
14-50  Stakeholder groups
                                    A group of people, relevant to a specific purpose or domain.
14-53  Role assignment
                                    Identifies:
14-54  Hardware bill of materials          · Persons and group of persons
                                           · Responsibilities of ownership
15-06  Project status                      · Representatives and roles

15-07  Reuse analysis evidence      Includes:
                                           · Information needs, for example reporting content and
© VDA Quality Management Center                 frequency.

                                    Examples and references:
                                           · Expert groups for specific domains, for example
                                                safety.
                                           · Executive board

                                    Assignment of person(s) to roles.

                                    Identifies:
                                           · Required competencies
                                           · Existing competencies

                                           · Experiences
                                           · Training related to role
                                    Includes:
                                           · Gap identification and guidance
                                           · Approver

                                    Description of subcomponents, material and assemblies
                                    included within a hardware product.

                                    Identifies:
                                           · Type of components
                                           · Number of hardware parts
                                           · Supplier name
                                           · Revision information

                                    Includes:
                                           · Structure and hierarchical information

                                    Evaluated result for the relative state of a project

                                    Identifies:
                                           · Progress and consistency to plans and schedule
                                           · Completed tasks
                                           · Relation to the intent of the project
                                           · Resources usage, for example hardware, material,
                                                human resources

                                    Includes:
                                           · Deviations and justification
                                           · Risks and opportunities to the planned progress and
                                                agreements
                                           · Issues and actions

                                    Evaluation of suitability for an existing component,
                                    requirement, design element, or process to be used in a new
                                    project.

                                    Identifies:
                                           · Constraints for reuse, for example known defects
                                                and vulnerabilities

                                                                                                            142
ID     Name                      Characteristics

15-09  Risk status                       · Related change of infrastructure and environment
15-12  Problem status                    · Functional fit
15-13  Assessment/audit result           · Compatibility
                                         · Dependencies
                                         · Maturity

                                  Includes:
                                         · Regulatory and standard differences
                                         · Characteristics of domain specific architecture

                                  Examples and References:
                                         · Reuse of an off-the-shelf component within a
                                              different product line.

                                  Status or change of an identified risk.

                                  Identifies:
                                         · Risk statement
                                         · Sources of the risk
                                         · Impact, for example in relation to severity and
                                              probability
                                         · Owner

                                  Includes:
                                         · Category
                                         · Threshold value(s)
                                         · Risk treatment activities and their progress

                                  Progress of problem resolution.

                                  Identifies
                                         · Containment and prevention activities
                                         · Dependencies status
                                         · References to status model

                                  Includes:
                                         · Problem categories and classification

                                  Documentation of results of an audit or assessment activity.

                                  Identifies:
                                         · Gaps, potentials, weaknesses or non-conformances
                                              that require corrective actions
                                         · Scope and purpose
                                         · Context to the evaluations
                                         · Results, for example rating by percentage or traffic
                                              lights
                                         · Dates the activity was performed
                                         · Requirements used

                                  Includes:
                                         · Methods used
                                         · References to evidence
                                         · Assumptions and limitations
                                         · Organizational unit
                                         · Sponsor information
                                         · Assessment team
                                         · Attendees

© VDA Quality Management Center  143
ID     Name                      Characteristics
15-16  Improvement opportunity
                                  Suggestion or idea of an improvement related to a weakness
15-51  Analysis results           or a new capability.

15-52  Verification results       Identifies:
                                         · Related problem and cause
15-54  Tailoring documentation           · Value expected to benefit of, for example business
                                              opportunities or efficiency increases
© VDA Quality Management Center          · Penalties of losses for not making the improvement

                                  Includes:
                                         · Owner
                                         · Decider and approve
                                         · Evaluation of the improvement

                                  Results of analysis of an object or task.
                                  Identifies:

                                         · Object under analysis
                                         · Analysis criteria
                                         · Selection criteria or prioritization scheme
                                         · Decision criteria
                                         · Quality criteria
                                  Includes:
                                         · Decisions and selections performed
                                         · Assumptions and constraints
                                         · Evaluation criteria, for example correctness, com-

                                              pleteness or consistency to a work product
                                  Examples and references:

                                         · Verifiability analysis results, for example when a test
                                              machine becomes defective

                                        · Results of a feasibility analysis

                                  Results of verification activities.

                                  Identifies:
                                         · Identification information
                                         · Log data
                                         · Passed and failed results
                                         · Not executed/blocked verification activities
                                         · Test execution details, for example tester name, role.
                                         · Timing information

                                  Includes:
                                         · Summary of verification results

                                        · References, for example to problem resolution ac-

                                              tions.

                                  Context specific use evaluation results and adaptations to a
                                  standard process.

                                  Identifies:
                                         · Applied criteria for tailoring
                                         · Evidence of adaptations made to the standard
                                              process, for example meeting organization changes.
                                         · Reference to standard process and version, for
                                              example adaptation of lifecycle

                                  Includes:
                                         · Traceability information
                                         · Methods, tools and techniques

                                                                                                          144
ID     Name                       Characteristics
15-55  Problem analysis evidence
                                          · Formalities for regulation compliance and
15-56  Configuration status                    conformities.
15-57
       Quantitative process        Examples and References:
15-58  analysis results                   · Project management tailoring for development in an
16-03                                          agile approach.
       Common cause of variation
       analysis results            Elements and documents proving a problem analysis is
                                   performed.
       Configuration management
       system                      Identifies:
                                          · Analyst and owner
                                          · Affected and involved parties
                                          · Context and root cause of the problem
                                          · Analysis results and summary
                                          · Potential impact, for example as severity or cost
                                               calculation

                                   Includes:
                                          · Date of the analysis
                                          · Potential solution(s)

                                   Summary of configuration management records and status.

                                   Identifies:
                                          · Version and change history information
                                          · Baseline identification
                                          · Status of configuration items (CI) integrity and
                                               consistency
                                          · Identified deviations, for example missing CI,
                                               performance metric deviations

                                   Quantitative analysis results of a process.

                                   Identifies:
                                          · Results to defined, measurable outputs, for example
                                               cycle time, defect density, process yield
                                          · Distribution results

                                   Includes:
                                          · Trend analysis
                                          · Statistical control evaluation
                                          · Quantitative control limits

                                   Examples and references:
                                          · Lean Six Sigma analysis with evaluation of process
                                               capability indices (Cpk)

                                   Results of variation analysis specific for common cause.

                                   Identifies:
                                          · References of common causes
                                          · Deviations of the quantitative performance of process
                                               instances
                                          · Distributions of the quantitative performance of
                                               process instances

                                   Includes:
                                          · Quantitative control limits

                                   System to manage configurations throughout a project or
                                   product life cycle, providing integrity, consistency and control.

© VDA Quality Management Center   145
ID     Name                      Characteristics

16-06  Process repository         Identifies:
                                         · Configuration items to be controlled, for example
16-50  Organizational structure               documents, hardware or tools
                                         · Configuration information, for example to a status
16-52  ML data management                     model
       system                            · Repository
                                         · Baselines
© VDA Quality Management Center          · Changes and change status

                                  Includes:
                                         · Reporting requirements
                                         · Workflow of recovery and other containment
                                              activities, for example security fire drills.

                                  Examples and References:
                                         · NASA defines it as technical management discipline
                                              that provides visibility and control over performance,
                                              functional, and physical characteristics of a product,
                                              preventing incorrect or unsafe configurations from
                                              being released.

                                  Controlled storage location for configuration related artefacts
                                  of a process.

                                  Identifies:
                                         · Artefacts, for example process descriptions
                                         · Assets of the process
                                         · Access control
                                         · Changes to artefacts
                                         · Version information
                                         · Meta data, for example name, attributes, reference
                                              links.

                                  Includes:
                                         · Storage and retrieval characteristics, for example in
                                              archiving processes
                                         · Status information

                                  Hierarchical overview and structure of a set of groups and
                                  persons interacting with each other for a specific activity.

                                  Identifies:
                                         · Hierarchical and functional reporting lines
                                         · Ownership and responsibilities
                                         · Organizational units

                                  Includes:
                                         · Interfaces
                                         · Locations
                                         · Communication details

                                  Data management system supporting machine learning
                                  engineering (MLE).

                                  Identifies:
                                         · Data management activities
                                         · Data collection workflow
                                         · Labeling, Annotations and description
                                         · Ingestion

                                                                                                          146
ID     Name                      Characteristics

17-00  Requirement                       · Exploration and profiling workflows
                                         · Procedure of structuring and cleansing
17-05  Requirements for work             · Related phases of engineering, for example ML
       products
                                              training
© VDA Quality Management Center
                                  Includes:
                                         · References to configuration management
                                         · Information of data sources

                                  Examples and References:
                                         · Supports the relevant sources of ML data

                                  Statement that identifies an operational, functional, or design
                                  characteristic, which is unambiguous, testable, measurable,
                                  and necessary for product or process acceptability.
                                  Identifies:

                                         · Expectation of functions and capabilities (e.g., non-
                                              functional requirements)

                                         · Owner and origin of the requirement
                                         · Identification information
                                         · Boundaries, for example target price range
                                  Includes:
                                         · Stakeholder viewpoint, for example black-box per-

                                              spective
                                         · Design constraints, for example predefined and nec-

                                              essary implementation details.
                                         · Tolerances
                                         · Domain specific details, for example of safety and

                                              privacy standards
                                  Examples and references:

                                         · ISO/IEC directive quote: "expression, in the content of
                                              a document, that conveys objectively verifiable criteria
                                              to be fulfilled and from which no deviation is permitted
                                              if conformance with the document is to be claimed"

                                         · ISO/IEC 42010:2007
                                         · Hardware level requirements for example mission

                                              profile, storage requirements of environment bound-
                                              ary definitions during environment test.

                                        · Operational expectations for example power con-

                                              sumption, crank behavior, heat dissipation bounda-
                                              ries.

                                        · Resource constraints, for example performance and

                                              memory space definition.

                                  Statement that identifies a textual, functional, or design
                                  characteristic, necessary for work products.
                                  Identifies:

                                         · Expectation to content and structure
                                         · Owner and origin of the requirement
                                         · Control and approval mechanism
                                         · Identification information
                                         · Access rights
                                         · Status model references, for example as mainte-

                                              nance and disposal requirements
                                  Includes:

                                                                                                          147
ID     Name                      Characteristics

17-54  Requirement attribute             · References to documentation templates
                                         · Table of content or other overview documentation
17-55  Resource needs                    · Design constraints, for example predefined and nec-

17-57  Special characteristics                essary implementation details.

18-06  Product release criteria         · Tolerances
                                        · Domain specific details, for example of safety and
© VDA Quality Management Center
                                              privacy standards

                                  Information supporting structuring of requirements for specific
                                  context or intent.

                                  Identifies:
                                         · Context and intent of requirement

                                  Includes:
                                         · Meta-attributes
                                         · Solution intent

                                  Identification of required resources for process performance.

                                  Identifies:
                                         · Human resources
                                         · Competencies
                                         · Skills and authorities
                                         · Material
                                         · Infrastructure and equipment
                                         · Tooling
                                         · Time
                                         · Budgets

                                  Includes:
                                         · Relation to work breakdown structure and planning
                                              information

                                  Product or process characteristics that impact safety, legal
                                  compliance, fit, function, performance, or further processing,
                                  and therefore require special treatment.

                                  Identifies:
                                         · Product characteristics
                                         · Production process parameters
                                         · Domain impact references, for example security.
                                         · References to regulations (compliance)
                                         · Conformity requirements

                                  Includes:
                                         · Processing and performance requirements

                                  Examples and References:
                                         · IATF 16949, VDA 6.x Guidelines, ISO 26262,
                                              ISO/SAE 21434
                                         · FMEA rating within FMEA can consider special
                                              characteristics.

                                  Conditions to be satisfied prior to authorization of a product for
                                  delivery.

                                  Identifies:
                                         · Release type and status
                                         · Elements of the release
                                         · Completeness conditions

                                                                                                          148
ID     Name                          Characteristics
18-07  Quality criteria
18-52                                        · Documentation needs
18-53  Escalation path
                                      Includes:
       Configuration item selection          · Adequacy considerations
       criteria                              · Coverage
                                             · Limits, for example the maximum of residing risk in a
                                                  product.

                                      Examples and References:
                                             · Acceptance conditions for an engineering service
                                                  product to a specific milestone.

                                      Specified requirements to determine whether a product,
                                      process, or service conforms to quality objectives.

                                      Identifies:
                                             · Measurement needs
                                             · Timings
                                             · Required elements
                                             · Needs for completeness
                                             · Accuracy
                                             · Performance needs

                                      Includes:
                                             · Thresholds
                                             · Tolerance level
                                             · Attributes
                                             · Compliance and conformance references

                                      Examples and References:
                                             · Conformance requirements specifying a specific set
                                                  of values to be within a defined range.

                                      A sequence of organizational levels or responsible roles to
                                      which an unresolved issue, deviation, or risk shall be
                                      communicated in order to decision-making.

                                      Identifies:
                                             · Trigger conditions
                                             · Stakeholders and roles
                                             · Escalation methods
                                             · Decision authority

                                      Includes:
                                             · Level specific conditions for an escalation.
                                             · Communication and documentation requirements

                                      Examples and References:
                                             · A task force group requested by a customer includes
                                                  an escalation path

                                      Rules or parameters to determine elements of a system to be
                                      included under configuration control.

                                      Identifies:
                                             · Stakeholder needs
                                             · Regulatory needs
                                             · Configuration item identification requirements

                                      Includes:
                                             · Type of work products
                                             · Classification characteristic

© VDA Quality Management Center      149
ID     Name                          Characteristics
18-57
18-58  Change analysis criteria      Examples and References:
       Process performance                 · Maintainability requirement of software evaluation
18-59  objectives                                work products.
18-70                                      · Traceability requirements of supplier goods.
       Review and approval criteria
       for work products             Definition of criteria to be included in the analysis of a change

       Business goals                Identifies:
                                           · Resource requirements
                                           · Timing needs, for example to a project schedule
                                           · Risks and opportunities

                                     Description of performance goals and targets to be achieved
                                     by a process.

                                     Identifies:
                                           · Evaluation criteria
                                           · Metrics, for example number of change requests
                                           · Timing definitions, for example duration until change
                                                 requests are to be analyzed
                                           · Events, for example demonstration milestone

                                     Includes:
                                           · Assumptions and constraints

                                     Examples and References:
                                           · Effort or cost targets
                                           · Budget limitations
                                           · Frequency of tasks
                                           · Limits of parallel work items for an employee

                                     Specification of review and approval criteria for work products.

                                     Identifies:
                                           · Review conditions
                                           · Timing needs, for example a specific milestone
                                           · Review methods, for example inspection or peer
                                                 review

                                     Includes:
                                           · Approval definition

                                     Examples and References:
                                           · Definition when and how to perform a walkthrough
                                                 meeting.

                                     Explanation of business goals.

                                     Identifies:
                                           · Requirements for the business needs
                                           · Associations to other goals
                                           · Reasons and rationales for the goals
                                           · Authorization level
                                           · Timeframe

                                     Includes:
                                           · Degree of the need
                                           · Effect on the business, for example in case of delay.
                                           · Assumptions and constraints

                                     Examples and References:

© VDA Quality Management Center                       150
ID     Name                      Characteristics
18-80  Process improvement
       opportunity                       · Enabler program of a new technical capability in
18-81                                         production.
19-01  Improvement evaluation
       results                           · Demonstrations of a prototype to customer may be
                                              used to evaluate and gain feedback to business
       Process performance                    goals.
       strategy
                                  Cause of an improvement need.

                                  Identifies:
                                         · Improvement objectives, for example a specific
                                              business goal
                                         · Organizational scope
                                         · Process scope
                                         · Qualitative evaluation
                                         · Quantitative evaluation

                                  Includes:
                                         · Activities
                                         · Stakeholders
                                         · Priorities

                                  Examples and References:
                                         · Best practice analysis
                                         · State-of-the-art observations
                                         · Market studies

                                  Evaluation result of the effects of realized changes initiated for
                                  improvement.

                                  Identifies:
                                         · Expected benefits
                                         · Conditions, for example evaluation cycle time
                                         · Constraints and assumptions

                                  Includes:
                                         · Tactical level impact
                                         · Strategical level impact
                                         · Operational level impact

                                  Examples and References:
                                         · Cycle time of a changed problem resolution process
                                              for optical hardware inspection.
                                         · ISO/IEC TR33014 Guide for process improvement

                                  Description of an approach to achieve performance objectives
                                  of a process.

                                  Identifies:
                                         · Proceedings
                                         · Methodology
                                         · Scope of the strategy

                                  Includes:
                                         · Monitoring requirements, for example of performance
                                         · Domain specific references
                                         · Socio-cultural differences

                                  Examples and References:
                                         · Performance specific to development sites
                                         · Configuration management approaches for software

© VDA Quality Management Center  151
ID     Name                      Characteristics
19-50  ML data quality approach
                                  Approach describing criteria and activities to satisfy ML data
                                  quality goals.

                                  Identifies:
                                         · Quality criteria for example relevant data sources.
                                         · Analysis activities of the data

                                  Includes:
                                         · Reliability and consistency of labeling
                                         · Completeness against ML data requirements

                                  Examples and References:
                                         · Quality criteria to avoid data bias

                                 Table B.2 -- Information Item Characteristics

© VDA Quality Management Center                                                 152
