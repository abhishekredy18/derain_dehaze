# Deraining, Defogging, and Desnowing of Images and Videos
## DRDO POC

### Installation Process
- Assuming the user has Python version>=3.10.9 installed and added to the path.
- Users are recommended to use PowerShell throughout the installation process.

### Virtual Environment Creation
- Create a virtual environment using the following command:
```bash
python -m venv name_of_your_env
```

### Virtual Environment Activation
- Navigate to the newly created virtual environment directory and run the appropriate command based on your shell:
```bash
# For PowerShell
scripts/activate.ps1

# For Command Prompt
scripts/activate.bat
```

### Clone the Project
- Clone the repository using the following command:
```bash
git clone https://github.com/INAI-IIIT/DRDO_POC.git
```

### Installing the Requirements.txt File
- Navigate to the project directory and install the requirements using the command below:
```bash
pip install -r requirements.txt
```

### Download the Essential Files (Weight Files)
- Download the files from the following link and place them in the project root directory:
[Download weight files](https://iiitaphyd-my.sharepoint.com/:f:/g/personal/mohammed_ibrahim_ihub-data_iiit_ac_in/Epfsj3OjKLFJrHdFzThAda8BnKexz0vLQGz1hkth9oeWoQ?e=n25z8x)

### Run the Application
- After successful execution of all the above steps, the app is ready to use. 
- There are currently two modes of the application:
    - Deraining Mode (to initialize the application in this mode use the syntax):

      ```bash
      python app.py --weights derain
      ```
    - Defogging Mode (to initialize the application in this mode use the syntax):

      ```bash
      python app.py --weights defog
      ```
    
- The Flask application will commence and will be accessible at the following address:
    - http://127.0.0.1:5005/
    - The above link will open a webpage through which images and videos can be uploaded and processed.
