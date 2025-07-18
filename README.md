# Melissa - Email Object Windows C++

## Purpose
This code showcases the Melissa Email Object using C++.

Please feel free to copy or embed this code to your own project. Happy coding!

For the latest Melissa Email Object release notes, please visit: https://releasenotes.melissa.com/on-premise-api/email-object/

For further details, please visit: https://docs.melissa.com/on-premise-api/email-object/email-object-quickstart.html

The console will ask the user for:

- Email 

And return 

- Mailbox Name
- Domain Name
- Top-Level Domain Name
- Top-Level Domain Description
- Result Codes

## Tested Environments
- Windows 10 64-bit Microsoft Visual C++ 14.34, Powershell 5.1
- Melissa data files for 2025-07
- Nmake 14.34
- Visual Studio 2022 Developer Command Prompt v17.4.2 64-bit

## Required File(s) and Programs

#### mdEmail.dll
This is the c++ code of the Melissa Object.

#### Data File(s)
- mdEmail.cfg
- mdEmail.db3

#### Dependencies
- mdEnums.h
- mdEmail.h
- mdEmail.lib

## Getting Started
These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

#### Visual Studio Developer Command Prompt
It is important to note that you must be able to initialize the Visual Studio Developer Command Prompt environment for `x86_x64` in order to test the Melissa Email Object. The Visual Studio Developer Command Prompt should already be downloaded if you have Microsoft Visual Studio installed. 

To check if you are able to intialize the Visual Studio Developer Command Prompt for `x86_x64`, you can open the start menu and search for `x86_x64 Cross Tools Command Prompt for VS 2022`. If this program exists, then you may continue to the next steps.

Alternatively, you can check to see if the following filepath exists: `C:\Program Files\Microsoft Visual Studio\2022\Professional\VC\Auxiliary\Build\vcvarsall.bat` (with Visual Studio 2022 installed). If the filepath exists, then you may continue to the next steps.

#### Set up Powershell settings
If running Powershell for the first time, you will need to run this command in the Powershell console: `Set-ExecutionPolicy RemoteSigned`.
The console will then prompt you with the following warning shown in the image below. 
 - Enter `'A'`. 
 	- If successful, the console will not output any messages. (You may need to run Powershell as administrator to enforce this setting).
	
 ![alt text](/screenshots/powershell_executionpolicy.png)

#### Download this project
```
git clone https://github.com/MelissaData/EmailObject-Cpp
cd EmailObject-Cpp
```

#### Set up Melissa Updater 
Melissa Updater is a CLI application allowing the user to update their Melissa applications/data.

- Download Melissa Updater here: <https://releases.melissadata.net/Download/Library/WINDOWS/NET/ANY/latest/MelissaUpdater.exe>
- Create a folder within the cloned repo called `MelissaUpdater`.
- Put `MelissaUpdater.exe` in `MelissaUpdater` folder you just created.

#### Different ways to get data file(s)
1.  Using Melissa Updater
	- It will handle all of the data download/path and dll(s) for you. 
2.  If you already have the latest DQS release zip, you can find the data file(s) in there
    - To pass in your own data file path directory, you may either use the '-dataPath' parameter or enter the data file path directly in interactive mode.
    - Comment out this line "DownloadDataFiles -license $License" in the powershell script.
    - This will prevent you from having to redownload all the files.

## Run Powershell Script
Parameters:
- -email: a test email address
 	
  This is convenient when you want to get results for a specific email address in one run instead of testing multiple email addresses in interactive mode.  

- -dataPath (optional): a data file path directory to test the Email Object
- -license (optional): a license string to test the Email Object
- -quiet (optional): add to the command if you do not want to get any console output from the Melissa Updater

When you have modified the script to match your data location, let's run the script. There are two modes:
- Interactive 

    The script will prompt the user for an email address, then use the provided email to test Email Object. For example:
    ```
    .\MelissaEmailObjectWindowsCpp.ps1
    ```
    For quiet mode:
    ```
    .\MelissaEmailObjectWindowsCpp.ps1 -quiet
    ```
    
- Command Line 

    You can pass an email address in ```-email``` parameter and a license string in ```-license``` parameter to test Email Object. For example:
    ```
    .\MelissaEmailObjectWindowsCpp.ps1 -email "info@melissa.com"
    .\MelissaEmailObjectWindowsCpp.ps1 -email "info@melissa.com" -license "<your_license_string>"
    ```
    For quiet mode:
    ```
    .\MelissaEmailObjectWindowsCpp.ps1 -email "info@melissa.com" -quiet
    .\MelissaEmailObjectWindowsCpp.ps1 -email "info@melissa.com" -license "<your_license_string>" -quiet
    ```

This is the expected output from a successful setup for interactive mode:

![alt text](/screenshots/output.png)

## Troubleshooting
Troubleshooting for errors found while running your program.

### C# Errors:
| Error      | Description |
| ----------- | ----------- |
| ErrorRequiredFileNotFound      | Program is missing a required file. Please check your Data folder and refer to the list of required files above. If you are unable to obtain all required files through the Melissa Updater, please contact technical support below. |
| ErrorLicenseExpired   | Expired license string. Please contact technical support below. |

## Contact Us
For free technical support, please call us at 800-MELISSA ext. 4 (800-635-4772 ext. 4) or email us at tech@melissa.com.

To purchase this product, contact the Melissa sales department at 800-MELISSA ext. 3 (800-635-4772 ext. 3).
