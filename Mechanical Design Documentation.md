# Design Goals
At the outset of this project we knew that we wanted to create a robot with differential swerve drive that was packaged as close to the same size as a Romi as possible. Due to these two broad constraints our design process started with creating a well-packaged swerve drive module and then nesting the other supporting components. Additionally, as a challenge to ourselves, we decided to design all of our own parts instead of relying on existing solutions (excepting off the shelf electronics components and hardware).
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
### Crayon CAD Confirmation
In order to be sure that our packaging concept would be physically possible, a simplified block-CAD model was created. From this we gained a good understanding of the tolerances we would be working with. 
![[Pasted image 20250506161520.png]]
![[Pasted image 20250506161541.png]]
Bearing clearance confirmation

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
We opted to implement a simple arm lifter for manipulating baskets. The angled comb design was chosen to accommodate baskets with handles of different height without letting them slide up and down the arm.
![[Pasted image 20250506154807.png]]
### Casters
Due to our decision to make a two-module swerve drive we needed casters to maintain balance. Use of ball casters was considered, but omni-wheels were chosen in their place due to their design allowing them to be tucked closer to the frame than equivalent ball casters (and because who doesn't want to design a omni-wheel). Each wheel consists of a 3d-printed frame, two ball bearings, and six casters held in place by bent piano wire. 
The geometry of the wheel was designed to be as thin as possible while maintaining a completely round outer profile.
![[Pasted image 20250506155516.png]]
![[Pasted image 20250506160151.png]]
Four points of contact were needed because the center of gravity could not have been reasonably kept over the base of support with just additionally point of contact past the swerve modules. In order to avoid over constraining the drivetrain one of wheels needed to be able to move. This was accomplished with a compliant flexure on the rear wheel. Two versions were created for different compliances.
![[Pasted image 20250506160838.png]]![[Pasted image 20250506160932.png]]
Finite element analysis was completed on the flexure, but yielded wildly inaccurate results due to the geometry of the part and the variations in material properties of 3d-printing filaments. 
![[Pasted image 20250506161116.png]]
Actual displacement under similar loads was roughly an order of magnitude larger.
