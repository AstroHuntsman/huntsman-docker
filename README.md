# huntsman-docker
Docker containers for Huntsman computers.

The idea is that we automate (as much as possible) the management of software accross all Huntsman devices using docker containers. Each docker image should inherit from huntsman-base:latest, which contains the common software between devices.

A proposed workflow:

- A device is powered-on and executes a login script (i.e. bashrc).
- The device learns which instructions it should carry out from the control computer by referencing its own IP.
- The appropriate docker container is Run, accessing shared files such as local configs via a shared file system (e.g. SSHFS).
- Logs are shared using a shared file system (e.g. SSHFS).


