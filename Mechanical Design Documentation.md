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
From Jacob Williams' design we drew inspiration for o-ring wheels. From the Wild Willy Robotics model we were inspired by the overall bevel gear arrangement and use of v-groove bearings. From the third design we learned that no matter what simple robotics platform a class uses, someone will make a diffy swerve alternative.
Additionally, one feature that we identified as missing from these existing designs was an encoder to know the angle of the wheels without having to complete a homing sequence using limit switches.
## Gearing Arrangement

## Gearing Considerations
As a design consideration we hoped to achieve a linear speed of 1 to 2 times the speed of a Romi. We also determined that the generally accepted range for twist speed is between 100 and 200 rpm.
One interesting challenge that we had to account for was the fact that packaging constraints allowed for only a certain range of tooth counts. Our first round of calculations is as follows.
![[Drivetrain Speed Calculations]]
## Design Choices
### Swerve Module
Our design revolves around a central hub that contains the wheel connected to two large bevel gears. 
![[Pasted image 20250506021302.png]]
These three moving components are held in place by a central hub that itself can spin. By rotating the large bevel gears in the same or opposite directions, the assembly can turn or spin the wheel respectively. This hub additionally has a top frame which holds the magnet for the magnetic encoder.
![[Pasted image 20250506021351.png]]
In order to constrain the bevel gears we employed v-groove bearings and a matching feature on the bevel gear.
![[Pasted image 20250506021433.png]]
This assembly is held in place with a set of 7 to 10 regular ball bearings stacked above and below a lip on the hub. The design has spaces for 10 bearings, but we found that using fewer bearings on the bottom side resulted in much lower resistance to spinning. This method was employed instead of v-groove bearings because it was significantly more resistant to axial loads. 
![[Pasted image 20250506124521.png]]
Power is transferred to the large bevel gears through two motor shafts with pinions at different heights.
![[Pasted image 20250506124746.png]]
A frame consisting of a top-plate, mid-plate, and bottom-plate was created to hold everything together. The top plate mounts motors and the encoder mount. The mid-plate constrains the bearings for the main hub, and the bottom-plate supports the end of the motor shafts with thin-wall bearings and grub screws (used instead of bolts to avoid using up valuable ground clearance). One improvement that could be made in future iterations would be to make separate motor mounts that screw in from the top, as it is currently necessary to disassemble the modules in order to replace them.
Three versions of electronics mounts were designed. Firstly, a development encoder mount was designed to mount an AS5600 breakout board for testing without a complete control board.
![[Pasted image 20250506153958.png]]
The second version was to implement the custom control boards. 
![[Pasted image 20250506154139.png]]
The third version designed was the best.
![[Pasted image 20250506154311.png]]
### Lifter


