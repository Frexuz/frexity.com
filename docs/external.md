# External access to your devices

This is useful for allowing external people (or 3rd party services) to access your development machine, or for yourself to gain access with a mobile device.

To access your machine, use http://frexity.ddns.net:YOUR_PORT

Available services:

## Service: Rails development server

1. Rails development servers start from port 3100 (External). Then add your ending IP address
2. Find your sequence number by finding your connection's IP address. Local client IP's start at 192.168.0.100.
3. Look at the last digits (minus 100)

**Example:**
- Your IP: 192.168.0.103
- Your sequence = 103 - 100 = 3
- External port: 3100 + 3 = 3103
- Final url: http://frexity.ddns.net:3103

**Starting your Rails server**
- Make sure you start your server with the same port, `rails s -p 3103`
- For privacy reasons, we don't route stright to port 3000. In this way we can control when the external access in ON or OFF.

**Notes:**
- If you're having problems connecting externally, try allowing any IP with `rails s -p 3103 -b 0.0.0.0`

## Note

- If we need more flexibility in the future, we can change the setup :)
