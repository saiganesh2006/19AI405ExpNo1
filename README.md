<h1>ExpNo 1 :Developing AI Agent with PEAS Description</h1>
<h3>Name: D.B.V. SAI GANESH</h3>
<h3>Register Number: 212223240025</h3>


<h3>AIM:</h3>
<br>
<p>To find the PEAS description for the given AI problem and develop an AI agent.</p>
<br>
<h3>Theory</h3>
<h3>Medicine prescribing agent:</h3>
<p>Such this agent prescribes medicine for fever (greater than 98.5 degrees) which we consider here as unhealthy, by the user temperature input, and another environment is rooms in the hospital (two rooms). This agent has to consider two factors one is room location and an unhealthy patient in a random room, the agent has to move from one room to another to check and treat the unhealthy person. The performance of the agent is calculated by incrementing performance and each time after treating in one room again it has to check another room so that the movement causes the agent to reduce its performance. Hence, agents prescribe medicine to unhealthy.</p>
<hr>
<h3>PEAS DESCRIPTION:</h3>
<table>
  <tr>
    <td><strong>Agent Type</strong></td>
    <td><strong>Performance</strong></td>
     <td><strong>Environment</strong></td>
    <td><strong>Actuators</strong></td>
    <td><strong>Sensors</strong></td>
  </tr>
    <tr>
    <td><strong>Medicine prescribing agent</strong></td>
    <td><strong>Treating unhealthy, agent movement</strong></td>
     <td><strong>Rooms, Patient</strong></td>
    <td><strong>Medicine, Treatment</strong></td>
    <td><strong>Location, Temperature of patient</strong></td>
  </tr>
</table>
<hr>
<H3>DESIGN STEPS</H3>
<h3>STEP 1:Identifying the input:</h3>
<p>Temperature from patients, Location.</p>
<h3>STEP 2:Identifying the output:</h3>
<p>Prescribe medicine if the patient in a random has a fever.</p>
<h3>STEP 3:Developing the PEAS description:</h3>
<p>PEAS description is developed by the performance, environment, actuators, and sensors in an agent.</p>
<h3>STEP 4:Implementing the AI agent:</h3>
<p>Treat unhealthy patients in each room. And check for the unhealthy patients in random room</p>
<h3>STEP 5:</h3>
<p>Measure the performance parameters: For each treatment performance incremented, for each movement performance decremented</p>



<h3>Program</h3>

```python
import random

class MedicinePrescribingAgent:
    def __init__(self):
        self.location = "Room1"  # Initial room location
        self.patient_temperature = { "Room1": random.uniform(97, 100),
                                     "Room2": random.uniform(97, 100) }
        self.performance = 0  # Initial performance measure

    def move_to_room1(self):
        if self.location != "Room1":
            self.location = "Room1"  # Move to Room1

    def move_to_room2(self):
        if self.location != "Room2":
            self.location = "Room2"  # Move to Room2

    def prescribe_medicine(self):
        temp = self.patient_temperature[self.location]
        if temp > 98.5:  # Check if patient is unhealthy
            print(f"Prescribed medicine in {self.location} (Temp: {temp:.1f})")
            self.performance += 10  # Increment performance for treating
            self.patient_temperature[self.location] = 98.0  # Normalize temperature
        else:
            print(f"No treatment needed in {self.location} (Temp: {temp:.1f})")

    def perform_action(self, action):
        if action == "move_room1":
            if self.location != "Room1":
                self.performance -= 1  # Penalize movement
            self.move_to_room1()
        elif action == "move_room2":
            if self.location != "Room2":
                self.performance -= 1  # Penalize movement
            self.move_to_room2()
        elif action == "treat":
            self.prescribe_medicine()
        else:
            print("Invalid action")

    def print_status(self):
        print(f"Location: {self.location}, Temperatures: {self.patient_temperature}, Performance: {self.performance}")


# Example usage:
agent = MedicinePrescribingAgent()

# Treat patients and move between rooms
agent.perform_action("treat")
agent.print_status()
agent.perform_action("move_room2")
agent.print_status()
agent.perform_action("treat")
agent.print_status()
agent.perform_action("move_room1")
agent.print_status()
agent.perform_action("treat")
agent.print_status()

```

## Output:

<img width="934" height="199" alt="image" src="https://github.com/user-attachments/assets/cea1992d-0fc5-4c1a-9dcb-155e34f9e83f" />


## Result:

Thus the Developing AI Agent with PEAS Description was implemented using python programming.
