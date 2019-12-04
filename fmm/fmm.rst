.. _fmm:

-----------------------------
Field Marketing Manager Info
-----------------------------

The Nutanix Technology Bootcamp is a marketing event to be run in the field by Nutanix sales teams and partners. The purpose of the bootcamp is to give attendees a close-up view of some of the powerful web-scale capabilities of the Nutanix Enterprise Cloud Platform, and showcase how simple Nutanix is to configure and manage. The intended audience for these bootcamps are technical IT operators at prospect organizations who have had prior exposure to Nutanix but have not done a POC yet.

The key messaging objectives:
  - Nutanix is simple. Everything is easy to do with Nutanix, from buying and deploying to managing and expanding resources.
  - Web-scale HCI is a fundamentally different approach to IT than traditional three-tier architectures, and it is better.
  - Nutanix AHV is enterprise-class virtualization built into the platform that is available and ready to use out of the box.

Program Format
+++++++++++++++

The boot camp is run as a half day event in the morning with a possible second 2-3hr session after lunch devoted to other optional topics such as Calm or Flow (to be run at SE’s discretion).

The overall flow includes a brief presentation that provides a high-level overview of Nutanix and covers features in depth. The presentation is interspersed with demos and hands-on exercises on a live cluster to give participants a feel for the Nutanix environment. The slides and demos are arranged to be aligned chronologically with a customer’s Nutanix experience. All boot camps are intended to be run on **AHV** clusters and should include demos of virtualization capabilities as well as core storage functionality.

As there is far more content than can typically be covered in the half-day format, the SE is encouraged to customize the content by including/excluding content or exercises based on their audience. Time spent on the introduction sections can be varied based on the audiences’ prior exposure to Nutanix.

The goal of these bootcamps is to move early opportunity stages forward. If customers leave a boot camp wanting to know more about the technology, it will be considered a success. Follow up meetings can include SE led deep dives, or POC activities.

Bootcamp Readiness
+++++++++++++++++++++

**Marketing Cluster Reservation**
SEs request a reservation of a marketing cluster for two consecutive days with an FMM, one for the day before to get ready for the event, and another for the day of the event.

The boot camp clusters are using the same reservation system as the HPOC and should be delivered cleanly foundationed to AHV with 4 nodes in the cluster. The CVMs should be reserved with 32GB of memory.

The SE leading the boot camp is responsible for verifying that the foundation succeeded and the cluster is ready for the event. This should be done the DAY BEFORE the event so that should there be any complications there is time for the corporate SE or TME teams to resolve.

A cluster reserved for use during this boot camp should be reserved as follows by the FMM:

- Specify "From" and "To" dates: 2 days total (day before and day of bootcamp).
- Select Bootcamp (enter any other relevant information in the text field).
- Share reservation: enter the SE's email address so that they get access to the reservation too and is able to make any changes as needed. (NOTE: Ensure you click the + character after entering the SE email in the form field)
- Click on Next to get to the next screen.
- Select latest available AHV version.
- Select latest available AOS version.
- CVM memory: 32GB.
- Number of nodes: 4.
- Leave custom password field blank (or enter a custom password if desired.

.. note::
  Warning: if entering a custom passwords note that all passwords get stored in clear text in a database so don't use any real passwords).

- Click on "Submit Reservation"

Once the cluster is reserved, SE and FMM should be getting a confirmation email, if the FMM shared the reservation. That email contains important reservation and access details for the cluster.

Need Help?
++++++++++++

If you have any questions or issues on the day of the bootcamp, please reach out to the corporate SE team at hostedpoc@nutanix.com or #rx-and-hpoc on slack. You can also ask in the #technology-bootcamps channel on slack.
