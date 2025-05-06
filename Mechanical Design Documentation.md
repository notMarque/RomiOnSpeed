# Design Goals
At the outset of this project we knew that we wanted to create a robot with differential swerve drive that was packaged as close to the same size as a Romi as possible. Due to these two broad constraints our design process started with creating a well-packaged swerve drive module and then nesting the other supporting components.
# Swerve Module
## Research 
When researching existing solutions for small form factor differential swerve drives we were able to find three main designs.
![[Pasted image 20250506014508.png]]
[Jacob Williams](https://www.printables.com/model/950641-xrp-differential-swerve-drive-robot)
![[Pasted image 20250506014532.png]]
[Wild Willy Robotics](https://www.thingiverse.com/thing:5579384)
![[Pasted image 20250506014714.png]]
[Wild Willy Robotics XRP](https://www.printables.com/model/951372-omnidirectional-xrp-robot)
From Jacob Williams design we drew inspiration for o-ring wheels. From the Wild Willy Robotics model we were inspired by the overall bevel gear arrangement and use of v-groove bearings.
Additionally, one feature that we identified as missing from these existing designs was an encoder to know the angle of the wheels without having to complete a homing sequence using limit switches.
## Gearing Considerations
As a design consideration we hoped to achieve a linear speed of 1 to 2 times the speed of a Romi. We also determined that the generally accepted range for twist speed is between 100 and 200 rpm.

