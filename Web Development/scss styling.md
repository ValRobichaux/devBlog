# SCSS Troubles

I was having a lot of trouble figuring out how to get my png spacing correct on my website because it was leaving a lot of white space on the bottom of the image.

```scss
> *{
    width: 100vw;
    height: calc(100vh - 70px);
    scroll-snap-align: start;
            
}
```

Here `vh` means the viewport height of the viewable screen height.

so I have to adjust my viewport here to account for the top nav bar that I have set earlier

```scss
     .sections {
        width: 100%;
        height: calc(100vh - 70px);
        background-color:lightcoral;
        position: relative;
        top: 70px;
```

Now trying to fix the white space at the bottom of my PNG and seeing if its a picture resolution size or scss sizing problem...

-------------------------------
The solution : 

My main issue I was having was my conatiner that I placed the image in was not the same size as the webpage so I was not getting my desired look on the page.

```scss
.intro{
    background: white;
    display: flex;

    .left{
        flex: 0.5;
        overflow: hidden;

        .imageContainer {
            width: 1200px;
            height: calc(100vh - 70px);
            background-color: rgb(79, 126, 226);
            border-radius: 60%;
            display: flex;
            align-items: flex-end;
            justify-content: center;
            float: right;
        
            img {
                height: 115%;    
                width: 115%;
                transform: scaleX(-1);
                border: hidden;
            }
            
        }
    }
```

The important thing here was that I calculated the height of my container to match the height of the section.

Next was just fiddling around with positioning in the `img`

Fun trick I used was `transform scaleX(-1)` in order to mirror the image since I was a bit leaned over in one direction in my original pic.

## Using animations

I started implementing animations for certain images on my page to give it a more alive feel to my page such as animating this small arrow bouncing.

``` scss 

            img {
                width: 80px;
                animation: arrowBounce 2s infinite;
            }

            @keyframes arrowBounce {
                0%, 20%, 50%, 80%, 100% {
                  transform: translateY(0);
                }
                40% {
                  transform: translateY(-30px);
                }
                60% {
                  transform: translateY(-15px);
                }
              }

```

the percentage values are used to separate the frames of the arrow and how it's going to be animated.

This allows us to specifically time movements to get the smoothest outcome.