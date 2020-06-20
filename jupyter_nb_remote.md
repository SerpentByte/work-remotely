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
Once the password has been generated you can start with hosting the sever.<\br>
In the terminal, ssh into the host and navigate to the location where you would 
want to open the notebook. Then type the following into the terminal
```$ jupyter notebook --no-browser --port=8889```
This starts the server only with a broadcasting port of 8889 (default for local system is 8888)
__This terminal has to be kept open.__

### Step 3
In a terminal on your guest, type
```$ ssh -N -f -L localhost:8888:localhost:8889 <username>@<IP>```
where username will be the username for host and IP is host's IP<\br>
Example:<\br>
ssh -N -f -L localhost:8888:localhost:8889 user@192.168.0.1

### Step 4
open your favourite browser and in the url type<\br>
localhost:8888/<\br>
The notebook will as for the password setup in __step 1__, or whichever password you had setup earlier.
On successfull login you will be able to see the homepage, but everything shown here is in the host device.


### Step 5 (OPTIONAL)
To check if you are really using the host's resources (RAM, CPU and HDD),
create a file in the host where you have opened the notebook.
Check if the jupyter tree is displaying it. Check if it is present in your guest.
(Unless it is already there. In that create something you do not have on you guest)

