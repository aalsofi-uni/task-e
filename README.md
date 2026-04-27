# Task E: Compliance and Supply Chain

<<<<<<< HEAD
### Overview

This task focuses on generating a Software Bill of Materials (SBOM) for a containerised web application and explaining how it supports compliance with secure software development practices.

### Step Used
=======
## D.1 Overview

This task focuses on generating a Software Bill of Materials (SBOM) for a containerised web application and explaining how it supports compliance with secure software development practices.

## Step Used
>>>>>>> 435653e184186b795d3129fcc3bd3c4b7a826eae
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
<<<<<<< HEAD
### SBOM Generation
=======
### D.2 SBOM Generation
>>>>>>> 435653e184186b795d3129fcc3bd3c4b7a826eae

An SBOM was generated using Syft, a tool used to analyse software components and dependencies within an application.

The following command was executed in the project directory:
```
<<<<<<< HEAD
syft . -o cyclonedx-json > sbom.json
```

The tool was used to scan the web application, and the scan completed successfully. The SBOM identified the application’s dependencies, including libraries such as Flask and its related components. The generated sbom.json file was saved in the webapp folder.

**Evidence 1**

The following screenshot shows the successful execution of the SBOM generation command:

![alt text](<Screenshots/successful execution of the SBOM generation command.png>)


### CI/CD Pipeline Execution (Automation Evidence)

The SBOM generation process was automated using GitHub Actions. The workflow runs automatically when code is pushed to the repository and executes in a clean environment.

This ensures that the SBOM is generated consistently without manual interference and supports secure software development practices.

**Evidence 2**

The following screenshot shows a successful GitHub Actions workflow run:

![alt text](<Screenshots/successful GitHub Actions workflow.png>)

### Identified Components

The components used in the application were identified through the generated SBOM file and analysis of the project dependencies.

The main components include:

- Python 3  
- Flask  
- Jinja2  
- Werkzeug  
- SQLite3  

These components form the Software Bill of Materials (SBOM) for the application and provide a clear overview of the software dependencies.


**Evidence**

The following screenshots provide evidence of the SBOM generation process and its results.

**Evidence 1: Syft Scan Execution**
The screenshot below shows the successful execution of the Syft command used to generate the SBOM.

![alt text](<Screenshots/successful execution of the SBOM generation command.png>)

**Evidence 2: Generated SBOM File**
The followint generated  `sbom.json` file saved in the project directory: task-e/webapp/sbom.json.


### Compliance with NIST SSDF

The SBOM supports compliance with the NIST Secure Software Development Framework by improving visibility into the software supply chain.

**This helps to:**

- Identify vulnerable or outdated dependencies.
- Improve overall software security.
- Support auditing and compliance requirements.


### Importance of SBOM

 SBOM is an important artifact in secure software development as it:

- Provides transparency of all software components.
- Helps detect security risks in third-party libraries.
- Supports better management of dependencies.


 ### Conclusion
=======
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
>>>>>>> 435653e184186b795d3129fcc3bd3c4b7a826eae

The SBOM provides a clear understanding of the components used within the application. Although the automated tool did not detect packages, manual analysis ensured that all key dependencies were identified. This supports secure development practices and aligns with compliance frameworks such as the NIST SSDF.