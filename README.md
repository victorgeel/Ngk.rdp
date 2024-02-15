# RDE
# Reverse Windows RDP for GitHub Actions
Enable RDP access on GitHub Actions VMs for general use.

## Usage
1) Create an account on [ngrok](https://dashboard.ngrok.com/signup), and copy your auth token displayed [here](https://dashboard.ngrok.com/get-started/your-authtoken)

2) Fork this repository

3) Go to the Settings tab of your repository, and go to Secrets, add the following secrets:
```
Name: NGROK_AUTH_TOKEN
Example Value: (obviously you insert the ngrok auth token of your account that you obtained in step 1)

Name: RDP_PASSWORD
Example Value: (you insert here the password that you will use for connect via RDP)
```

All of those secrets are required for the script to work, if you forget to add one, then it will throw an error

4) Trigger an build, by editing this README or uploading anything to your repository, don't modify the contents of the resources or scripts folders

5) Go to the Actions tab of your repository, go to your build process and wait until the pre-last step, that it will hang forever while setting ngrok's tunnel

6) Visit ngrok's tunnel list [dashboard](https://dashboard.ngrok.com/endpoints/status)

7) Take note of the active tunnel host and port

8) Connect to the host and port combination with a RDP client of your preference

9) If it requires an username, write "runneradmin" and as password, the password that you wrote in the RDP_PASSWORD secret in step 3

10) Once connected, be sure to not close any already open processes and windows, and most importantly: DO NOT UNINSTALL NOTHING

11) Enjoy!

### Please note that the duration of the runners in GitHub Actions is for 6 hours, so, the RDP machine lasts 6 hours.
