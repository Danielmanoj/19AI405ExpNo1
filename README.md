<h1>ExpNo 1 :Developing AI Agent with PEAS Description</h1>
<h3>Name: Saravanan N</h3>
<h3>Register Number/Staff Id: TSML006</h3>


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

## VACUUM CLEANER AGENT
## DESIGN STEPS 
1. Define environment with two dirty squares, randomly placing the agent in one of them.
2. Implement agent behavior using a table-driven program for actions based on location and square status.
3. Create classes for Environment (`VacuumEnvironment`) and Agent (`VacuumAgent`).
4. Instantiate environment and agent, print initial state, and simulate actions until environment is clean.
5. Test scenarios to ensure correct agent behavior and environment updates.

## PROGRAM
```
Developing AI Agent with PEAS Description
Developed by: MANOJ G
RegisterNumber: 212222240060
```

```
class VacuumEnvironment:
    """
    Environment for the vacuum cleaner agent.
    """

    def __init__(self):
        self.squares = {"A": "Dirty", "B": "Dirty"}
        self.agent_location = random.choice(["A", "B"])  # Start the agent at a random location

    def percept(self):
        """
        Returns the agent's current location and the status of the square (clean or dirty).
        """
        return self.agent_location, self.squares[self.agent_location]

    def execute_action(self, action):
        """
        Performs the action specified by the agent.
        """
        if action == "Left":
            self.agent_location = "A"
        elif action == "Right":
            self.agent_location = "B"
        elif action == "Suck":
            self.squares[self.agent_location] = "Clean"

    def is_done(self):
        """
        Checks if the environment is done (all squares are clean).
        """
        return all(status == "Clean" for status in self.squares.values())


class VacuumAgent:
    """
    Vacuum cleaner agent.
    """

    def __init__(self):
        self.performance = 0

    def table_driven_program(self, percept):
        """
        Table-driven program for the agent.
        """
        location, status = percept
        if status == "Dirty":
            return "Suck"
        elif location == "A":
            return "Right"
        elif location == "B":
            return "Left"
        else:
            return "NoOp"  # No operation


if __name__ == "__main__":
    environment = VacuumEnvironment()
    agent = VacuumAgent()

    print("Initial state:")
    print("Agent Location:", environment.agent_location)
    print("Square Status:", environment.squares)
    print("Agent Performance:", agent.performance)

    while not environment.is_done():
        percept = environment.percept
```

## OUTPUT

![image](https://github.com/Danielmanoj/19AI405ExpNo1/assets/69635071/d3a5dd66-638f-4094-9827-0cf79d5f0724)

## RESULT
Thus the Developing AI Agent with PEAS Description was implemented using python programming.
