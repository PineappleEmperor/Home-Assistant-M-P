![GitHub](https://img.shields.io/github/license/PineappleEmperor/Home-Assistant-M-P)
![GitHub Repo stars](https://img.shields.io/github/stars/PineappleEmperor/Home-Assistant-M-P)
![GitHub release (latest by date)](https://img.shields.io/github/v/release/PineappleEmperor/Home-Assistant-M-P)
[![hacs_badge](https://img.shields.io/badge/HACS-Default-orange.svg)](https://github.com/hacs/integration)
![Pytest](https://github.com/PineappleEmperor/Home-Assistant-M-P/workflows/Pytest/badge.svg?branch=master)
![CodeQL](https://github.com/PineappleEmperor/Home-Assistant-M-P/workflows/CodeQL/badge.svg?branch=master)
![Validate with hassfest](https://github.com/PineappleEmperor/Home-Assistant-M-P/workflows/Validate%20with%20hassfest/badge.svg?branch=master)

![GitHub contributors](https://img.shields.io/github/contributors/PineappleEmperor/Home-Assistant-M-P)
![Maintenance](https://img.shields.io/maintenance/yes/2023)
![GitHub commit activity](https://img.shields.io/github/commit-activity/y/PineappleEmperor/Home-Assistant-M-P)
![GitHub commits since tagged version](https://img.shields.io/github/commits-since/PineappleEmperor/Home-Assistant-M-P)
![GitHub last commit](https://img.shields.io/github/last-commit/PineappleEmperor/Home-Assistant-M-P)
![Codecov branch](https://img.shields.io/codecov/c/github/PineappleEmperor/Home-Assistant-M-P/main)

## About Mail and Packages integration

The [Mail and Packages integration](https://github.com/PineappleEmperor/Home-Assistant-M-P) creates sensors for [supported shippers](https://github.com/PineappleEmperor/Home-Assistant-M-P/wiki/Supported-Shipper-Requirements) to show a snapshot of mail and **packages that are scheduled to be delivered the current day**. For the packages that are scheduled for delivery the current day a count of in transit and delivered packages will be provided. It also generates the number of USPS mail pieces and provides a rotating GIF of the USPS provided images of the mail, if available, for the current day.

## Credits:

From the original repo:
- Huge contributions from [@firstof9](https://github.com/firstof9) moving the project forward and keeping it active!

## How it works

From your instance of HASS, the [Mail and Packages integration](https://github.com/PineappleEmperor/Home-Assistant-M-P) connects to the email account you supply where your shipment notifications are sent. It reviews at the subject lines of the current day's emails from the [supported shippers](https://github.com/PineappleEmperor/Home-Assistant-M-P/wiki/Supported-Shipper-Requirements) and counts the subject lines that match known language from the [supported shippers](https://github.com/PineappleEmperor/Home-Assistant-M-P/wiki/Supported-Shipper-Requirements) about their transit status. For USPS Informed delivery emails, it also downloads the mail images to combine them into a rotating GIF. 
See the WIKI [information on how this works](https://github.com/moralmunky/Home-Assistant-Mail-And-Packages/wiki).

_**The email can not be deleted until the next day**_. You can have your email filtered into a folder and have the integration watch that folder.

The image will revert back to the no mail graphic after the first email check after midnight, local time.

* **All procedures are done locally on your machine.**
* **No external services are used to process your email.**
* **No data is sent outside of your local instance of Home Assistant**

##### *Privacy / Security Note
Please note that files stored in the `www` Home Assistant folder are [publicly accessible](https://www.home-assistant.io/integrations/http/#hosting-files) unless you have taken security measures outside of Home Assistant to secure it. For increased security and simplicity the USPS Informed Delivery image name is random by default and no longer has the option to turn it on/off. Two new sensors have been created that provide the local file path or a web accessible url for use in displaying or sending in various Home Assistant notification methods.

* `sensor.mail_image_system_path`
* `sensor.mail_image_url` - Requires that either `External_URL` or `Internal_URL` is defined in the general configuration options in Home Assistant.

## Support
[Configuration](https://github.com/moralmunky/Home-Assistant-Mail-And-Packages/wiki/Configuration-and-Email-Settings)

[Troubleshooting](https://github.com/moralmunky/Home-Assistant-Mail-And-Packages/wiki/Troubleshooting)

[Supported Shipper Requirements](https://github.com/moralmunky/Home-Assistant-Mail-And-Packages/wiki/Supported-Shipper-Requirements)

## Template and Examples
[USPS Informed Delivery Image](https://github.com/moralmunky/Home-Assistant-Mail-And-Packages/wiki/USPS-Informed-Delivery-Image)

[Text Summary](https://github.com/moralmunky/Home-Assistant-Mail-And-Packages/wiki/Mail-Summary-Message)

[Notificaions](https://github.com/moralmunky/Home-Assistant-Mail-And-Packages/wiki/Notifications)
