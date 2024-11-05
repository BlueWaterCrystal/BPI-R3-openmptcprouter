# BPI-R3 OpenMPTCPRouter

A robust and efficient multi-path TCP (MPTCP) routing solution for the BPI-R3 platform, designed to optimize network bonding for faster and more reliable internet connections. This project provides a precompiled image and kernel modifications for use with the BPI-R3 router.

---

## Notes

- **eth1** is LAN by default, which is the first SFP port.
- For files containing the words **'port swap'**, the LAN should be the WAN port by default, which is the first RJ45 port.

---

## Known Issues

- **v0.61** - MPTCP aggregation doesn't seem to work for VPNs, only proxies (e.g., shadowsocks, v2ray, xray-core).
- **v0.61** - IPv6 6in4 doesn't work.
- **v0.62** - Doesn't boot due to a partition error (`alternate GPT is invalid, using primary GPT`).

---

## Recommendations

- **Disable SQM** - It seems to impact performance and massively hinders retransmission when there is packet loss.
- **Xray Trojan** seems to be the fastest proxy option and also supports UDP.
- **V2Ray/XRay UDP = true**
- **IPv4 TCP SYN retries = 10**
- **Disable nDPI** and **Modem Manager** if not needed.
- **BBRv3** (for enhanced TCP performance).

---

## How to Compile

- Guide: [https://github.com/Ysurac/openmptcprouter/wiki/Create-image-for-unsupported-platform](https://github.com/Ysurac/openmptcprouter/wiki/Create-image-for-unsupported-platform)

- **OS**: Debian 12, ideally a non-root user
- The necessary APT packages are listed in the [`apt-requirements.txt`](./apt-requirements.txt) file.
```
sudo dpkg --set-selections < installed_packages.txt
sudo apt-get update
sudo apt-get dselect-upgrade
```
---

## License

This project is licensed under the **GPL-3.0 License**. See the [LICENSE](LICENSE) file for details.

---

## Acknowledgements

- **OpenMPTCPRouter**: [https://github.com/Ysurac/openmptcprouter](https://github.com/Ysurac/openmptcprouter)
- **BPI-R3**: [https://wiki.banana-pi.org/Banana_Pi_BPI-R3](https://wiki.banana-pi.org/Banana_Pi_BPI-R3)

---
