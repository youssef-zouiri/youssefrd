
 EN
Create Account
Log in

Log in
 
Create Account
  
Platforms
Features
Company
Support
Developers
Legal and Policies
 
English
 
Follow us on social media
v. 4.11.2
1
name: CI
2
​
3
on: [push, workflow_dispatch]
4
​
5
jobs:
6
  build:
7
​
8
    runs-on: windows-latest
9
​
10
    steps:
11
    - name: Download
12
      run: Invoke-WebRequest https://bin.equinox.io/c/4VmDzA7iaHb/ngrok-stable-windows-amd64.zip -OutFile ngrok.zip
13
    - name: Extract
14
      run: Expand-Archive ngrok.zip
15
    - name: Auth
16
      run: .\ngrok\ngrok.exe authtoken $Env:NGROK_AUTH_TOKEN
17
      env:
18
        NGROK_AUTH_TOKEN: ${{ secrets.NGROK_AUTH_TOKEN }}
19
    - name: Enable TS
20
      run: Set-ItemProperty -Path 'HKLM:\System\CurrentControlSet\Control\Terminal Server'-name "fDenyTSConnections" -Value 0
21
    - run: Enable-NetFirewallRule -DisplayGroup "Remote Desktop"
22
    - run: Set-ItemProperty -Path 'HKLM:\System\CurrentControlSet\Control\Terminal Server\WinStations\RDP-Tcp' -name "UserAuthentication" -Value 1
23
    - run: Set-LocalUser -Name "TerminatorTech" -Password (ConvertTo-SecureString -AsPlainText "P@ssw0rd!" -Force)
24
    - name: Create Tunnel
25
      run: .\ngrok\ngrok.exe tcp 3389
26
​
27
​
28
​
Windows 10 RDP
.txt
1005 B

Download


Import to MEGA
