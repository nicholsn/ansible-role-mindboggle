ansible-role-mindboggle
=======================

Mindboggle virtual machine setup script.

This program installs Mindboggle and dependencies, such as
FreeSurfer and ANTs, in a VirtualBox virtual machine (vm)
using Vagrant software, which can package the vm.
You must have Vagrant (http://www.vagrantup.com) and
VirtualBox (http://www.virtualbox.org) installed,
as well as a good internet connection.

The Mindboggle software automates shape analysis of anatomical labels
and features extracted from human brain MR image data.
See http://mindboggle.info for up-to-date documentation.

Requirements
------------

There is an option to use a local installation of FreeSurfer and ANTS

Role Variables
--------------

- freesurfer_dir
- ants_dir

Dependencies
------------

- nicholsn.miniconda

Example Playbook
-------------------------

Supply paths to FreeSurfer and ANTs

    - hosts: servers
      roles:
         - { role: nicholsn.miniconda, miniconda_home: /miniconda }
         - {role: nicholsn.mindboggle, 
            freesurfer_dir: /usr/local/freesurfer,
            ants_dir: /usr/local/ants}

Install FreeSurfer and ANTs

    - hosts: servers
      roles:
         - { role: nicholsn.miniconda, miniconda_home: /miniconda }
         - {role: nicholsn.mindboggle, 
            build_freesurfer: True,
            build_ants: True}

License
-------

Apache 2.0

Author Information
------------------

Nolan Nichols <nolan.nichols@gmail.com>