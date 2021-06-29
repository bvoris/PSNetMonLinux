# PSNetMonLinux
Setting up a PSNetMon IoT Device in Linux


# Update Raspbian
sudo apt-get update <BR />
sudo apt-get upgrade -y <BR />

Install powershell <BR /> 
https://docs.microsoft.com/en-us/powershell/scripting/install/installing-powershell-core-on-linux?view=powershell-7.1#raspbian
 <BR />
###################################
# Prerequisites

# Update package lists
sudo apt-get update

# Install libunwind8 and libssl1.0
Regex is used to ensure that we do not install libssl1.0-dev, as it is a variant that is not required <BR />
sudo apt-get install '^libssl1.0.[0-9]$' libunwind8 -y <BR />

###################################
# Download and extract PowerShell

# Grab the latest tar.gz
wget https://github.com/PowerShell/PowerShell/releases/download/v7.1.3/powershell-7.1.3-linux-arm32.tar.gz

# Make folder to put powershell
mkdir ~/powershell

# Unpack the tar.gz file
tar -xvf ./powershell-7.1.3-linux-arm32.tar.gz -C ~/powershell

# Start PowerShell
~/powershell/pwsh

# Start PowerShell from bash with sudo to create a symbolic link
sudo ~/powershell/pwsh -c New-Item -ItemType SymbolicLink -Path "/usr/bin/pwsh" -Target "$PSHOME/pwsh" -Force


install apache2 http <BR />
https://www.raspberrypi.org/documentation/remote-access/web-server/apache.md
 <BR />
sudo apt update <BR />
sudo apt install apache2 -y <BR />
