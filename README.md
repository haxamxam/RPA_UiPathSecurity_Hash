# RPA UiPath Client Security Hash

Robotic Process Automation case study on UiPath to hash and update Client Security Key.

## Documentation


The REFramework Documentation can be accessed through this link:

[Robotic Enterprise Framework](https://github.com/UiPath/ReFrameWork/blob/master/Documentation/REFramework%20documentation.pdf)


## Robotic Enterprise Template

**REFramework Template**

The framework template allows users to design effective processes as it provides several methods for storing, reading and modifying configuration project data. Furthermore, the framework provides methods to handle exceptions and log event activities.


- The REFramework is built on top of Transactional Business Process template

- It utilises State Machine layout for the phases of automation project

- It offers high level exception handling and application recovery

- Keeps external settings in *Config.xlsx* file and Orchestrator assets
pulls credentials from Credential Manager and Orchestrator assets

- The framework gets the transaction data from Orchestrator queue and updates back status of the transaction


- It takes screenshots of applications to handle application exception


- A sample Notepad application with dummy Excel input data can be executed for testing purposes




## Application usage

The application is divided into several states.

**1. Init State**
                                 
- *Init* all the the settings from the Configuration file and orchestrator assets.

- *Init* all applications through the settings

- *Retry* a specific number of times if transaction or settings fail

**2. Get Transaction Data**

- *Gets* the Orchestrator queue 

**3. Process Transaction**

- *Try* to process transaction item 
 
- *Display* exceptions and try to handle them. *Retry* transaction
 
- *Set* status of transaction item processed

- *Update* status of transaction item processed

**4. End Process**

- *Close* all applications from the process.

## How to run it

- Go to the *Config Excel file* and go to the settings tab

- Under the *Name Column* and *Value Column* make sure you have the following values.  

           System1_URL:              https://acme-test.uipath.com/
           System1_Credential:       System1_Credential
           logF_BusinessProcessName: Framework
           SHA1ONLINE_URL:           http://www.sha1-online.com/

**Note:** Please also make sure that you have the same settings for your Orchestrator



## License
[MIT](https://choosealicense.com/licenses/mit/)
