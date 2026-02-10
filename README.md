<h1>ExpNo 1 :Developing AI Agent with PEAS Description</h1>
<h3>Name: sarmasaran M </h3>
<h3>Register Number:212224060239


<h3>AIM:</h3>
<br>
<p>To find the PEAS description for the given AI problem and develop an AI agent.</p>
<br>
<h3>Theory</h3>
<h3>Medicine prescribing agent:</h3>
<p>Such this agent prescribes medicine for fever (greater than 98.5 degrees) which we consider here as unhealthy, by the user temperature input, and another environment is rooms in the hospital (two rooms). This agent has to consider two factors one is room location and an unhealthy patient in a random room, the agent has to move from one room to another to check and treat the unhealthy person. The performance of the agent is calculated by incrementing performance and each time after treating in one room again it has to check another room so that the movement causes the agent to reduce its performance. Hence, agents prescribe medicine to unhealthy.</p>
```
import random
ROOMS = ["Room 1", "Room 2"]
FEVER_THRESHOLD = 98.5
environment = {
    "Room 1": round(random.uniform(97.0, 101.0), 1),
    "Room 2": round(random.uniform(97.0, 101.0), 1)
}
agent_location = "Room 1"
performance_score = 0

def check_temperature(room):
    temp = environment[room]
    print(f"Checking {room}... Patient temperature: {temp}°F")
    return temp

def treat_patient(room):
    global performance_score
    print(f"Treating patient in {room}... ")
    performance_score += 1 

def move_to(room):
    global agent_location, performance_score
    if agent_location != room:
        print(f"Moving from {agent_location} to {room}... ")
        agent_location = room
        performance_score -= 1  
print("Medicine Prescribing Agent Simulation Started \n")

for room in ROOMS:
    move_to(room)
    temp = check_temperature(room)
    if temp > FEVER_THRESHOLD:
        treat_patient(room)
    else:
        print(f"No treatment needed in {room}.\n")
print("\nSimulation Complete!")
print(f"Final Performance Score: {performance_score}")
print("Environment State:", environment)
```

<img width="596" height="345" alt="image" src="https://github.com/user-attachments/assets/739777d7-2b1c-4175-ad9f-3c5e0f794c61" />

