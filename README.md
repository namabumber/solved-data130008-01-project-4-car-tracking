Download Link: https://assignmentchef.com/product/solved-data130008-01-project-4-car-tracking
<br>
This (and every) assignment has a written part and a programming part.

The full assignment our supporting and scripts Can be downloaded as car.Zip.

This icon means a written answer is expected car. pdf.

This icon means you shOLAd write code in submi ssion. py.

written answers must in order and clearly and correctly to receive credit.

Should modify the in ss i py between

but you can add other t-•elper functions outside this block if you want. Do not make changes to Res other than submi ss i on. py.

Your code will be evaluated on two types of test cases, basic and hidden, which you can see in grader. py. Basic tests, which are

to you, do not stress your code with large inputs or tricky corner cases. Hidden tests are more complex and do stress your code. The i

hidden tests are provided in grader. py, but the correct outputs are not. To run the tests, you will need to have gradertlti I. py in th

directory as your code and grader. py. Then, you Can run all the tests by typing




‘is (and every) assignment has a written part and a programming part.

full assignment our supporting and scripts Can be downloaded as car.Zip.

This icon means a written answer is expected car. pdf.

This icon means you shOLAd write code in submi ssion. py. written answers must in order and clearly and correctly to receive credit.should modify the in submi ssion. py between ‘t you can add other t-•elper functions outside this block if you want. Do not make changes to Res other than submi ss i on. py. code will be evaluated on two types of test cases, basic and hidden, which you can see in grader. py. Basic tests, which are fully providedyou, do not stress your code with large inputs or tricky corner cases. Hidden tests are more complex and do stress your code. The inputs Ofsudden tests are provided in grader. py, but the correct outputs are not. To run the tests, you will need to have gradertlt i I. py in the same

and grader. py. Then, you Can run all the tests by typing

python grader. PY

‘is will tell you only whether you passed the basic tests. On the hidden tests, the script will alert you if your code takes long or crashes, but not say whether you got the correct Output. You can also run a single test (eg., 3a—O-has i c) by typing

grader. py

strongly encmjrage y.ÄJ to read and understand the test cases, create your own test cases, and not just blindly run grader. py.

‘is assignment is a version Of the Car assignment written by Chris

This assignment is a version Of the Car assignment written by Chris

A Study by Work’ Health Organization found that kill a Shocking I .24

million people a year worldwide. In response. there has been great interest in developing

autonomous driving technology that Can drive calculated precision and this

death toll. Building an autonomous driving system is an increddy convex endeavor. In

this assignment, you will focus on the sensing system. which allows us to track other

Cars based on noisy Sensor

Getting started. You will be running two files in this assignment – grader.py and drive.py.

grader.py runs on Python 3 as usual. but drive.py is not

used for any grading purposes. ifs just there to visualize the code you wil be writing and

help you gain an for how different approaches result in different behaviors

(and to have fun’). Let’s start by trying to drive manually. Note again that you need to run

drive, py usjng Python2.

drive. p

You can steer by either using the arrow keys or W. and The up key and W accelerates your car forward. the left key and •a’ turns the

steering wheel to the left. and the right key and ‘d’ turns the steering wheel to the right. Note that you cannot reverse the car or turn in place. Quit

by pressing Your goal is to drive from the start to finish (the green box) without getting in an accident. How well can you do on the windy

Lombard Street Without the location Of Other cars? Don’t Worry if not very good; the teaching Staff Were only to get to the finish

line 4/10 times. An accident rate of 60% is pretty abysmal, which why we’re going to use Al to do this.

Hags for python drive. py:

—a: Enable (as to manual).

• —i (inference method): Use none. exact Inference.

Of the Other Cars.

Use this map (e.g. small or Iombard). Defaults to snal I.

• Debug by all the Cars on the map.

—p: All other cars remain parked (SO that they don’t move).

Modeling car locations. We assume that the world is a twcrdimensional rectangular grid on which your car and K other cars reside. At each time

p your car gets a noisy estimate of the distance to each of the cars.’ a simplifying assumption. we assume that each of the K Other cars car independently (notationally. we assume there is just one other car).

At each time step t let Ct R 2 be a pair of coordinates representing the actual bc.atk:m of the sin* other car (which is unobserved). We assume

there is local distribution Ct_l) which governs be your Cars position, you Observe and

also control. To minimize costs. we use a simple sensing system based on a microphone. The microphone provides us with Dt. which is a

Gaussian random With mean equal to the true distance between the Other Car and (in the code, is

Const. SONAR_STD. which is about two-thirds the length of a car). In symbols.

D, N M(llat –

Fcy exanWe, if your car is at at = (l, 3) and the other car is at Ct (4, 7) , then the actual distance is 5 and Dt might be 4.6 or 5.2, etc. use

util. pdf(mean, std, value)

to compute the probability density function (PDF) Of a Gaussian With given and Standard deviation

st d. evaluated at val ue. Note that evaluating a PDF at a certain value does not retum a probability densities can exceed I but for the

puTx»ses Of this assignment, you Can get away With treating it like a probability The Gaussian density function for the noisy

observation Dt, which is centered around your distance to the car llat — Ctll . is shown in the fdlowing figure:

True distance (t)

from the tile to your

o = const.SONAR_STD

Value Of d

Your job is to implement a car tracker that (approximately) computes the posterior distribution P(Ct DI dl , … , Dt dt) (your beliefs of

Where the Other Car is) and update it each = 1, 2, _ We Will take Care Of using this information to actually drive the Car (i.e., Set at a

collision with ct). so you don’t have to w«ry about that part.

(row, Col) pairs, row &lt; numRowsandO col &lt;

To simpbfy things. we wil discretize the world into tiles represented by

s. tile, We Skye a probability representing our that a Car on that tile. The values Can accessed by:

self. bel ief. getProb (row, Col). Toconvertfromatiletoalocatbn.use util. rowToY (roa)

and util. colToX(coI).

an overview of the ass.gnrnent components:

• Problem I (written) will give you practice with probabilistic inference on a simple Bayesian network.

• In Problems 2 and 3 (code). wil implement Exact Inference, which computes a full probability of another cars location

over tiles

• In Problem 4 (code). you win implement ParticleFi I ter. which works with particle-based representation of this same distribution.

A few important notes before we get started:

Past experience suggests that this will be one Of the most conceptually challenging assignnW1ts Of the quarter for many students. Please Your job is to implement a car tracker that (approximately) computes the posterior distribution P(Ct DI dl, … , Dt dt) (your beliefs of

Where the Other Car is) and update it each = 1, 2, _ We Will take Care Of using this information to actually drive the Car (i.e., Set at to a

collision with ct). so you don’t have to w«ry about that part.

To simplify things. we will discretizetheworld into tiles represented by (row. Col) pairs, where O row &lt; numRowsandO col &lt;

s. each tile, We Skye a probability representing our that a Car on that tile. The values Can accessed by:

self. belief. getProb(rcm, Col). util. rowToY (roa)

and util. colToX(coI).

an overview of the ass.gnrnent components:

Problem I (written) will give you practice with probabilistic inference on a simple Bayesian network.

• In Problems 2 and 3 (code). wil implement Exact Inference, which computes a full probabdity of another cars location over tiles ( row, Col).

• In Problem 4 (code). you win implement ParticleFi I ter. which works with particle-based representation of this same distribution.

A few important notes before we get started:

• Past experience suggests that this will be one of the most conceptually challenging Of the quarter for many students. Please start early, especially if you’re low late days!

• We strongly recommend that you attend/watch the lectures on Bayesian networks and HMMS before getting Started. and keep the slides

handy reference While working,

• The code portions of this assignment are short and straightforward —no more than about 30 lines in total—but only if your understanding of

the smiability concepts is dear! (If not. see the previous point.

• As a notational reminder: we use the lowercase expressions or p(rly) for loca cmditional probability distributions, which are defined

by the Bayesian We use the uppercase P (X = or P (X for joint and posterior probability

distributions, which are not pre-defined in the Bayesian network but can be computed by probabilistic inference. Please review the ecture

Slides for more details.

• As mentioned at the start of the assignment, renwmt»rtorun dri ve. py with Python 2. Note that drive.pyisntused for grading purposes.

Problem 1: Bayesian network basics

First. let us look at a simplified version of the car tracking problem. For this problem only. let Ct {O, I} be the actual location of the car we wish

to Observe at time Step t E {l, 2, 3) . Let Dt E 1} be a sensor reading for the location Of that measured at time t. Here’s What the

Bayesian network (ifs an HMM, in fact) h•oks like:

102

The distribution over the initial car distribution is uniform; that is. for each value {O, I}:

p(cl) 0.5. ifct

p(ct ct-l) =

local conditional the noise in the Sensor (With probability reports Wrong positim).

if dt et

p(dt ct) =

I — n if dt=ct.

you Will be asked to find the posterior the at the Step given different Sensor readings.

mportant: For the following computations. to’ to follow the general strategy described in lecture (marginalize non-ancestral variables. conditiM1.

Try to delay the Very end YOull get than trying to Chug lots Of equations.

C.

Suppose we have a sensor reading for the second timestep, 102 O. Compute the posterior distribution P(C2 I I “2 O)

We encourage you to draw out the (factor) graph,

Suppose a time step has elapsed and we got another sensor reading, 103 I , but we are still interested in Compute the

posterior distribution P(C2 I 1.)2 = = l) . The resulting expression might be We

you to draw out the (factor) graph.

Suppose e = 0.1 and 0.2.

Compute and compare the probabilities P(C2 I O) I O, I) Give numbers. round

answer to 4 digits.

ii. How did adding the second sensor reading D3 = I change the result? Explain your intuition for why this Change makes

Sense in terms Of the Car and Sensor

iii. What would you have to set e to be while keeping = 0.2 so that

p (C2 = 1 02 = = 1 = = 1) ? Explain Car

the o bservations.

Problem 2: Emission probabilities

n this problem, we assume that the Other car is stationary (e.g.. Ct Ct—l for all time Steps t). You wil implement a function observe that upon observing a new distance measurement Dt = dt updates the current posterior probability from

We have rnultiplied the emission I Ct ) described earlier under •Modeling Car The Current posterior probability iii. What would you have to set to be while keeping = 0.2 so that

p(C2 = I 02 = 1 = = 1) ? Explain Car

the o bservations.

Problem 2: Emission probabilities

In this problem. we assume that the Other car is stationary (e.g.. Ct Ct. 1 for all time Steps t). You wil implement a function observe that upon observing a new distance measurement Dt = dt updates the current posterior probability from Where We have the emission p(dt Ct) described earlier under Car The Current posterior is stored as self. bel ier in Exactlnrerence.

1

method in the Exact Inference class Of subni ssi on. py. This method should sel f. be I i ef in

Fill in the observe

place to update the posterior Of each tile given the Observed distance to the Other Car. After you

Should be able to find the Stationary car by driving around it (using the fiag —p means cars don’t move); You can Start driving with exact inference now. Remember to use Pythat 2 when running drive.py.

pytlmn drive. py —a —p —d —k I —i exact Inference

You can also turn Off -a to drive manually.

t’s generally best to run dri ve. py your local machine. but if you do decide to run it on cardinal/rice itstead. please ssh into the farmshare machines with either the •X or -Y option in order to get the graphical interface; otherwise, you will get some display error message. Note. do expect this graphical interface to be a bit slow, . dri ve. py is not used for grading. but is just there for you to visualize and enjoy the game!

• Read through the codein util.pyforthe fiel i ef class before you get started… you’ll need to use this class for several of the code tasksin

this assignment.

• Remember to normalize the posterior probability after you update it. (There’s a useful function for this in util.py).

• On the small map, the autonomous driver will sometimes drive in circles around the middle before heading target area. In

general. don’t worry too much about the precise path the car takes. Instead, focus on whether your car tracker correctly infers the location

Of other cars.

Don’t if your Car crashes in a While! do happen, Whether you are human Al However, even if there Was an accident. your driver should have been aware that there was a hOh probability that another car was in the area.

Problem 3: Transition probabilities

Now. lets consider the case where the other car is moving according to transition probabilities p(ct+l I ct). We have provided the transition probabilities self. transprob. Specifically. sel f. le, newTi 10) ) isthe probability of the othercar being

neu•TiIe

at time Step + 1 given that it Was in O ldTi Step

In this part, you will implement a function el apseTirne that updates the probability about the location Of the car at a current time to the next Step t •k the same Via the recurrence:

Again, the posterior probability is stored as self. bel i ef Exac t Inference.

elapseTirne

Finish t by the

When you are all done, be to track a moving car well enough to drive by running the following. Remember to run drive_py using Python 2.

python drive, py —k You can also drive autonomously in the presence Of more than one car:

pytium driu• p

Can drive down Lombard:

python drilepy —a —d —k 3 —i enwtlnference —l

Remember to use Pyttu»n 2 for running drive.py. On Lombard, the autonotnous driver may attempt to drive up and down the street before

heading towards the target area. Again. focus on the car tracking component. instead of the actual driving.

Problem 4: Particle filtering

Though exact inference works well for the small maps. it wastes a lot of effort computing probabilities for every available Ole. even for tiles that are

unlikely to have a car on them. We can seve this problem using a particle filter. LJJXfates to the particle filter have complexity that’s linear in the

number of particles. rather than linear in the number of tiles.

For a great cmceptual of how particle filtering works, check out this video on using particle filtering to estimate an airplane’s altitude.

In this two Short but important methods for the Part i i I ter dass in SS ion. py_ When finished, your code should be aNe to track cars nearty as effectively as it does with exact inference.

a Some Of the code has been provided for you. For example, the particles have already been initialized randomly. You need to fill in the observe and o lapseTime functions. These should modify self. part icl es. which is a map from tiles (row.) to Of existing at that tile, i ef, Which needs to be updated re-sample

the partide Itxations.

You should use the same transition probabilities as in exact nference. The belief distribution generated by a particle filter is expected to 100k noisier

compared to the one Obtained by exact inference. Remember to run With Python 2.

python drive. py —a —i particleFilto•r —l

To debug. you might want start with the parked car nag and the display car nag ed).


