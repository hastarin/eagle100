# eagle100
Rainforest EAGLE 100 client (forked from uEagle)

## Maintenance status

**This library is unmaintained.**
I no longer own an EAGLE-100, so I can't test or review changes.
It is used by Home Assistant's `rainforest_eagle` integration, and I've stepped down as that integration's codeowner ([home-assistant/core#190792](https://github.com/home-assistant/core/pull/190792)).

I'm open to transferring this repository and the PyPI project to anyone with an EAGLE-100 who wants to take it on.
Please open an issue if you're interested.

Basic, lightweight client for accessing the local REST API of Rainforest Automation's EAGLE 100 device.

Based off a micropython module, this uses minimal local resources.

This has been forked from [toddsay/uEagle](https://github.com/toddsay/uEagle) to get his fix to [jcalber/uEagle](https://github.com/jcalbert/uEagle) published to PyPi.
Example use:

```python
from eagle100 import Eagle
 
CLOUD_ID = '012abc'
INSTALL_CODE = '0123456789abcdef'
ADDRESS = '192.168.1.123' #optional if your platform can resove mDNS
 
eagle = Eagle(CLOUD_ID, INSTALL_CODE, address=ADDRESS)
 
demand_data = eagle.get_instantaneous_demand()
print('Current Usage: {:.3f} kW'.format(demand_data['Demand']))
```
