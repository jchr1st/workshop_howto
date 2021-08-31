.. _ad_scheme:

------------
AD User Scheme
------------

Each cluster has a dedicated domain controller VM, called AUTOAD, responsible for providing AD services for the NTNXLAB.local domain. The domain is populated with the following Users and Groups:


.. list-table::
   :widths: 15 10 20
   :header-rows: 1

   * - Group
     - Username(s)
     - Password
   * - Administrators
     - Administrator
     - nutanix/4u
   * - SSP Admins
     - adminuser01 - adminuser25
     - nutanix/4u
   * - SSP Developers
     - devuser01 - devuser25
     - nutanix/4u
   * - SSP Consumers
     - consumer01 - consumer-25
     - nutanix/4u
   * - SSP Operators
     - operator01 - operator-25
     - nutanix/4u
   * - SSP Custom
     - custom01 - custom25
     - nutanix/4u
   * - Bootcamp Users
     - user01 - user25
     - nutanix/4u


