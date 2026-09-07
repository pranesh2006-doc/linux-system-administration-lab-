| Command                      | Use                                        |
| ---------------------------- | ------------------------------------------ |
| `ip link`                    | **Shows network interfaces**               |
| `ip addr`                    | **Shows IP addresses**                     |
| `hostname -I`                | **Shows machine IP**                       |
| `ip route`                   | **Shows routing/gateway**                  |
| `ping -c 4 8.8.8.8`          | **Tests internet connectivity**            |
| `ping -c 4 google.com`       | **Tests DNS + connectivity**               |
| `curl https://example.com`   | **Tests HTTP/website access**              |
| `nslookup google.com`        | **Finds domain IP using DNS**              |
| `dig google.com`             | **Detailed DNS information**               |
| `dig google.com +short`      | **Shows DNS IP quickly**                   |
| `ss -tuln`                   | **Shows listening TCP/UDP ports**          |
| `sudo ss -tulpn`             | **Shows ports and processes**              |
| `./commands/network-info.sh` | **Runs networking commands automatically** |
| `chmod +x network-info.sh`   | **Makes script executable**                |

minimal short notes :
ip link       → Network interfaces
ip addr       → IP addresses
hostname -I   → Machine IP
ip route      → Gateway / routes
ping          → Connectivity
curl          → HTTP request
nslookup      → DNS lookup
dig           → DNS details
dig +short    → DNS IP
ss -tuln      → Listening ports
ss -tulpn     → Ports + processes
./script.sh   → Run script
chmod +x      → Make executable
