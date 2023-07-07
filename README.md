# Rally Snap

This repository contains the source code of the snap for the OpenStack benchmark
as a service, Rally.

## Installing this snap

The rally snap can be installed directly from the snap store:

    sudo snap install --edge rally

Initialize your local rally db

    rally db create

Register your existing OpenStack deployment using the credentials in the environment

    rally deployment create --fromenv --name my-xena-cloud

Install desired Tempest verifier version

    rally verify create-verifier --type tempest --platform openstack --version xena-last --name tempest-xena

Install Tempest plugins

    rally verify add-verifier-ext --id tempest-xena --source https://opendev.org/openstack/octavia-tempest-plugin --version xena-last

Run verification

    rally verify start --id tempest-xena --deployment-id my-xena-cloud --pattern set=smoke --concurrency 4

## Support

Please report any bugs related to this snap on
[Launchpad](https://bugs.launchpad.net/snap-rally/+filebug).

Alternatively you can find the OpenStack Snap team in `#openstack-snaps`
on Freenode IRC.
