Upgrading workstations from Tails 3 to Tails 4
----------------------------------------------

.. note::

   This guide will be removed in a future release of this documentation, and
   is no longer actively tested as part of SecureDrop QA. If you still use older
   Tails USB drives and encounter issues during the upgrade, please get in
   touch.

As a precaution, we recommend backing up your workstations before the upgrade
to Tails 4. See our :doc:`Workstation Backup Guide <../backup_workstations>` for
more information. We also recommend that you keep a USB drive running Tails 3.16
on hand in case you need to revert.

Once you have created the backups, create a *Tails 4 Primary USB* which you will
use to upgrade your workstations. Follow the
`instructions on the Tails website <https://tails.boum.org/install/index.en.html>`__
to create a fresh Tails drive on a computer running Windows, Mac, or Linux.

Boot the *Tails 4 Primary USB* on the air-gapped computer you use as the *Secure
Viewing Station*, and follow the instructions for `manually upgrading from
another Tails <https://tails.boum.org/upgrade/clone/index.en.html>`__
to upgrade each workstation USB in turn. This procedure preserves the persistent
storage volume of each USB drive you upgrade to Tails 4.

Once the upgrade is completed, shut down the *Tails 4 Primary USB* and boot into
each workstation USB to verify that the upgrades were successful. On the *Secure Viewing Station* USB, the upgrade process is now complete, and no additional configuration is required.

On the *Admin* and *Journalist Workstation* USBs, set an administrator password on the Tails welcome screen, and update the SecureDrop environment using the
following commands: ::

  cd ~/Persistent/securedrop
 ./securedrop-admin update
 ./securedrop-admin setup
 ./securedrop-admin tailsconfig

During the ``./securedrop-admin setup`` step, Tails will prompt you if you want
to install a set of packages every time you start Tails. These packages are only
required for the setup process, so you can safely click **Install Only Once**.

.. important::

   Until you run these commands, the SecureDrop shortcuts on the Tails desktop
   will not work, and the graphical updater will no longer report available
   updates for the SecureDrop code on your workstation.

If you experience difficulties with this upgrade, please do not hesitate to
contact us using any of the methods below. If the upgrade failed and you need
to restore from a backup, see our :ref:`guide for restoring workstations <restore_workstations>`.
Make sure you restore to a Tails drive using Tails 3.16 before attempting
another upgrade to Tails 4.


Getting Support
---------------

Should you require further support with your SecureDrop installation, we are
happy to help!

.. include:: ./includes/getting-support.txt
