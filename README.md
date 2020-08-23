# Draw_A_Ball

![image](https://github.com/bobwzb/Draw_A_Ball/blob/master/images/res.PNG)

This project is mainly about draw a ball on a 2D plane. Usually the ratio of the text is 2:1 so we just set the plane to 80*40.

If we project the ball into the plane, it will just like a simple circle (x^2+y^2<=1). So inside the circle we need to draw the shadow and outside the circle, we just need to fill the background with a character (B).

In order to show the stereoscopy, we need to draw the shadow of the surface of the ball. The normal of unit ball is equal to its position of every points on the surface. So on the xy plane we can it normal by: 

z=√(1-x^2-y^2)

Usually, we use the Lambert model to draw the color:

max(L·N,0)

L is the direction of the light. N is normal. We use the max function is because if the intersection angle is over 90, there won't be light at this point. It may cause the picture is too dark. So we choose to use another sslution here, Half Lambert.

![image](https://github.com/bobwzb/Draw_A_Ball/blob/master/images/half%20lambert.jpg)

(L·N+1)/2

Half Lambert is first used in the Half Life by Valve. This model can increase the degree from 90 to 180, which can make nearly all the surface can be colored.

This time we just choose the L=[ √3/3 , √3/3 , √3/3 ] as the direction of light, which is already normalized. So finally the function we use will be:

(√3/3N+1)/2
