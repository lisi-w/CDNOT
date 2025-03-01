

layout: default

Welcome to ESGF Software and Services
-------------------------------------

The `Earth System Grid Federation <http://esgf.llnl.gov/>`_ (ESGF) is a collaboration that develops, deploys and maintains software infrastructure for the management, dissemination, and analysis of model output and observational data. Below are the different data access interfaces and software tools. You can install and configure all the tools or a subset depending on your needs. 

Search data
^^^^^^^^^^^


* LLNL Data site (CoG Web UI): https://esgf-node.llnl.gov/projects/esgf-llnl/
* `ESGF User Guide and FAQ <https://esgf.github.io/esgf-user-support>`_

  * Includes information on operation of the CoG frontend, wget script and Globus downloads

* `Search API Documentation <https://esgf.github.io/esg-search>`_

  * For direct access to search on ESGF using http-based tools.

* Getting help:

  * https://esgf.github.io/esgf-user-support/faq.html#how-to-contact-us

ESGF Software Stack: for the Node Administrator
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

*ESGF Data and Index/Identity Node*
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


* **Description:**

  * The ESGF Data Node software stack enables sites hosting earth system data to make it available to the community over several transfer protocols including http(s).  Index nodes enable search for hosted data via data publishing to the index, and these nodes include a search API and web frontend.  Identity nodes manage user accounts.  All these services together consitute a "Full" ESGF installation.  These nodes are installed using the popular Ansible automation platform using our esgf-ansible collection of playbooks.

* **Use case:**

  * I want to install a data and/or index/IdP node software stack using the current architecture
  * I want to upgrade my existing node software stack to the latest supported service versions

* **New and returning installations:**

  * Regardless of whether you have installed and administered an ESGF node previously, please read the following document on ESGF policies, as this should influence what type of installation you should do:

    * http://esgf.llnl.gov/media/pdf/ESGF-Policies-and-Guidelines-V1.0.pdf
    * https://esgf.llnl.gov/esgf-media/pdf/ESGF-Tier1and2-NodeSiteRequirements-V5.pdf

      * describes suggested requirements under “Tier 2 sites” section.

* Requirements, Setup and Usage documentation
  .. code-block::

       * <https://esgf.github.io/esgf-ansible/intro/intro.html>

* **Basic Prerequisite:**

  * The ESGF software stack requires Linux RedHat Enterprise or Centos 7 distributions and administrators have full sudo privileges to root access
  * The services are meant to run on webserver-grade hardware.  For data nodes, storage holding your data to share must be mounted on the node.
  * See the main documentation site for more information

* **Source repository on github**

  * `ESGF Ansible playbooks source repository <https://github.com/ESGF/esgf-ansible>`_

* **Issues: (bug reporting)**

  * https://github.com/ESGF/esgf-ansible/issues

* **Installation email list:**

  * esgf_iwt@llnl.gov

*ESGF Docker (beta)*
~~~~~~~~~~~~~~~~~~~~~~~~


* **Description**

  * ESGF Docker is the deployment mechanism for the next generation ESGF architecture, and can be tested concurrently with the production platform.

* **Use case**

  * I want to test install the next-generation architecture 

* **Main page: includes installation instructions**
  .. code-block::

       * <https://github.com/ESGF/esgf-docker/tree/future-architecture/>


  * **Issues:**

    * https://github.com/ESGF/esgf-docker/issues

*User Interface (CoG) Frontend*
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


* See the CoG README for instructions to access the Admin and Developers Guide:

  * https://github.com/earthsystemcog/COG

ESGF data publisher
^^^^^^^^^^^^^^^^^^^

*ESG publisher (esg-publisher)*
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


* **Description:**

  * The ESG Publisher (esgcet python package) enables data publishers to push references of their data on their site’s data node to an ESGF Index for use in search and retrieval

* **Use Cases:**

  * I want to publish a new dataset to ESGF
  * I want to update an existing dataset that I published on ESGF
  * I want to retract/delete a dataset that I published from ESGF 

* **Main Page: (user documentation)**

  * https://esg-publisher.readthedocs.io/en/refactor/

* **Recently Updated**

  * The new publisher for ESGF data is available for install via conda (stable version) or by cloning our `git repository <https://github.com/lisi-w/esg-publisher/tree/refactor>`_ (latest version).
  * The newly updated (v5) Publisher can be run external to the Data Node, but the data to be published must be locally accessible on your linux file system.
  * For other details about the new publisher and help getting started, see our docs.

* **Issues:**

  * https://github.com/ESGF/esg-publisher/issues

* **Publication working team mailing list:**

  * esgf-pwt@llnl.gov

**For Data Preparation**\ , our collaborators at IPSL provide the `Pre-publication Tools <https://esgf.github.io/esgf-prepare>`_ for a number of ongoing ESGF data projects.  


*ESGF Compute end-user API (esgf-compute-api)*
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


* **Description:** The esgf-compute-api is python package design to interact with the ESGF Compute Node’s Web Processing Service (ECN WPS). It provides access to primitive operations (subset, min, max, etc) that will be execute using remote resources.
* **Use Cases**

  * I want to retrieve a subset of the data.
  * I want to execute compute operations on data using remote resources.

* **Main Page:**

  * https://github.com/ESGF/esgf-compute-api 

* **Installation:** 

  * https://github.com/ESGF/esgf-compute-api#installation

* **Documentation:** 

  * Example Jupyter Notebooks: `Jupyter Notebooks <https://github.com/ESGF/esgf-compute-api/tree/devel/examples>`_

* **Support:**

  * Github Issues: https://github.com/ESGF/esgf-compute-api/issues

*ESGF Compute Node Web Processing Service (ECN WPS)*
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


* **Description:** The ECN WPS is a scalable compute service. The service is exposed to users through a WPS interface. The compute backend is Xarray based and scales on a Kubernetes cluster.
* **Use Cases:**

  * I want to host a compute service near data.

* **Main Page:** 

  * https://github.com/ESGF/esgf-compute-wps 

* **Installation:** 

  * https://github.com/esgf-compute/charts#installing-the-chart 

* **Documentation:** 

  * https://github.com/ESGF/esgf-compute-wps/blob/devel/README.md 

* **Support:**

  * Github Issues: https://github.com/ESGF/esgf-compute-wps/issues

Misc software and documentation
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

*CMIP6 administrators and publishers*
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

PCMDI has produced the Data Node Managers guide for CMIP6 data specifically here: https://pcmdi.llnl.gov/CMIP6/Guide/dataManagers.html 

*ESGF bulk data download tools*
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


* https://github.com/ESGF/sproket  Sproket Download tool for command line data search and download, where you can specify search criteria and download data files in a single command.
* http://prodiguer.github.io/synda/index.html From IPSL, Synda is an automated download service to manage massive replica copies of ESGF datasets. (suited for server administrators to operate) 
