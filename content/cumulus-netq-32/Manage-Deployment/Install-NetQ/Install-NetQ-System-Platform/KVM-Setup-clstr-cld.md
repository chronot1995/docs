---
title: Set Up Your KVM Virtual Machine for a Cloud Server Cluster
author: Cumulus Networks
weight: 228
toc: 5
bookhidden: true
---
First configure the VM on the master node, and then configure the VM on each worker node.

Follow these steps to setup and configure your VM on a cluster of servers in a cloud deployment:

1. Verify that your master node meets the VM requirements.

    {{<netq-install/vm-reqs deployment="cloud" hypervisor="kvm">}}

2. Confirm that the needed ports are open for communications.

    {{<netq-install/port-reqs server="cluster">}}

3. Download the NetQ Platform image.

    {{<netq-install/kvm-platform-image deployment="cloud" version="3.2.1">}}

4. Setup and configure your VM.

    {{<netq-install/vm-setup hypervisor="kvm" deployment="cloud" version="3.2.1">}}

5. Log in to the VM and change the password.

    {{<netq-install/change-pswd>}}

6. Verify the master node is ready for installation. Fix any errors indicated before installing the NetQ software.

    {{<netq-install/verify-cmd deployment="cloud">}}

7. Change the hostname for the VM from the default value.

    {{<netq-install/set-hostname>}}

8. Run the Bootstrap CLI. Be sure to replace the *eth0* interface used in this example with the interface on the server used to listen for NetQ Agents.

    {{<netq-install/bootstrap version="3.2.1" server="single" platform="vm" deployment="cloud">}}

9. Verify that your first worker node meets the VM requirements, as described in Step 1.

10. Confirm that the needed ports are open for communications, as described in Step 2.

11. Open your hypervisor and setup the VM in the same manner as for the master node.

    {{<notice note>}}
Make a note of the private IP address you assign to the worker node. It is needed for later installation steps.
    {{</notice>}}

12. Log in to the VM and change the password.

    {{<netq-install/change-pswd>}}

13. Verify the worker node is ready for installation. Fix any errors indicated before installing the NetQ software.

    {{<netq-install/verify-cmd deployment="cloud">}}

14. Run the Bootstrap CLI on the worker node.

    {{<netq-install/bootstrap version="3.2.1" server="cluster" platform="vm" deployment="cloud">}}

15. Repeat Steps 9 through 14 for each additional worker node you want in your cluster.

## Considerations for Container Environments

{{<netq-install/container version="3.2.1">}}

## Install and Activate the NetQ Software

The final step is to install and activate the Cumulus NetQ software. You can do this using the Admin UI or the CLI.

Click the installation and activation method you want to use to complete installation:

- {{<link title="Install NetQ Using the Admin UI" text="Use the Admin UI">}} (recommended)
- {{<link title="Install NetQ Using the CLI" text="Use the CLI">}}
