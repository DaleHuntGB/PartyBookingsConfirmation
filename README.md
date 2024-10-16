# Party Booking Confirmation

## Libraries:
- [Flask](https://flask.palletsprojects.com/en/3.0.x/)
- [JSON](https://docs.python.org/3/library/json.html)
- [DOCX](https://pypi.org/project/python-docx/)
- [BytesIO](https://docs.python.org/3/library/io.html)

### BytesIO & GDPR:
The `BytesIO` implementation will utilises this library by storing all user information in the memory of the server rather than the file-system, afterwhich the `send_file` function will send this directly back to the user for download. Once this cycle has completed, memory is reclaimed passively by Python's Garbage Collection. This should hopefully cover all GDPR implications, however, further security can be added to utilised HTTPS for file transfers.

## How It Works

The user access the [Web App](partybookingsconfirmation.onrender.com) and inputs all required information. Once all information is completed, the user can press the `Submit` button which will invoke the Python Script. This will generate a Word Document based on the template provided by replacing key words with the corresponding information. The user is prompted to download the generated file, and is named `Customer Name` - `Party Type` - `Party Confirmation`. As stated previously, all user information is stored in memory on the server side and cleared up with Garbage Collection, the Word Document is not stored on the server file-system for security.

## Implementation Requirements

None, this is a Web Application and is hosted on [Render](https://render.com/) and utilises Flask to build an `index.html` file that the user interacts with. This is accessible via any browser on any operating system. No Python libraries are required for install as this is handled externally.

### Note: If you are accessing the webpage and it is taking time to load, it is in the processes of being deployed. Servers shutdown during downtime.

Built & Maintained by Dale Hunt.
