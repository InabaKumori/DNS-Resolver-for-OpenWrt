# DNS Resolver for OpenWrt

This repository contains a DNS resolver script for OpenWrt that ensures proper startup and functionality of the `https-dns-proxy` and `dnsmasq` services. The script is designed to improve DNS resolution reliability and provide detailed logging for troubleshooting purposes.

## Features

- Checks the status of the `https-dns-proxy` service and starts it if not running
- Starts the `dnsmasq` service after ensuring `https-dns-proxy` is running
- Performs a DNS resolution test using `dig` to verify proper functioning
- Logs detailed messages to a log file for monitoring and troubleshooting

## Prerequisites

- OpenWrt installed on your router
- `https-dns-proxy` and `dnsmasq` services installed and configured

## Installation

1. SSH into your OpenWrt router.

2. Clone this repository or download the `dns-resolver` script:

   ```
   git clone https://github.com/inabakumori/dns-resolver.git
   ```

   or

   ```
   wget https://raw.githubusercontent.com/inabakumori/dns-resolver/main/dns-resolver
   ```

3. Move the `dns-resolver` script to the `/etc/init.d/` directory:

   ```
   mv dns-resolver /etc/init.d/
   ```

4. Make the script executable:

   ```
   chmod +x /etc/init.d/dns-resolver
   ```

5. Enable the script to start at boot:

   ```
   /etc/init.d/dns-resolver enable
   ```

## Usage

The DNS resolver script will automatically start at boot and perform the necessary checks and actions. You can also manually start, stop, or restart the script using the following commands:

- Start: `/etc/init.d/dns-resolver start`
- Stop: `/etc/init.d/dns-resolver stop`
- Restart: `/etc/init.d/dns-resolver restart`

## Logging

The script logs detailed messages to the `/var/log/dns-resolver.log` file. You can view the log file to monitor the script's actions and troubleshoot any issues:

```
cat /var/log/dns-resolver.log
```

The log file will contain timestamped messages indicating the status of the `https-dns-proxy` and `dnsmasq` services, as well as the results of the DNS resolution test.

## Testing

This script has been successfully tested on OpenWrt. If you encounter any issues or have suggestions for improvement, please open an issue on the GitHub repository.

## License

This project is licensed under the GNU General Public License v3.0. See the [LICENSE](LICENSE) file for details.

## Acknowledgements

- OpenWrt community for their excellent documentation and support
- DNS-over-HTTPS (DoH) providers for their secure and reliable DNS services

## Disclaimer

This script is provided as-is without any warranty. Use it at your own risk. The author is not responsible for any damage or issues caused by the use of this script.

---
