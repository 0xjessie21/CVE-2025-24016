[![Python 3.x](https://img.shields.io/badge/python-3.x-yellow.svg)](https://www.python.org/)
# CVE-2025-24016
An unsafe deserialization vulnerability in Wazuh servers allows remote code execution through unsanitized dictionary injection in DAPI requests/responses. This issue arises from the way DistributedAPI parameters are serialized as JSON and then deserialized using the as_wazuh_object function in framework/wazuh/core/cluster/common.py.

If an attacker injects an unsanitized dictionary into a DAPI request or response, they can craft an unhandled exception (__unhandled_exc__), allowing arbitrary Python code execution.

# Screenshot
![cve-2025-24016](https://github.com/aratane/CVE-2025-24016/blob/main/wazuhrce.png)

| :exclamation:  **Disclaimer**  |
|---------------------------------|
| This project is primarily built to be used as a standalone CLI tool. **Running this exploit as a service may pose security risks.** It's recommended to use with caution and additional security measures. DWYOR |

# Installation
```
git clone https://github.com/0xjessie21/CVE-2025-24016.git
cd CVE-2025-24016/
pip install -r requirements.txt
```

# Usage
```sh
python3 CVE-2025-24016.py -h
```
<details>
  <summary>Expand full help flags</summary>
  
This will display help for the tool. Here are all the switches it supports.
```yaml
Usage:
  python3 CVE-2025-24016.py [flags]

options:
  -h, --help            show this help message and exit
  -u URL, --url URL     Target URL (ex: https://<worker-server>:55000/security/user/authenticate/run_as)
  -i IP, --ip IP        Local host for reverse shell connection
  -p PORT, --port PORT  Local port for reverse shell connection
```
</details>

# Credits

- [Aiman Al-Fatih](https://github.com/pondoksiber)
- [Cahyo Ramdhani](https://github.com/danarseno)
- [Michael Sanji](https://github.com/aratane)

<br>

## Contributors
<p align="left">
<a href="https://github.com/aratane"><img src="http://avatars.githubusercontent.com/u/76691705?v=4" width="50" height="50" alt="" style="max-width: 100%;"></a>
</p>
