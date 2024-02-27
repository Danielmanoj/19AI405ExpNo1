<h1>ExpNo 1 :Developing AI Agent with PEAS Description</h1>
<h3>Name: MANOJ G</h3>
<h3>Register Number: 212222240060</h3>


<h3>AIM:</h3>

<p>To find the PEAS description for the given AI problem and develop an AI agent.</p>


<h3>Theory</h3>
<h3>Vaccum Cleaner agent:</h3>
<p>Performance Measure: minimize energy consumption, maximize dirt pick up. Making this precise:
one point for each clean square over lifetime of 1000 steps.

Environment: two squares, dirt distribution unknown, assume accions are deterministic and
environment is static (clean squares stay clean).

Actuators: Left, Right, Suck, NoOp.

Sensors: agent can perceive its location and whether location is dirty.</p>

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
    <td><strong>Vaccum Cleaner</strong></td>
    <td><strong>Cleanliness, Number of Movements</strong></td>
     <td><strong>Rooms, Dust</strong></td>
    <td><strong>Steering, Cleanliness</strong></td>
    <td><strong>Location, Motion</strong></td>
  </tr>
</table>

## DESIGN STEPS
### STEP 1:
Identifying the input:
### STEP 2:
Identifying the output:
### STEP 3:
Developing the PEAS description:
### STEP 4:
Implementing the AI agent
### STEP 5:
Measure the performance parameters


## PROGRAM
```

import random

import time



class VacuumEnvironment:

    """

    Environment for the vacuum cleaner agent.

    """



    def __init__(self):

        self.squares = {"A": "Dirty", "B": "Dirty"}

        self.agent_location = random.choice(["A", "B"]) # Start the agent at a random location



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

            return "NoOp" # No operation



if __name__ == "__main__":

    environment = VacuumEnvironment()

    agent = VacuumAgent()



    print("Initial state:")

    print("Agent Location:", environment.agent_location)

    print("Square Status:", environment.squares)

    print("Agent Performance:", agent.performance)



    while not environment.is_done():

        percept = environment.percept()

        action = agent.table_driven_program(percept)

        environment.execute_action(action)

        agent.performance += 1 # Increment performance for each action

        print("\nAgent performs action:", action)

        print("Agent Location:", environment.agent_location)

        print("Square Status:", environment.squares)

        print("Agent Performance:", agent.performance)

        time.sleep(1)



    print("\nAll squares are clean. Task completed!")

    print("Agent Performance:", agent.performance))


```

# OUTPUT

![image](https://github.com/Harish2404lll/19AI405ExpNo1/assets/141472096/04bf65ab-0329-469c-ba47-046e2413444c)


# RESULT
Thus, an AI agent is developed.
