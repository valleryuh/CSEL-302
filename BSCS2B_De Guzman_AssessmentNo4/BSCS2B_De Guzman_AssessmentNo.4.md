# Part 1 – Simulation Scenario

You will create a simple classroom participation simulation.
Each student agent has the following attributes:

Attribute	Description
energy	ability of the student to participate
score	participation score
status	active or inactive
Rules
1.	Students may participate in class.
2.	When participating:
o	score increases by 1
o	energy decreases by 1
3.	When energy reaches 0, the student becomes inactive.
# Part 2 – Step 1: Create the Model
Create a new GAMA model.
Example:
model classroom_simulation   ![alt text](image.png)
# Part 3 – Step 2: Define the Student Agent
Create a student species.
Example:
species student {

   int energy <- 5;
   int score <- 0;
   string status <- "active";  ![alt text](image-1.png)
# Part 4 – Step 3: Add Behavior (Participation)
Students randomly participate in class.
Example:
reflex participate when: status = "active" {

   if flip(0.4) {
      score <- score + 1;
      energy <- energy - 1;                                          
   }

}
Explanation:
• flip(0.4) means 40% chance of participation. ![alt text](image-2.png)
# Part 5 – Step 4: Add Reflex for Status Update
When energy becomes 0, change the status.
reflex update_status {

   if energy <= 0 {
      status <- "inactive";      ![alt text](image-3.png)
   }

}
# Part 6 – Step 5: Create the Environment
Add the global section.
global {

   init {
      create student number: 20;   
   }

}
# Part 7 – Step 6: Run the Simulation
Observe the following:
•	• Which students participate the most - Students with higher energy levels participate the most because they can sustain activity for more cycles before reaching exhaustion.
• How energy changes over time - Average energy decreases steadily over time, eventually dropping to 0.0 as shown in the monitors.
• When students become inactive - Students become inactive when their energy level hits zero, which has occurred for all 20 students by the cycle takes longer.

# Part 8 – Guide Questions
Answer the following questions.
1.	What happens to students when energy reaches 0? When energy reaches 0, students stop participating, their color changes from blue to red, and they are counted as Inactive Students
2.	How does participation affect score and energy? Higher participation increases the Average Score but causes energy to deplete faster toward 0.0.
3.	If participation probability increases to 0.8, what happens? If participation probability increases to 0.8, students will engage in activities more frequently, leading to a much faster depletion of energy and earlier inactivity.
4.	What pattern do you observe in the simulation? The simulation follows a "resource-depletion" pattern where high initial activity leads to a steady decline in energy until the entire population becomes inactive.






