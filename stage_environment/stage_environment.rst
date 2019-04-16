.. _stage_environment:

------------------------
Staging the Environment
------------------------

*The estimated time to complete this is 60 minutes.*

Overview
++++++++

This Exercise will show you how to stage your HPOC or Marketing cluster so you can run a Workshop or Bootcamp.

What Do We Need To Start
++++++++++++++++++++++++

Before we can stage an environment, we will need the Reservation (RX) information. This will give us the **Password** and **Cluster Information** for our HPOC or MKT cluster.

You should have received an email similar to the example below.

.. figure:: images/staging_01.png

Running the Staging Scripts
+++++++++++++++++++++++++++

Now that we have our HPOC / MKT cluster information, lets stage the Environment.

#. Use Terminal or Putty to ssh into a Controller VM (CVM).

.. code-block:: bash

  ssh nutanix@10.42.55.29

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

  1) Bootcamp (AOS 5.10+/AHV PC 5.10+) = Current (AutoDC2)
  2) Citrix Desktop on AHV Workshop (AOS 5.10+/AHV PC 5.10+) = Development
  3) Tech Summit 2019 (AOS 5.10+/AHV PC 5.10+) = Development
  4) Change Cluster Input File
  5) Validate Staged Clusters
  6) Quit
  Select an option: 1

  Are you sure you want to stage Bootcamp (AOS 5.10+/AHV PC 5.10+) = Current (AutoDC2) to the cluster(s) provided?
  Your only 'undo' option is running Foundation on your cluster(s) again.
  (Y/N)y

#. To monitor the progress of the staging on **Prism Element**, tail the *bootcamp.log* file.

.. code-block:: bash

  tail -f bootcamp.log

#. You will see it update and install several things

- sshpass & jq
- AutoDC2 (LDAP/Active Directory)
- Role Mapping
- Configure VM Networks & Storage Container
- Download and Install Prism Central (this takes roughly 17 minutes)
- Register Prism Element to Prism Central
- Download and Install Files

#. When you see the following at the end of the *bootcamp.log* file, you can ctrl-c to kill the tail.

.. code-block:: bash

  |main|Remote asynchroneous PC Image import script... EMAIL=nathan.cox@nutanix.com PC_HOST=10.42.55.39 PE_HOST=10.42.55.37 PE_PASSWORD=techX2019! PC_LAUNCH=bootcamp.sh PC_VERSION=5.10.2 nohup bash /home/nutanix/bootcamp.sh IMAGES

#. Now ssh to the Prism Central VM so you can tail the *bootcamp.log* file there and follow along.

.. code-block:: bash

  ssh nutanix@10.42.55.39

#. The password with be nutanix/4u since this is a default install of Prism Central.

#. Now tail the *bootcamp.log* file on the Prism Central VM.

.. code-block:: bash

  tail -f bootcamp.logs

#. You will see it update and enable several things

- sshpass & jq
- SSP Authentication
- Enable Calm
- Enable Karbon
- LCM Inventory and Upgrades
- Enable Flow
- Create Project
- Upload Images needed for Bootcamps or Workshops (These will continue to run in the background)

#. When you see the following at the end of the *bootcamp.log* file, you can ctrl-c to kill the tail.

.. code-block:: bash

  |finish|/home/nutanix/bootcamp.sh ran for 2556 seconds._____________________

#. You can ctrl-c to kill the tail.

#. Now you can move to your browser and verify Prism Element and Prism Central. Remember, Images will continue to upload in the background.
