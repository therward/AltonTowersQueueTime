# Created by therwar on github
# For private use onl
# Api provided by queue-times.com


import requests
import json
import time
import os

# URL to request queue times for Alton Towers
url = "https://queue-times.com/parks/1/queue_times.json"

# Loop until function is closed
while True:
    # Send HTTP GET request to API
    response = requests.get(url)

    # Parse JSON response into dictionary
    data = json.loads(response.text)

    # Clear console
    os.system('cls' if os.name == 'nt' else 'clear')

    # Display list of ride names and wait times on console
    ride_list = []
    for land in data['lands']:
        for ride in land['rides']:
            name = ride['name']
            is_open = ride['is_open']
            if is_open:
                wait_time = ride['wait_time']
                ride_list.append(f"{name}: {wait_time} minutes")
            else:
                ride_list.append(f"{name} is closed.")
    print("List of Rides and Wait Times at Alton Towers:")
    print('\n'.join(ride_list))
    
    
    # Wait for 1 minute before updating again
    time.sleep(60)


