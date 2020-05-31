# devolo-500-wifi-reboot

Script to reboot a devolo dlan 500 wifi adaptor remotely.

## Usage

1. Install the script /usr/local/bin
2. Configure the adaptor(s) with static IP address(es)
3. Add a cron entry for the script with the relevant adaptor IP addresses

```
git clone https://github.com/rjlee/devolo-500-wifi-reboot.git
cd devolo-500-wifi-reboot
sudo cp devolo /usr/local/bin/
sudo chmod u+x /usr/local/bin/devolo
sudo crontab -e
6 0 * * * /usr/local/bin/devolo 192.168.0.20 192.168.0.21
```

## Notes

This has been tested to work with the 3.1.3 firmware, which is included in this repo.

It works by temporarily enabling telnet on the adaptor via a hidden option in the web interface and issuing a reboot command via telnet.  Once the device reboots, telnet is disabled again.
