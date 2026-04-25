# Task E: Compliance and Supply Chain

## D.1 Overview

This task focuses on generating a Software Bill of Materials (SBOM) for a containerised web application and explaining how it supports compliance with secure software development practices.

## Step Used
requirements.txt file was created and placed inside webapp folder the purpose of the file is to list all external Python libraries that your application needs to run. The file include the follwing:

```
Flask==3.0.0
```

Dockerfile was created and placed in webapp folder, 
the purpose of the file is a script that automates the creation of a Container Image. It defines the entire operating system environment.

The file include the follwing:

```
FROM python:3.9-slim
WORKDIR /app
# This copies requirements.txt from your "webapp folder" into the container
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
# This copies app.py into the container
COPY app.py .
CMD ["python", "app.py"]
```
### D.2 SBOM Generation

An SBOM was generated using Syft, a tool used to analyse software components and dependencies within an application.

The following command was executed in the project directory:
```
syft .
```
The tool successfully scanned the application however, no packages were automatically detected. This is because the application does not include a dependency file such as requirements.txt, and dependencies are not installed within the scanned directory.

## D.3 Identified Components

Despite the automated scan not listing packages, the components used in the application were identified through manual analysis of the source code:

Python 3
Flask
Jinja2
Werkzeug
SQLite3

These components form the Software Bill of Materials (SBOM) for the application.

## D.4 Evidence

A screenshot of the Syft scan output is included as evidence, showing the successful scan and the absence of automatically detected packages.
![alt text](Screenshot.png)

## D.5 Compliance with NIST SSDF

The SBOM supports compliance with the NIST Secure Software Development Framework by improving visibility into the software supply chain.

This helps to:

Identify vulnerable or outdated dependencies
Improve overall software security
Support auditing and compliance requirements


## D.6 Importance of SBOM

An SBOM is an important artifact in secure software development as it:

Provides transparency of all software components
Helps detect security risks in third-party libraries
Supports better management of dependencies


 ## Conclusion

The SBOM provides a clear understanding of the components used within the application. Although the automated tool did not detect packages, manual analysis ensured that all key dependencies were identified. This supports secure development practices and aligns with compliance frameworks such as the NIST SSDF.