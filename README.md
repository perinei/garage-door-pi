# garage
control garage door and monitor status (open / close) using raspberry pi and AWS IoT

app should runs as a service that automatically starts at reboot.
you can use systemctl to start/enable/status/stop service.
example:
$ systemctl start garage
$ systemctl enable garage
$ systemctl status enable

example of service file configuration /usr/lib/systemd/system/garage.service

[Unit]

Description=Garage Manager

After=multi-user.target

[Service]

User=pi

Type=idle

ExecStart=/usr/bin/python3 /home/pi/garageapp/app.py --endpoint <mqtt broker endpoint> --root-ca /home/pi/garageapp/root-CA.crt --cert /home/pi/gar$

[Install]

WantedBy=multi-user.target
  
  
