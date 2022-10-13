## Bart's Music Server

Provisions a host to play audio from Bluetooth, Airplay, and Spotify sources.

### Requirements
- Python 3 on the host you are running Muse on
- One of the following on the host(s) to provision:
  - Ubuntu 22.10 (Kinetic Kudu)
  - Ubuntu 22.04 (Jammy Jellyfish)
  - Debian 11 (Bullseye)
  - Raspberry Pi OS based on Debian 11 (Bullseye)
  - Any derivatives of the above

### Usage
```
usage: muse [-h] [--local-host] [--ssh-host [user@]host [[user@]host ...]] [--ssh SSH] [--no-bluetooth]

Provision audio streaming services on one or more hosts.

options:
  -h, --help            show this help message and exit
  --local-host          Provision the host you are currently running Muse on.
  --ssh-host [user@]host [[user@]host ...]
                        Provision the specified remote SSH host.
  --ssh SSH             Provide a custom way of invoking the OpenSSH client. Example: `ssh -o "StrictHostKeyChecking=no" -i ./id_rsa`. Defaults to `ssh -T`.
  --no-bluetooth        Do not provision Bluetooth on the host(s).

```