# fastcom

<div align="left">
<a href="https://ppizarror.com"><img alt="@ppizarror" src="https://img.shields.io/badge/author-Pablo%20Pizarro%20R.-lightgray.svg" /></a>
<a href="https://opensource.org/licenses/MIT/"><img alt="License MIT" src="https://img.shields.io/badge/license-MIT-blue.svg" /></a>
<a href="https://www.python.org/downloads/"><img alt="Python 3.4+" src="https://img.shields.io/badge/python-3.4+-red.svg" /></a>
<a href="https://pypi.org/project/pyfastcom"><img alt="PyPi package" src="https://badge.fury.io/py/pyfastcom.svg" /></a>
<a href="https://github.com/ppizarror/pyfastcom/issues"><img alt="Open issues" src="https://img.shields.io/github/issues/ppizarror/pyfastcom" /></a>
<a href="https://pypi.org/project/pyfastcom/"><img alt="https://pypi.org/project/pyfastcom/" src="https://img.shields.io/pypi/dm/pyfastcom?color=purple" /></a>
</div><br />

Python API that gets the results from fast.com test using Selenium.

## Install

pyfastcom can be installed via pip. Simply run:

```bash
pip install pyfastcom
```

## Usage

To create a searcher object, use the *PyFastCom* class:

```python
from pyfastcom import PyFastCom

fast = PyFastCom()
```

To configure the path of the webdriver (Chrome as for now):

```python
fast.set_driver_path('path/to/webdriver/executable/')
```

Then, execute the `.run(timeout=120)` method. This function takes the timeout as an input. That is the maximum number of seconds before throwing an Exception. By default, the timeout is 240 s (2 minutes). The function returns the following dictionary:

```python
results = fast.run()
print(results) # {'client_ip': 'XXX', 'client_isp': 'XXX', 'client_location': 'XXX', 'download': (100, 'Mbps'), 'latency_download': (1, 'ms'), 'latency_upload': (1, 'ms'), 'server_info': 'XXX', 'upload': (100, 'Mbps')}
```

Also, the results can be obtained through the following methods:

- PyFastCom.**get_client_ip()**: Returns the client IP, *str*
- PyFastCom.**get_client_isp()**: Returns the client ISP, *str*
- PyFastCom.**get_client_location()**: Returns the client location, *str*
- PyFastCom.**get_download_speed()**: Returns the download speed, *(int, str)*
- PyFastCom.**get_download_latency()**: Returns the download latency, *(int, str)*
- PyFastCom.**get_upload_speed()**: Returns the upload speed, *(int, str)*
- PyFastCom.**get_upload_latency()**: Returns the upload latency, *(int, str)*
- PyFastCom.**get_server_info()**: Returns the server info, *str*
- PyFastCom.**ready()**: Returns true if the results exists, *bool*

Check out the provided <a href="https://github.com/ppizarror/pyfastcom/blob/main/example.py">example.py</a> to see the complete usage scenario.

## Author

[Pablo Pizarro R.](https://ppizarror.com) | 2020

## License

This project is licensed under MIT [https://opensource.org/licenses/MIT/](https://opensource.org/licenses/MIT/)
