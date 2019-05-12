# ESE 350 Group 14 Blog
## Final Demo Video
Link - https://www.youtube.com/watch?v=NKJDuv7oGUY

## Public Demo Day
05/09/19

![image](Smile.JPG)![image](Frown.JPG)


On Public Demo Day we finally closed the loop and got our camera integrated into our project. We used OpenCV with an API to achieve smile detection with our camera, that wrote whether or not a smile was detected to a .txt in our Final Project folder. We were then able to check in our c code whether a smile had been detected or not and use that information to determine the image that was displayed on our screen. If a smile was detected our screen would display a smile(pictured left), and if not it would display a frown(pictured right). With that we had finally reached our reach goal of integrating the camera in an interactive way into our system! 

## Class Demo Day
05/04/19

![image](1.JPG)![image](2.JPG)![image](3.JPG)![image](4.JPG)

For the class demo we were able to finally get our project working, finally able to successfully display configured patterns and designs on our wodden tile screen. In order to communicate the picture information to our servos, we used a 2d array(this is the 2d array for the images pictured above), 
```markdown
int boxbox[12][14] = {  
   {2500, 2500, 2500, 2500, 2500, 2500, 2500, 2500, 2500, 2500, 2500, 2500, 2500, 2500} , 
   {2500, 2500, blck, blck, blck, blck, blck, blck, blck, blck, blck, blck, blck, 2500} , 
   {2500, 2500, blck, 2500, 2500, 2500, 2500, 2500, 2500, 2500, 2500, 2500, blck, 2500} , 
   {2500, 2500, blck, 2500, 2500, 2500, 2500, 2500, 2500, 2500, 2500, 2500, blck, 2500} , 
   {2500, 2500, blck, 2500, 2500, blck, blck, blck, blck, blck, 2500, 2500, blck, 2500} , 
   {2500, 2500, blck, 2500, 2500, blck, 2500, 2500, 2500, blck, 2500, 2500, blck, 2500} , 
   {2500, 2500, blck, 2500, 2500, blck, 2500, 2500, 2500, blck, 2500, 2500, blck, 2500} , 
   {2500, 2500, blck, 2500, 2500, blck, blck, blck, blck, blck, 2500, 2500, blck, 2500} , 
   {2500, 2500, blck, 2500, 2500, 2500, 2500, 2500, 2500, 2500, 2500, 2500, blck, 2500} , 
   {2500, 2500, blck, 2500, 2500, 2500, 2500, 2500, 2500, 2500, 2500, 2500, blck, 2500} , 
   {2500, 2500, blck, blck, blck, blck, blck, blck, blck, blck, blck, blck, blck, 2500} , 
   {2500, 2500, 2500, 2500, 2500, 2500, 2500, 2500, 2500, 2500, 2500, 2500, 2500, 2500} , 
}
;
```
and in the code we go through column by column, telling the servos how much to move and in what positions to create the image. Between calls to the column we had the stepper motor move a fixed distance to the next column using the following code:
```markdown
      for(int i =0; i < 12; i++){
         for(int j = 0; j < 14; j++){
	          gpioServo(j+2, smiley[i][j]);  //print one column of the image
            usleep(10000);
	       }
	       sleep(1);
         
	        for(int k =0; k < 14; k++){
	          gpioServo(k+2, 2500);         //reset each servo
	          usleep(10000);
         }
         sleep(1);
	       stepperRight(4018);              //move the stepper motor over to the next column
	       sleep(1);
      }
      stepperLeft(45025);                 //move back to the starting image once all the columns are complete
```
In this way we finally achieved our initial dream of creating a functioning tile display screen. We were also able to take photos with our camera, but hadn't integrated it into the program.
## Week 4 - building 
April 28th
## Week 3 - building 
April 21st
## Week 2 - building 
April 14th
## Week 1 - testing out viability of electromagnet
April 7th



### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown

```
