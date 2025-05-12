# 🤖 Lego Robot Controlled by DE1-SoC and Nios V Processor

This project builds a Moving and Dancing Lego Robot with DC Motors, Light Distance Sensors, and controlled using the UofT Lego Controller attached to the DE1-SoC and Nios V Processor. The robot moves forward, back, left and right, controlled using the key pushbuttons on the DE1-SoC board and also dances with programmed moves to background music, played on the Audio Speakers integrated with the system. The system also uses a VGA Display to interface the robot’s movement, leaving a trail every time the robot moves creating a drawing effect and also having a short animation while the robot is dancing.

## High Level Overview

## Functionality

This robot is controlled using the four pushbuttons available on the DE1-SoC board. Each button triggers a specific motor control operation by interacting with GPIO, audio, and VGA buffers.

### 🔘 Button Controls
- Key 0 – Move Forward
  Activates the robot’s motors in a clockwise direction, propelling it forward. Achieved by writing to the GPIO buffers.

- Key 1 – Move Backward
  Activates the motors in a counter-clockwise direction to drive the robot backward. Also handled via GPIO buffer writes.

- Key 2 – Rotate
  Enables the left and right motors to rotate in opposite directions simultaneously, allowing the robot to spin in place.

- Key 3 – Dance Mode
  Initiates a series of pre-programmed movements and spins. Between moves, the system:

  - Adds delays for synchronization
  - Plays audio by writing to audio buffers
  - Updates the VGA display through VGA buffers
  - This creates a coordinated visual and auditory performance.

### ⚖️ Self-Balancing Mode
When no button is pressed, the robot enters Self-Balancing Mode, where:

- Light sensors connected via GPIO are read continuously.

- Pulse Width Modulation (PWM) is used to make fine motor adjustments for maintaining balance.

- The robot actively corrects its orientation to stay upright.


