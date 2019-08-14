This page contains all information and reference to information related to the technical aspects of the VUTURA project.

The VUTURA demonstration in Delft had 5 drones in it. Three of these were flying using the normal AirMap app. The other two, a Parrot Disco and an Altura X8 AED-drone (with RPi) had onboard software communicating directly with AirMap/Unifly.

### 4G subscriptions
https://github.com/tudelft/mavlab/wiki/4G-subscriptions

### TUDelft VM in faculty managed server
Go to [https://tudelft.topdesk.net/tas/public/ssp/](https://tudelft.topdesk.net/tas/public/ssp/) and search for `Faculty managed server`. This is basically what we have. Click `(ICT) Request Faculty Managed Servers` for details on how to get into the system. NetID's with access to the [mavlab-drones.tudelft.nl](mavlab-drones.tudelft.nl) VM are:

```
bjmmslinger
dcvanwijngaard
```

To login into the VM, use the following instructions:
```
ssh -l <netid> linux-bastion-ex.tudelft.nl
ssh mavlab-drones.tudelft.nl
sudo su bjmmslinger
```

## Onboard software architecture

## Compiling

To run this software onboard the Parrot Disco or on the RPi, a couple of software packages need to be [cross-compiled](https://github.com/tudelft/mavlab/wiki/Cross-Compiling).

## Configuration

