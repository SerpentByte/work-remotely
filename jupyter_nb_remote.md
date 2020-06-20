# Jupyter Notebook Remote access
This is how one can open a Jupyter Notebook server remotely (eg. your Desktop at a remote location)
and use a browser on your current device (eg. your laptop which you might be using from your home)
to execute jupyter notebook codes.
## Notations
host    ---> remote location computer (eg. Desktop at the institute/office)
guest   ---> device you are using right now (eg. the laptop you're using right now)

### Step 1 (If you have not set up login using password)
open a terminal on your guest device and ssh into your host device.
Type the following command. Enter a new password. Verify by entering the same password.
```$ jupyter notebook password
Enter password:   **************
Verify password:  **************
Wrote hashed password to /home/wasim/.jupyter/jupyter_notebook_config.json
```
### Step 2
Once the password has been generated, type the following into the terminal
```$ jupyter notebook --no-browser --port=8889```
This starts the server only with a broadcasting port of 8889 (default for local system is 8888)
* This terminal has to be kept open *

