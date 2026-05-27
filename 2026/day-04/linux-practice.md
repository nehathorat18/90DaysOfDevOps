## Process checks
<img width="1426" height="982" alt="Picture1" src="https://github.com/user-attachments/assets/765b9e48-9130-4934-ba30-bb477bb745e4" />
<img width="1479" height="935" alt="Picture2" src="https://github.com/user-attachments/assets/4b9d40b3-ef94-4e24-b2f6-ee74f807963c" />
<img width="593" height="219" alt="Picture3" src="https://github.com/user-attachments/assets/1e29d02a-0638-4912-bdf9-75643734034d" />

## Service checks
<img width="962" height="871" alt="Picture4" src="https://github.com/user-attachments/assets/b3fcb4b2-33e6-46f3-b22a-a1e1f3380efc" />

## Log checks
<img width="1575" height="589" alt="Picture5" src="https://github.com/user-attachments/assets/0987cac6-ef1e-4552-b4da-ec9529791ac3" />

## Mini troubleshooting steps
<img width="1886" height="973" alt="Picture6" src="https://github.com/user-attachments/assets/25d9189f-3475-4a84-875d-744f724ce50f" />
<img width="1919" height="726" alt="Picture7" src="https://github.com/user-attachments/assets/fe0a41ef-b837-427c-9c1e-3d6a813f4e5a" />
<img width="1909" height="935" alt="Picture8" src="https://github.com/user-attachments/assets/22731447-54d0-4240-9b5d-25e85d552cbd" />
<img width="1909" height="630" alt="Picture9" src="https://github.com/user-attachments/assets/6333bd40-e611-42da-8901-ccad5c07b3fb" />
<img width="1903" height="633" alt="Picture10" src="https://github.com/user-attachments/assets/3f65b786-90fd-4793-8ef3-169b781bf89a" />


### Other commands

systemctl list-units --type=service    # only services
systemctl list-units --type=socket
systemctl list-units --type=mount
systemctl list-units --type=timer
systemctl list-units --state=failed

journalctl -r
<img width="1900" height="372" alt="image" src="https://github.com/user-attachments/assets/1537395a-eb3d-4d37-bacc-54d9d932c533" />
<img width="1845" height="885" alt="image" src="https://github.com/user-attachments/assets/ea320196-051b-4e5f-b3f4-f0deda8a8ad9" />


journalctl -u nginx             # logs for nginx service
journalctl -u nginx -f          # follow nginx logs live
journalctl -u ssh -u nginx      # logs for multiple units
journalctl - list all logs of systemd
journalctl -r   -> most recent log of systemd
<img width="1897" height="557" alt="image" src="https://github.com/user-attachments/assets/11bb5f58-5367-41b7-9778-a168b263103a" />

systemctl status $SERVICE          # overview + recent logs
systemctl is-active $SERVICE       # active / inactive
systemctl is-enabled $SERVICE      # enabled / disabled
journalctl -u $SERVICE -p err      # errors only
pgrep -la $SERVICE                 # running PID(s)

<img width="1707" height="458" alt="image" src="https://github.com/user-attachments/assets/9be12896-3d7c-46ec-8ede-81270e4ccd16" />
<img width="1467" height="253" alt="image" src="https://github.com/user-attachments/assets/60867c83-4351-4a98-b289-8e9e3ebb6ca5" />
<img width="1907" height="390" alt="image" src="https://github.com/user-attachments/assets/249c62ef-012b-4f52-854e-b34f9f78ceb5" />



