<link rel="stylesheet" href="assets/custom.css">
<title>shadows on a flat earth</title>

# Shadow Model
*A project by [Alan Ma](https://alan-ma.me)*  
**The initial problem:** Model the shadow length of a building on a flat Earth, assuming that rays from the Sun are all parallel (and not radial).

## Solution: First Edition
I started out with a graphical interpretation of the scenario:  
| *the flat-earth, point-sun model* |
| :-: |
| ![shadow model 1 - graphical representation](assets/shadow-model-1.png) |

I wanted to create a model that was flexible enough to allow parameters – a variable building position and height, as well as a variable radius of the sun.
With these parameters, I defined a few variables and gave a more concrete model.

$let \ point \ O \ be \ the \ origin \ of \ the \ Sun \ at \ (0,0)$  
$let \ point \ B \ be \ the \ tip \ of \ the \ building \ at \ (h,k)$  
$let \ point \ E_b \ be \ the \ bottom \ of the \ building \ at \ (h,0)$  
$let \ the \ point \ at \ which \ the \ shadow \ hits \ the \ ground \ be \ E_s \ at \ (E_{sx},0)$  
$let \ the \ sun \ be \ at \ point \ S \ which \ revolves \ around \ a \ circle \ with \ origin \ O \ and \ radius \ r.$  
$let \ the \ angle \ the \ Sun \ is \ above \ the \ horizon \ be \ \theta$
$let \ the \ length \ of \ the \ shadow \ be \ L$

We know that the coordinates of S are dependant on $\theta$ and are equal to $(rcos\theta,rsin\theta)$.  
The model would then be:  
| *the model with variables* |
| :-: |
| ![shadow model 2 - graphical representation](assets/shadow-model-2.png) |

The value that we are looking for is $E_{sx}$. I found this with a 2-step process:  
1. Find the equation of the the line passing through points $E$ and $B$.
2. Substitute $y=0$ into the equation to find the x-intercept – this will be $E_{sx}$.
3. Use the values of $E_{sx}$ and $h$ to find the shadow length $L$.

**Step 1**  
Equation of a line using points:  
$\frac{ y - y_1 }{ y_2 - y_1 } = \frac{ x - x_1 }{ x_2 - x_1 }$   
$x = \frac{ (y - y_1)(x_2 - x_1) }{ y_2 - y_1 } + x_1$  
Use this equation for $\overline{BS}$:  
$x = \frac{ (y - k)(rcos\theta - h) }{ rsin\theta - k } + h$  
**Step 2**  
Substituting in $y=0$ yeilds the following:  
$x = \frac{ -k(rcos\theta - h) }{ rsin\theta - k } + h$  
$x = \frac{ -krcos\theta + hk + hrsin\theta - hk }{ rsin\theta - k }$  
$x = \frac{ -krcos\theta + hrsin\theta }{ rsin\theta - k }$  
Thus, $E_{sx} = \frac{ -krcos\theta + hrsin\theta }{ rsin\theta - k }$  
**Step 3**  
The shadow length is equal to the position of the building minus the position of the shadow of the ground. Since lengths are always positive, the absolute value of the result is taken.  
$L = \lvert h - E_{sx} \rvert$  
$L = \lvert \frac{ krcos\theta - hrsin\theta }{ k - rsin\theta } + h \rvert$  

