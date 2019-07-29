.. _create_bootcamp:

-----------------------------
Create Workshop From Template
-----------------------------

The Nutanix Hands on Workshops platform provides multiple Templates allowing you to create event specific Workshops or Bootcamps quickly and easily. Creating the event specific instance from a Template allows you to customize messaging and track granular statistics for your event.

What Do We Need To Start
++++++++++++++++++++++++

To start you need to know which Workshop or Bootcamp you are running.

Here is the list of Template offerings with more planned in the future:

- **Nutanix Technology Bootcamp** - A customer facing introduction to Nutanix Core Product (HCI, and Prism Element).
- **Nutanix Essentials Bootcamp** - A customer facing introduction to Nutanix Essentials Products (Prism Central, Prism Pro, Files, Calm, and Flow).
- **Nutanix Era Bootcamp** - A customer facing bootcamp focusing on using Era with Postgres and MSSQL.

Add-On Labs:

- **Veeam** - Using Veeam with Nutanix.
- **Hycu** - Using Hycu with Nutanix.
- **Peer** - Using Peer with Nutanix Files.

- Here is the link to the Marketing presentations and printable workbooks - https://ntnx.how/PresentationDecks

Creating A Workshop from a Template
+++++++++++++++++++++++++++++++++++

#. In a browser, login to https://bootcamps.nutanix.handsonworkshops.com/profiles/login/ using OKTA.

   .. note::

   If you are not able to use OKTA, log in with your @nutanix.com email. If this is your first time logging in and OKTA does not work, create an account with your @nutanix.com email.

   .. figure:: images/create_bootcamp_01.png

#. Once you log in you will see all of the Bootcamps and Workshops for which you are already registered.

#. Click the dropdown by your username/email, and select **Manage Workshops**.

   .. figure:: images/create_bootcamp_02.png

#. You should now see all of the **Active Workshops** you have created.

#. To clone a Template, Click **Add A Workshop +**.

   .. figure:: images/create_bootcamp_03.png

#. Fill out the following fields:

   - **Choose a Template** - Select your desired Template
   - **Name** - This is what will be displayed as the title of the Workshop (e.g. *Portland - May 2009 Nutanix Essentials Bootcamp*)
   - **Description** - While optional, the description allows you to provide brief context about what will be covered during the Workshop/Bootcamp or other logistical details such as address and time.
   - **Notes** - Optional

   .. figure:: images/create_bootcamp_04.png

#. Click **Add Workshop**.

#. The instance will now be built. This will take up to 15 minutes.

   .. figure:: images/create_bootcamp_05.png

#. Once this has completed, you will have a URL specific to this instance that your attendees will use to register for the Workshop/Bootcamp.

   .. figure:: images/create_bootcamp_06.png

#. Copy the link (or click the **Clipboard Icon**) and open in a new browser tab.

#. This is what your Prospects / Customers / Partners will see when they use that registration link. *(They will be prompted to login or create an account)*

   .. figure:: images/create_bootcamp_07.png

#. You can provide the registration link to your attendees prior to the event, as they won't have access to the environment until you provide them with access credentials.

Managing a Workshop
+++++++++++++++++++

#. Click the dropdown by your username/email, and select **Manage Workshops**.

#. Click on a specific Workshop or Bootcamp **Name**.

#. Select the **Enrollment** tab to view all registered users.

   .. figure:: images/create_bootcamp_08.png

#. Select the **Stats** tab to track page views. *(Additional data collection planned for the future)*

   .. figure:: images/create_bootcamp_09.png

#. Click **Export stats as > CSV** to download a spreadsheet with individual page views per registered user.

#. If you want to remove access from users following an event, you can archive the Workshop under the **Details** tab.
