.. _stage_environment:

------------------------
Staging the Environment
------------------------

*The estimated time to complete staging a cluster is 60 minutes.*

This exercise will show you how to stage your Hosted POC or Marketing cluster so you can run a Workshop or Bootcamp.

What Do We Need To Start
++++++++++++++++++++++++

Before we can stage an environment, we will need the reservation information provided by the RX tool. This will give us the **Password** and **Cluster Information** for our HPOC or MKT cluster.

Refer to your automation@nutanix.com **Reservation Confirmation** e-mail, similar to the example below.

.. figure:: images/staging_01.png

Bootcamp To Staging Scripts Pairing
+++++++++++++++++++++++++++++++++++

With the latest release of Bootcamps, we have introduced *Bootcamp Specific Staging Options*. Please see the table below to make the correct choice.

.. list-table::
   :widths: 40 60
   :header-rows: 1

   * - Bootcamp
     - Staging Option
   * - **AOS and AHV Bootcamp**
     - Basic / API Bootcamp (AOS 5.11.x/AHV PC 5.11.2.1) = Current
   * - **Enterprise Private Cloud Bootcamp**
     - Private Cloud Bootcamp (AOS 5.11.x/AHV PC 5.11.2.1) = Current
   * - **Databases with Era Bootcamp**
     - Databases with Era Bootcamp (AOS 5.11.x/AHV PC 5.11.2.1) = Current
   * - **Files Bootcamp**
     - Files Bootcamp (AOS 5.11.x/AHV PC 5.11.2.1) = Current
   * - **Calm Bootcamp**
     - Calm Workshop (AOS 5.11.x/AHV PC 5.11.2.1) = Current
   * - **Citrix on AHV Bootcamp**
     - Citrix Bootcamp (AOS 5.11.x/AHV PC 5.11.2.1) = Current
   * - **API Bootcamp**
     - Basic / API Bootcamp (AOS 5.11.x/AHV PC 5.11.2.1) = Current
   * - **Core/Essentials/Enterprise Bootcamps (Archiving End of April)**
     - Previous Bootcamp Staging (AOS 5.11.x/AHV PC 5.11.2) = Stable

Running the Staging Scripts
+++++++++++++++++++++++++++

#. Use Terminal or PuTTY to SSH into a Controller VM (CVM).

   .. code-block:: bash

    ssh nutanix@<CVM-IP>

#. Now we need to call the staging script. We will use the following command to download and call the **bootstrap.sh** file.

   .. code-block:: bash

    curl --remote-name --location https://raw.githubusercontent.com/nutanixworkshops/stageworkshop/master/bootstrap.sh && sh ${_##*/}

#. Next you will be prompted to enter the Clusters **Admin User**, **Admin Password**, and **Admin Email**. The **Admin User** and **Admin Password** map to the **Prism UI Credentials** in the email you received, and the **Admin Email** is your email address.

   .. code-block:: bash

          Note: Hit [Return] to use the default answer inside brackets.

        Optional: What is this cluster's admin username? [admin] admin

          Note: Password will not be displayed.
        REQUIRED: What is this PHX-POC055 cluster's admin password?
        CONFIRM:              PHX-POC055 cluster's admin password?

          Note: @nutanix.com will be added if domain omitted.
        REQUIRED: Email address for cluster admin? nathan.cox@nutanix.com

#. Now we need to select the Option we want to Stage. You will see options for **Bootcamp**, **Citrix** (which is under development), and **Tech Summit**.

   .. note::

    You need to read this each time, as options may change.

   .. code-block:: bash

    1) Bootcamp Staging (AOS 5.11+/AHV PC 5.11.2.1) = Current
    2) SNC (1-Node) Bootcamp Staging (AOS 5.11+/AHV PC 5.11.2.1) = Current
    3) Previous Bootcamp Staging (AOS 5.11.x/AHV PC 5.11.2) = Stable
    4) Previous SNC (1-Node) Bootcamp Staging (AOS 5.11.x/AHV PC 5.11.2) = Stable
    5) Basic / API Bootcamp (AOS 5.11.x/AHV PC 5.11.2.1) = Current
    6) Private Cloud Bootcamp (AOS 5.11.x/AHV PC 5.11.2.1) = Current
    7) Databases with Era Bootcamp (AOS 5.11.x/AHV PC 5.11.2.1) = Current
    8) Files Bootcamp (AOS 5.11.x/AHV PC 5.11.2.1) = Current
    9) Calm Workshop (AOS 5.11.x/AHV PC 5.11.2.1) = Current
    10) Citrix Bootcamp (AOS 5.11.x/AHV PC 5.11.2.1) = Current
    11) Change Cluster Input File
    12) Validate Staged Clusters
    13) Quit
    Select an option: 5

    Are you sure you want to stage Basic / API Bootcamp (AOS 5.11.x/AHV PC 5.11.2.1) = Current to the cluster(s) provided?
    Your only 'undo' option is running Foundation on your cluster(s) again.
    ( Y/N)y

#. To monitor the progress of the staging on **Prism Element**, tail the *xyz_bootcamp.log* file.

   .. code-block:: bash

    tail -f *bootcamp.log

#. You will see it update and install several things:

- sshpass & jq
- AutoAD
- Role Mapping
- Configure VM Networks & Storage Container
- Download and Install Prism Central (this takes roughly 17 minutes)
- Register Prism Element to Prism Central


#. When you see the following at the end of the *xyz_bootcamp.log* file, you can Ctrl+C to kill the tail.

   .. code-block:: bash

    |finish|./ts2020.sh ran for 5872 seconds._____________________


#. Now ssh to the Prism Central VM (10.XX.YY.39) so you can tail the *xyz_bootcamp.log* file there and follow along.

   .. code-block:: bash

    ssh nutanix@<PC IP>

#. The password with be nutanix/4u since this is a default install of Prism Central.

#. Now tail the *xyz_bootcamp.log* file on the Prism Central VM.

   .. code-block:: bash

    tail -f *bootcamp.log

#. You will see it update and enable several things:

- sshpass & jq
- SSP Authentication
- Enable Calm
- Enable Karbon
- LCM Inventory and Upgrades
- Enable Flow
- Create Project
- Upload Images needed for Bootcamps or Workshops (These will continue to run in the background)
    - WinToolsVM.qcow2
    - Linux_ToolsVM.qcow2
    - CentOS7.qcow2
    - Windows2016.qcow2
    - Windows2016.iso
    - Win10v1903.qcow2
    - Nutanix-VirtIO-1.1.5.iso


#. When you see the following at the end of the *xyz_bootcamp.log* file, you can Ctrl+C to kill the tail.

   .. code-block:: bash

    |finish|/home/nutanix/bootcamp.sh ran for 2556 seconds._____________________

#. You can Ctrl+C to kill the tail.

#. Now you can move to your browser and verify Prism Element and Prism Central. Remember, Images will continue to upload in the background.
