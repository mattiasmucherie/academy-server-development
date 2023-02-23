# Internet

## Task 1: Find Your Local IP Address

### Method 1: Using the Command Prompt or Terminal

1. Open a Command Prompt (Windows) or Terminal (Mac/Linux) window.
1. Type "ipconfig" (Windows) or "ifconfig" (Mac/Linux) and press Enter.
1. Look for the "IPv4 Address" entry under your network adapter. This is your local IP address.

### Method 2: Using Network Properties (Windows)

1. Click on the network icon in the taskbar and select "Open Network & Internet Settings."
1. Scroll down to the "Advanced network settings" section and click on "Change adapter options."
1. Right-click on your network adapter and select "Status."
1. Click on the "Details" button.
1. Look for the "IPv4 Address" entry. This is your local IP address.

Note: Your local IP address is used for communication within your network and is not visible to devices outside of your network. It is important to keep this address private and secure.

## Task 2: Find Your Public IP Address

1. Open a web browser.
1. Go to https://www.whatismyip.com/ or https://www.whatismyipaddress.com/.
1. Your public IP address should be displayed on the page along with additional information such as your internet service provider (ISP) and location.

Note: Your public IP address is the address that is visible to devices outside of your network. This address can be used to identify your device and its location, so it's important to keep it private and secure.

## Task 3: Use Ping to Test Network Connectivity

1. Open a command prompt (Windows) or terminal window (Mac/Linux).
1. Type `ping google.com` and press Enter. Write down the IP address that is displayed.
1. Type `ping www.google.com` and press Enter. Write down the IP address that is displayed. Are they the same? If not, can you think of a reason why?
1. Note the time it took for each ping command to complete. Did the times differ?
1. Type `ping www.canberra100.com.au` and press Enter. Did it take longer than the previous pings to Google? Why do you think that is?

Note: Ping is a useful tool for testing network connectivity and latency. It sends packets of data to a target device and measures the time it takes for the device to respond. This information can be helpful in diagnosing network issues.
Ping is a good way to see if you're able to reach a different machine. You'll also get information about how long it took for the computers to connect.
