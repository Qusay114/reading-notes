# Transform :
In css3 came new ways to position and alter elements , and one of them is transform property which is can take a lot of values , some of them :

        * transform:rotate(20deg);       //here it will rotate the element 20 degree clockwise, while if we used negative value it will rotate counter clockwise 

        * transform:scaleX(2);	         //here it will scale the width of the element 2 times
        * transform:scaleY(3);	         //here it will scale the height of the element 3 times
        * transform:scale(2,3); 


        * transform:translateX(10px);	 //it will push the element to the right 10px
        * transform:translateY(100px);	 //it will push the element down 100px
        * transform:translate(10px,100px);

        * transform:skewX(20deg);	     //it will distort the element 20 degree on the horizntal axis
        * transform:skewY(40deg);	     //it will distort the element 40 degree on the vertical axis




we can also combine the values of the transform , Example:

        .box
        {
            transform: rotate(20deg) scaleX(2) translateY(25px) skew(5deg, 10deg) ;
        }


As we know the transform take the origin as the center of the element , but we can change the origin using :

transform-origin: 0 0 or 80% 30% or top right or 30px 80px ;



# Transition :
We can animate our elements using transition property , here are some of the realted properties :

        * transition-property:background; 	//here to set the property(background) to make the transition on it .

        * transition-duration:3s; 		//here to set the duration(3 seconds) of the transition .

        * transition-timing-function:linear ; 	//here to determine the transition moving (constant) .

        * transition-delay: 4s ; 		//here to determine the delay(4 second) before the transtion happens .
