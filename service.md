## Step 1
Create the script that will be called and run

```
cd ~
touch iptvService.sh
chmod +x iptvService.sh
```

Put all the code in it

## Step 2
Create a systemmd service file in ```/etc/systemd/system/```
```
sudo nano /etc/systemd/system/iptvService.service
```

```
[Unit]
Description=My Script Service
After=network.target

[Service]
ExecStart=/path/to/your-script.sh
Restart=always
User=your-username
Group=your-groupname

[Install]
WantedBy=multi-user.target
```

Description: A short description of your service.<br>
After: Defines the service dependencies.<br>
ExecStart: The full path to your script.<br>
Restart: Configures the service to restart on failure.<br>
User and Group: The user and group under which the script should run (optional).<br>

## Step 3
Restart systemmd
```
sudo systemctl daemon-reload
```

## Step 4
Enable the sertvice to start on boot, and start the service

```
sudo systemctl enable my-script.service
sudo systemctl start my-script.service
sudo systemctl status my-script.service
```