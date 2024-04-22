# Deraining, Defogging and Desnowing of Images and Videos
## DRDO POC



### Installation process
*Assuming the user has a installed python version>=3.10.9 and added to path.*
Users are recommended to use a Powershell throughout the installation process.



### Virtual Environment creation
`python -m venv name_of_your_env`



### virtual environment activation
traverse to the newly created virtual environment from the cmd and run the below commands.                       
    `scripts/activate.ps1` _(for powershell)_
    `scripts/activate.bat` _(for command prompt)_



### Clone the above project.
`git clone https://github.com/INAI-IIIT/DRDO_POC.git`



### Installing the requirements.txt file
go to the project directory and run the command
`pip install -r requirements.txt`



### Download the essential files (weight files)
from the given link download the files and place them in the root directory (project root directory)
https://iiitaphyd-my.sharepoint.com/:f:/g/personal/mohammed_ibrahim_ihub-data_iiit_ac_in/Epfsj3OjKLFJrHdFzThAda8BnKexz0vLQGz1hkth9oeWoQ?e=n25z8x



### Run the Application.
After successfull execution of all the above steps, the app is ready to use.
There are currently two modes of the application.
1. Deraining mode _(to initialize the application in this mode use syntax)_
  `python app.py --weights derain`
2. Defogging mode _(to initialize the application in this mode use syntax)_
  `python app.py --weights defog`



The flask application will be commenced and will be accessible at the given address.
    http://127.0.0.1:5005/



### UI Guidance
the above given link will open up a webpage through which the images and videos can be uploaded and processed.





