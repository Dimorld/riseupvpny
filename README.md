# Riseup VPN Client

This software/bash script is a simple front end to the openvpn command line utility, it was written in Puppy Linux FOSSAPUP to handle the connection to the Riseup VPN service

[a relative link](jammy32demostracion-2023-12-23_05.38.28.mp4)
[a relative link](path%20with%20spaces/other_file.md)

## Dependencies

- OpenVPN 2.4.12

- YAD

- Wget 1.20.3

- GNU bash 5.0.17

- gtkdialog-splash (puppy linux only app?)

- ipv6 kernel module

- tun kernel module

- Openssl

## Usage

- Make sure you have a working internet connection to the outside world, then launch the script/program from your system's menu, the rest is self-explanatory, if a successful connection is established, a tray icon will appear, Right-Click on it to see the menu options available

- If you can not start the software/script read the documentation, to access it, in the terminal run: ```riseupvpny --help``` 

- The software script is a front end to openvpn, you can add or remove settings by directly modifying the file ```/root/.riseupvpn/riseup_configuration.ovpn```

## Troubleshooting

**First and foremost, make sure you have a working internet connection to the outside world**

**If there are firewalls turned on, turn them off**

**If you can not start the software/script you can access this document via terminal: ```riseupvpny --help```**

**Access key files expire, if you have been connecting for a while, perhaps it is time to get a new one, in terminal run: ```riseupvpny --renew-credentials```**

### When the program is started, the message "The computer is already connected to Riseup VPN" appears on the screen

1. In the terminal emulator or console type: ```killall openvpn```, and press ENTER

2. Restart the program

### The start window entries, such as Gateway, Protocol, or Port, are empty, or have gibberish

1. Click Cancel

2. Follow steps at the beginning of the Troubleshooting section

### If Everything Fails

1. Uninstall the PET package

2. Delete the /root/.riseupvpn directory and its contents

3. Install the PET package again

## Things To Consider  

- The script is heavily commented, it goes through the thought process of the person who wrote it, if you read it, you will have a better understanding of what it does, you are encouraged to improve it, especially since it was written by a complete amateur.

- Older YAD versions may cause icon rendering problems

- The PET package installs the following files:

```
/
├── root
│   └── .riseupvpn
│       ├── c_port
│       ├── c_protocol
│       ├── c_server
│       ├── first_run
│       └── riseup_configuration.ovpn
└── usr
    ├── bin
    │   └── riseupvpny
    └── share
        ├── applications
        │   └── riseupvpny.desktop
        ├── doc
        │   └── riseupvpny
        │       └── riseupvpny.html
        ├── icons
        │   ├── connect_riseup.svg
        │   ├── riseup.svg
        │   ├── vpnriseup.svg
        │   └── vpn.svg
        └── locale
            └── es
                └── LC_MESSAGES
                    ├── riseupvpny.mo
                    ├── riseupvpny.po
                    └── riseupvpny.pot

12 directories, 15 files

```
- Once the script/software is run for the first time, it creates four files:
    
    - Three in the /root/.riseupvpn directory, a certificate file (riseup.crt), a key file (client.key), and a list of servers file (servers_list.txt)
    
    - A log file (riseupvpn.log) in the /tmp directory

## Learn More About Riseup

https://riseup.net/

## Learn More About Openvpn Connetivity Issues

https://openvpn.net/community-resources/how-to/#starting-up-the-vpn-and-testing-for-initial-connectivity
