# nickmarcusriley
Computer Python MITapp
Goals

Use velocity with Cartesian x- and y-coordinates
Describe the purpose and concept of abstracting a procedure
Introduce lists and iteration across lists
Describe the role of argument values and return values
 

Introduction

How does animation work? Images can appear to glide across the surface of a painting canvas on the screen. In reality, the screen's image changes discretely, approximately every 30 milliseconds. What is really happening every time the screen is drawn?

In this activity, you will play a game as part of a usability study, in which developers observe users using a program. You will adopt the game as a development team, create a plan to improve it, and complete one sprint.

The principles of game development can be applied to any game. What is a game you'd like to create?

Games can be used to simulate real situations, like birds and bees pollinating flowers. By playing with a simulation, the user can learn about the system being modeled. What is there to learn about birds, bees, and pollination? What is another real situation you might be interested in exploring with a simulation?

Computer programs can have millions of lines of code. This activity's game is only about 100 lines long. On average, a line of computer programming code gets written once and then read by an average of seven people trying to maintain and improve it. What do you suppose you look for first when you start exploring the code of someone else's computer program?

121a.png

 

Materials

Computer with browser
Android device with AI Companion
Google ID
1.2.1 sourceFiles.zip
 

Procedure

Form pairs as directed by your teacher. Meet or greet each other to practice professional skills. Set team norms.
Part I: Explore the program

In your pair, choose one person to be a test user. The other person will play the role of a developer conducting a usability study. Follow the instruction for your role below for 120 seconds. Then switch roles.
Test user: Play bouquet_v1.apk on your Android device. Describe the app's behavior.
Developer: Observe the user using the app. Record your observations.
Which elements of the user interface do they use?
Do they stumble over any element of the user interface?
Did it ever look like they expected one thing to happen while interacting with the interface, but the app didn't respond the way they expected?
An app should suit its purpose. As a game, how well did the app engage the user?
By discussing as a class, identify any additional functionality the app has that you didn't record earlier in step 2a.
What is a usability study? Why do you think it is important? When do you think it should occur in the development cycle?
Now, all team members will be developers. With your partner, create a product backlog for Bouquet. Brainstorm features that a user might want and why. Later, you will pick one of the backlog items and break that item down into tasks for a sprint task list. Your teacher might have the class share ideas.
To get ready to modify the program, examine a high-level description of the program. This description will be provided by your teacher in person or in a document, presentation, or video.
Each stack of App Inventor blocks provides the code for one event handler or for one procedure. These stacks provide chunks of functionality. What are the major chunks of functionality in this program?

Part II: Identify and explain abstractions

A primary purpose of this activity is to understand abstraction. Abstraction is a strategy for handling complexity. An abstraction generalizes something by removing details.

Abstraction helps us solve complex problems. We break apart a big, complex problem into pieces. We solve the small problems, one at a time. We abstract our solutions to the small problems by giving a solution a name. This kind of abstraction is called a procedure or a function, depending on whether it returns a result. By giving that solution a name, we can refer to it to help solve a bigger problems.

The bouquet program creates several abstractions. A programmer can call upon the abstraction by name without worrying about the details implemented in the code. If the procedure depends on some value that might change, we can use a parameter to pass that value to the procedure. When the procedure is called, that parameter becomes a local variable that can only be used inside the procedure because that is the scope of the variable. Practice using the vocabulary based on the pictures of the blocks, using the following example.

121 q6 reset sprite.PNG

Example vocabulary use: The procedure reset_sprite is an abstraction. You can call the procedure reset_sprite. You will have to pass a value for the parameter sprite. The local variable sprite will be created when the procedure is called.

Practice the vocabulary using this picture of the blocks. Note that both parameters become local variables.
 121 q7 handle edge.PNG

Write the previous paragraph, “Example vocabulary use … is called,” using the handle_edge code for procedure and variable names.

 

The procedure ____________________________________________

_________________________________________________________________________________________________________________________

 

Sometimes it is helpful to dig in to the details to understand an abstraction, to make sure the abstraction is correct, or to find vulnerabilities that need to be closed.
For each of the following abstractions, read the summary of the abstraction. Note that parameters are listed in parentheses after the name of a procedure. Then read the code that implements the abstraction. Identify some of the details that are abstracted away. What details are left out of the summary that a programmer doesn't need to worry about when calling the procedure?

The reset_sprite(sprite) procedure moves the sprite to a random location at the top of the screen and resets the image size.
What details are abstracted away?

121aresetsprite.PNG

This answer is provided as an example: When calling the reset_sprite procedure, the programmer doesn't have to worry about details that the name of the procedure reset_sprite(sprite) abstracts. The programmer doesn't have to worry about the fact that the height and width will be reset based on the number of pixels given by the global variable initial_sprite_size. The programmer also doesn't have to worry about how the procedure is setting the new x-coordinate randomly at the top of the screen. The programmer doesn't have to worry about the fact that the leftmost pixel possible has x=0 or that the rightmost pixel possible is the canvas width minus the sprite size.
The handle_edge(sprite, edge) procedure takes an appropriate action for a sprite that has collided with the left, right, or bottom edges. Left and right edges wrap to the other side; the bottom edge resets the sprite at the top.
What details are abstracted?

121 q8b handle_edge.PNG

The enlarge(sprite) procedure makes a sprite a little bigger.
What details are abstracted?

121 q8c enlarge sprite.PNG

In addition to the procedures, the program bouquet creates some abstractions that are functions instead of procedures.
What is the difference between a function and a procedure? How are functions and procedures similar?
The results returned by the get_increment_x and get_increment_y tell how many pixels to move a sprite based upon the forward-backward tilt (pitch) and left-right tilt (roll) of the tablet. What details of the calculation are abstracted by the functions?
121 q9b get increment.PNG

Good code comes with documentation that summarizes the action of procedures. Why do you think it is important for programmers to provide high-level documentation of their code?
Part III: Relate position, velocity, acceleration, and gravity

Mobile computers usually contain a device to measure acceleration. That device is called an accelerometer*. The bouquet program uses the accelerometer to fly the hummingbird based on the tilt of the tablet.
What is the difference between speed* (a scalar*) and velocity* (a vector*)?
What is the difference between velocity and acceleration*?
The figure below shows a tablet laying flat on a desk and shows the orientation of the standard positive x-, y-, and z-axes used in mathematics. (Note: The standard mathematics axes are different than the graphics axes of the tablet. The math axes have y increasing as you go up the page in two dimension or away from you in three dimensions. The tablet graphics are only two dimensions, have a fixed origin at the upper left corner of the window, and have larger y coordinates further down the tablet screen.) Suppose you pick up the tablet and the accelerometer reports acceleration in the positive y and z directions and in the negative x direction. Demonstrate the direction of the acceleration to your partner by pretending you are picking up a tablet from your desk.
121 q11c tablet coordinates xyz.PNG

Run the program acceleration_demo (either AIA or APK) on your tablet. You should see a green circle centered on a bullseye. The x-, y-, and z-components of acceleration are reported on screen. The x- and y-components are shown as pink lines. The z-component is shown as a filled green or red circle. Green indicates z-acceleration toward the screen; red indicates z-acceleration toward the back face. Describe the appearance of the filled circle and the pink lines for each of six positions on the tablet. The first two are done for you.
Screen facing up: When laying on the table, the tablet sensor feels like it is in a rocket ship accelerating 10 m/s2 upward. We see… a green circle of radius 10.
Standing on left edge: When standing on the left edge, the tablet sensor feels like it is in a rocket ship accelerating 10 m/s2 upward. We see… a pink line of length 10 pointing to the right of the tablet.
Standing on right edge: When standing on the table, the tablet sensor feels like it is in a rocket ship accelerating 10 m/s2 upward. We see…
Standing on bottom edge: When standing on the table, the tablet sensor feels like it is in a rocket ship accelerating 10 m/s2 upward. We see…
Standing on top edge: When standing on the table, the tablet sensor feels like it is in a rocket ship accelerating 10 m/s2 upward. We see…
Screen facing down: When laying on the table, the tablet sensor feels like it is in a rocket ship accelerating 10 m/s2 upward. We see…
No matter which way I hold the tablet, if tablet is not accelerating, the total acceleration reported is _______ m/s2.

The acceleration of any object in freefall* near Earth’s surface is 9.8 m/s2 downward, a quantity known as g*. Using the rounded value of 10 m/s2, fill in the table with the velocities of a ball after it is thrown 20 m/s upward.
 

Seconds after being thrown

Velocity

0 seconds

20 m/s upward

1 second

 

2 seconds

 

3 seconds

 

Accelerating in one direction feels identical to being pulled by gravity in the opposite direction. In theory, a rocket ship could make passengers feel like they were on Earth by steadily accelerating away from the “ground” 10 m/s2. For example, a rocket ship could accelerate toward a distant star for the first half of the trip, rotate 180° when it was halfway to the star, and decelerate during the last half of the trip. The following diagrams show the rocket ship during the first half of the trip and the last half of the trip, respectively.
121 q12 rocket rotates.png

Draw an arrow to show the direction of the 10 m/s2 acceleration vector during the two halves of the trip.
Describe what is happening to the speed of an object when velocity and acceleration are in the same direction and what is happening to the speed of an object when these two vectors are in opposite directions.
In the following figure, the tablet has been tilted up from the table, with its left edge still touching the table. Gravity still pulls straight down, and the accelerometer reports perceived acceleration up away from Earth. For the accelerometer device, this is to the right of the tablet (x) and out of the front face of the tablet (z). The green dotted arrows show how the x component and the z component of the vector add up to the perceived acceleration. The length of the arrows is the magnitude of the measurement.
Based on the length of the arrow representing 10 m/s2, estimate the lengths of the x and z acceleration arrows.

121 q14 titled tablet xz.PNG121 q14 vector diagram.PNG

Part IV: Identify a user story and create the solution

Prioritize your backlog so that one or two items you want to work on first are at the top. You might want to refine the top one or two items to be more precise and manageable in the amount of work required to complete them. This is called grooming the backlog. Your teacher might have the class share ideas and select distinct features to work on.
Break the top item or two from the backlog into tasks for a sprint task list.
Prepare to develop the task at the top of your sprint task list.
Authenticate to Google and open the App Inventor 2 development environment in a web browser. Upload the bouquet_v1.AIA file into App Inventor.
You will keep bouquet_v1.AIA as a record of the version you started with, and work on the next version with your improvements. Select Projects > Save project as... and save as bouquet_v2 in a location specified by your teacher.
Discuss and record your plan for accomplishing the first task. Use your engineering notebook or other project documentation as directed by your teacher.
Develop the task at the top of your sprint task list.
So that you can test as you code, launch the AI2 Companion app on your Android device. Connect to the device using Connect > AI Companion.
Decide who will begin as driver and who will begin as navigator. As you work to accomplish the first sprint task, the driver should think out loud and the navigator should provide ideas and ask questions. Switch driver/navigator roles frequently.
As you develop, take the time to record problems you encounter, ideas you tried, results you observed, and reasons why you think an idea doesn't work when you thought it would. A Word document with screenshots of code works well for this purpose.
When you accomplish a task, save the bouquet_v2.AIA version of your program as described in the following step.
To document your development process, save intermediate versions following these steps.
Save the program in the App Inventor website. You won't work on this version any more.
Download the AIA file using Projects > Export the selected project (.aia) to my computer. Save this file in the location specified by your teacher. It documents the progress you made at this stage of development.
In App Inventor, select Projects > Save project as and then use a new name, for example, bouquet_v3.
Continue development using this new version.
In your engineering notebook (or other project documentation as directed by your teacher), record a sentence with each small accomplishment as you develop. After 30 to 60 minutes of progress, download the version the you have created and append a version number to file name you downloaded. Summarize the improvement alongside the name of the AIA file containing the version number.
Repeat steps a through e as many times as needed. End on step c so that, for example, you have documented and downloaded bouquet_v5.AIA and have moved on to bouquet_v6.
Submit the following as directed by your teacher:
Deliverable version of the program at the end of your sprint. Your teacher might direct you to install an APK of your app on one tablet passed around to all the teams.
Project documentation describing your development process
Present your team's work to one or more other teams as directed by your teacher.
*Physics Key Terms

Term	Definition
accelerometer	A device that measures how quickly an object’s velocity is changing
acceleration	The rate at which an object’s velocity is changing
component	A component of a vector is a piece of a vector pointing in a particular direction
freefall	The motion of an object experiencing only gravity—no propulsion, lift, or air resistance
g	The acceleration of an object in freefall near earth’s surface, 9.8 m/s2. The symbol g is used for this quantity in physics formulas, and accelerations are sometimes described in multiples of g, such as “pulling 3g’s”.
scalar	A quantity that has no direction. Compare vector.
speed	The rate at which an object’s position is changing, either at an instant or on average during an interval of time
vector	A quantity that has both an amount and a direction; the opposite of a scalar. A positive or negative sign shows direction in one dimension.
velocity	The combination of an object’s and direction
