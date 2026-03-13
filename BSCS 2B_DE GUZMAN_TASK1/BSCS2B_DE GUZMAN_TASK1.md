#
PART 1 — Pre-Lab Concept Questions (15 minutes)
Answer the following before running the simulation:
1.	What is an agent in an Agent-Based Model? An encapsulated computer entity that simulates a real-world actor within a defined environment.
2.	What is the difference between:
o	global variables - is accessible by all agents such as observer, with only one value existing for the entire variable.
o	species variables? - belong specifically to a particular agent species has it won unique value fir that variable.
3.	What does this expression mean? 
student mean_of each.attention. 
-referring to the calculated average(mean) attention score for student or maybe referring to        the average of specific student maintained during specidc activity over a period of time.   
4.	What happens if attention continuously decreases without a break? This can cause rapid depletion of cognitive resources, resulting in decreased retention, high error rates.

PART 2 — Run the Base Model 
Step 1
Run the provided model.
![alt text](image.png)

Step 2
Observe:
•	Student movement – Most of it move toward the center and form small groups, while some move away and spread out as it longer the project runs. The movement shows that it interacts and gather while still changing positions in the space.
•	Color changes – it changes it color, red, green and yellow
•	Monitor values - As the simulation runs, the monitor updates to display changes in the students’ movement. This allows the user to observe patterns and understand how the students interact in the environment.

Step 3
Open the generated file: classroom_data.csv
![alt text](image-1.png)  ![alt text](image-2.png)

PART 3 — Data Observation Table
Fill in the table after 100 cycles:
![alt text](image-3.png)

PART 4 — Guided Code Analysis Activity 1: Break Frequency
Original code:
if (cycle mod 30 = 0)

Task:
Change break interval to:
15 cycles

Questions:
1.	Does attention increase faster? Not really. Some are more stable.
2.	Does performance grow faster? Performance may grow slightly faster because attention reaches the required level more often.
3.	Is the system more stable? The system becomes more stable the movement of students looks more observable.

Activity 2: Attention Decay Rate
Original:
attention <- max(0.0, attention - 0.02);

Task:
Change decay rate to:
0.05

Observe:
•	Does attention collapse? Yes, attention decreases much faster because the decay rate is higher
Does performance still improve? Explain why. Performance improves less often because students lose attention quickly and students should have stable attention level to increase performance.

  
Activity 3: Performance Growth Condition
Original:
if (attention > 0.6)

Task:
Change threshold to:
0.8

Questions:
•	Does performance improve slower? Yes. Fewer students reach the higher attention threshold, so performance increases more slowly.
•	What does this represent in real classroom settings? It represents that students need very high focus before their learning performance improves.

PART 5 — Experiment: Class Size Impact (30 minutes)
Use parameter:
Initial number of students Test:
![alt text](image-4.png)

Analysis Questions:
1.	Does increasing class size affect average attention? Yes. Larger classes usually reduce average attention because there are more students moving and interacting.
2.	Does mobility create more randomness? Yes. Student movement causes more unpredictable behavior in the simulation.
3.	Is emergent behavior visible? Yes. Patterns such as clustering or varying attention levels appear naturally from student interactions.

PART 6 — Data Analysis Task (Optional Python)
Using Excel or Power Query Editor
1.	Load classroom_data.csv
2.	Plot: 
o	Attention vs Cycle
o	Performance vs Cycle
![alt text](image-7.png)
3.	Identify break cycles. They happen consistently and frequently across the entire chart, showing a repeating pattern of focus followed by a quick reset.
4.	Compute correlation between attention and performance. There is no real connection between the two. While attention (blue) keeps jumping up and down, performance (orange) stays perfectly steady at the top. This means the drops in attention do not hurt the performance at all.

Question:
Is performance strongly dependent on attention? Yes. Performance increases only when attention passes a certain level, showing a strong relationship between the two variables.

PART 7 — Critical Thinking Questions
1.	Why does performance only increase when attention > 0.6? Because students need a certain level of focus before learning improves.
2.	Is this model deterministic or stochastic? It is stochastic because random values (like mobility and attention) affect the simulation.
3.	What real-world classroom factors are missing? Teacher interaction, Student collaboration, Classroom, Different learning of Student.
4.	How would peer influence affect the system? Students with high attention could help nearby students improve their focus.

PART 8 — Advanced Extension Tasks (Choose One) 
Option A: Peer Influence
Add logic:
•	Students near high-attention peers increase attention.
![alt text](image-8.png)

code:![alt text](image-9.png)
By adding the peer_influence enable agent-to-agent interaction. The code doesn't just look at global variables; it commands the student species to "look" at its neighbors' internal variables, creating a complex social system where the behavior of one individual directly modifies the attributes of another.









