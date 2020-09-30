What is Bonita?
Welcome to this Bonita starter tutorial. This page will give you a quick overview of what you can do with Bonita and introduce you to the architecture of Bonita.

If you can't wait to start building your first app with Bonita, you can skip this page and go straight to downloading and installing Bonita Studio.

What can I do with Bonita?
Bonita is a Digital Process Automation (DPA) platform that allows you to build process-based applications. Processes can be partially automated (if users are involved) or fully automated.

The DPA, available with all editions of Bonita, applies to a wide range of use cases: applications can include, among others, the management of loan applications, the registration process of students at a university or even analytical processes in drug discovery! You will find the different sectors in which Bonita is used as well as the use cases on our dedicated page on the website .

As of Bonita 7.10, you can also process Adaptive Case Management with Bonita. ACM (Adaptive Case Management) is similar to DPA in that it allows cases to be handled with some automation. However, it is also based on strong principles that differentiate it from DPA:

Giving power to the actors: the actors responsible for the case have a certain autonomy to end the case: all the paths of the process are not predetermined. Some tasks are optional, others are discretionary. The specific knowledge of the actors allows them to choose the appropriate next action for a case.
Expect the unexpected: a case can be stopped, resumed and can even change its state at any time without having predefined a path. It may be necessary to create new tasks on the fly to reflect the specificity of a case while benefiting from traceability.
Adapt to the context: the type and state of the case define the availability of tasks according to a set of business rules. These rules must be modifiable on the fly.
Focus on data: The execution of the case is not focused on a strict process, but on the case data to create and update.
ACM is available in Teamwork, Efficiency, Performance and Enterprise editions of Bonita.

To learn how to use ACM features in Bonita, see the documentation .

How to create a Bonita application?
Thanks to the Bonita low-code platform, you won't have to write a lot of code to build an app. The creation of Bonita applications is largely based on models: a process model (using the BPMN standard), a data model for the management of business data, a WYSIWYG tool for the design of the user interface ...

To create an application in Bonita Studio (Bonita's development environment), you must follow the following steps:

graphically design one or more processes using BPMN notation
define the data model using Bonita's business data management functionality (you can of course use your own database if needed)
create web user interfaces using Bonita's user interface editor (or your favorite web framework)
define the users involved in the process
configure connectors to integrate Bonita into the information system (for example, send an e-mail, call a web service, etc.)
We will cover these steps in this getting started tutorial to familiarize you with the concepts of a Bonita application.

Presentation of the architecture of the Bonita solution
Bonita Studio
Architecture of Studio Bonita

Bonita Studio provides you with everything you need to develop and build a Bonita application. Bonita Studio is a desktop application built on Eclipse.

It provides:

features to model BPMN (Business Process Modeling Notation) processes
functionalities to model the BDM (Business Data Model)
features to model user interfaces (UI Designer)
functionalities to model applications
an integrated Bonita server (described below), exclusively dedicated to the application tests carried out locally by the application developer.
Bonita Studio is not intended for any use other than development. Therefore, the Bonita stack built into Bonita Studio cannot be used for production purposes.

Stack, runtime and Bonita server
Bonita stack architecture

The “Bonita stack” refers to all the components you need to deploy and deliver applications to end users in production. It includes Bonita runtime and two database schemas (one for the Bonita engine and one for business data).

Bonita runtime includes a unique Bonita server in the Bonita Community Edition. In the Enterprise Edition, Bonita runtime can include multiple Bonita servers to create a cluster for high performance and high availability.

The Bonita server has two components: the Bonita engine which manages the execution of the processes and the web portal which provides the web interfaces for end users and administrators.

The Bonita server is a stand-alone Java application executed on a Java application server installed on a host (a machine, a virtual machine, a cloud instance, a container such as Docker ...).

Now that you have an overall image of Bonita, you are ready to take the next step: download and install Bonita Studio .
