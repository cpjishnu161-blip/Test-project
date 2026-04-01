# Test-project
import socket

target = "Target ip"

print(f"\nScanning target: {target}\n")

# Common ports list
ports = [21, 22, 23, 25, 53, 80, 110, 139, 143, 443, 445, 8080]

for port in ports:
    s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
    socket.setdefaulttimeout(1)

    result = s.connect_ex((target, port))

    if result == 0:
        print(f"Port {port} is OPEN")
    else:
        print(f"Port {port} is CLOSED")

    s.close()
