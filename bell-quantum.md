# Bell's inequality violation or the failure of classical determinism
Today, Alice and Bob decided to go to the Science museum to test a new public experiment proving the failure of the classical description of the world in favor of the quantum description.
They have heard about quantum superposition for a long time, for example in  Schrödinger's cat experiment where the cat in the box is neither (or both) dead or alive according to quantum mechanics. What a piece of shit, Bob has always thought. Theses physicists are completely crazy, such a thing is completely non sense. How could you assert, or check that the cat is in a superposition of state before one opens the box ?

But now this experiment at the museum claims to offer a chance to any pair of guys to check by themselves that the world cannot be classical.

Alice and Bob arrive at the experiment place. There are two black boxes located far from one another, with one seat in front of each one. Alice goes to the left one, and Bob to the right one. Each black box has one input (a switch) which is 1 or -1, and one output which is 1 or -1.

They agree to take part in the experiment for five minutes. The experiment starts.

Every second, they choose simultaneously a random input 1 or -1, and they write down the output given by the black box. At the end of the experiment they compare the outputs. They compute the products of their outputs for each time. Then they separte their data into 4 categories :
* The times when Alice chose the input $$1$$ and Bob chose the input $$1$$. 
* The times when Alice chose the input $$1$$ and Bob chose the input $$-1$$. 
* The times when Alice chose the input $$-1$$ and Bob chose the input $$-1$$. 
* The times when Alice chose the input $$-1$$ and Bob chose the input $$1$$. 

For each category, they compute the average of the product of their outputs. 
### Small example
This is a small example to explain the previous sentence.

Here is the outputs Alice and Bob got for each time when they both chose +1 as inputs.

| A | B |
|---:|---:|
|-1 | 1 |
| 1 | 1 |
|-1 | 1 |
|-1 |-1 |
|-1 |-1 |
| 1 | -1 |

They compute the products of the output for each time
| A | B | AB |
|---:|---:|----:|
|-1 | 1 | -1 |
| 1 | 1 |  1 |
|-1 | 1 | -1 |
|-1 |-1 | -1 |
|-1 |-1 |  1 |
| 1 |-1 | -1 |

Now they compute the average : this gives a number between -1 and +1 (here, this gives $$u_{++}=-\frac{1}{3}$$)
### End of example
We note
* $$u_{++}$$ the computed average for the first category,
* $$u_{+-}$$ the computed average for the second category,
* $$u_{-+}$$ the computed average for the third category,
* $$u_{--}$$ the computed average for the fourth category,

Now they compute $$u_{++}+u_{+-}+u_{-+}-u_{--}$$. They find a number which is bigger than 2. A panel explains that if the world were classical they could not find a number bigger than 2.

Bob is disappointed : he expected to see a Schrödinger's cat, and this experiment is just about computing numbers. So boring!
While Bob complains, Alice reads the panels that explain why this should be so.
## Why classical picture predicts less than 2
Let us model this as a random experiment. Here, an experiment is what happens every second : a choice of inputs, leading to outputs.
* The internal initial state of Alice's black box (ie the state of Alice's black box just before Alice or Bob sets the input)  is a random variable $$s_a$$. For example, $$s_a$$ may be the positions and speeds of all the particles inside the black box.
* the internal initial state of Bob's black box is a random variable $$s_b$$ 
* The input chosen by Alice is a random variable $$i_a$$ which is $$1$$ or $$-1$$
* The input chosen by Bob is a random variable $$i_b$$ which is $$1$$ or $$-1$$

Note that here, we are not assuming that one is able to know exactly the internal states of the black boxes.

#### Assumptions
(HI) We assume that the choice of inputs $$i_a$$ and $$i_b$$ are independent of the initial states $$s_a$$ and $$s_b$$. 

We assume that the output of Alice's black box depends only on Alice's input choice and of its initial state. This is the classical determinism assumption.

More formally,
* (HA) there exists a function $$F_a$$ which, given an input i and an initial state $$s$$ of Alice's black box gives the output $$F_a(s,i)\in \{-1,1\}$$
* (HB) there exists a function $$F_b$$ which, given an input i and an initial state $$s$$ of Bob's black box gives the output $$F_b(s,i)\in \{-1,1\}$$


#### Notations
Some notations :
* $$a_+ = F_a(s_a,1)$$
* $$a_- = F_a(s_a,-1)$$
* $$b_+ = F_b(s_b,1)$$
* $$b_- = F_b(s_b,-1)$$

All of these are random variables because $$s_a$$ and $$s_b$$ are random variables.

* $$o_a = F_a(s_a,i_a)$$
* $$o_b = F_b(s_b,i_b)$$

These random variables are the observed outputs for each experiment.

#### Tadam!
Now, what is it that Alice and Bob are computing after having separated the datas into 4 categories ?
Recall that $$u_{++}$$, for example, is the averaged product of Alice's and Bob's black boxe outputs, where the average is restricted to the cases where Alice and Bob both chose 1 as input.
More formally, $$u_{++}= E(o_a o_b | i_a = 1, i_b=1)=E(F_a(s_a,i_a) F_b(s_b,i_b)|i_a=1,i_b=1) =E(F_a(s_a,1) F_b(s_b,1))=E(a_+ b_+)$$. The middle equality holds because $$s_a$$ and $$s_b$$ are independent of $$i_a$$, $$i_b$$.

Here $E(X)$ is a notation for the average of the random variable $X$.

Then, $$u_{++}+u_{+-}+u_{-+}-u_{--} =E(a_+ b_+) + E( a_+ b_- ) + E(a_- b_+) - E(a_- b_-)=E(a_+ b_+ + a_+ b_- + a_- b_+ - a_- b_- )=E(a_+(b_+ + b_-) + a_-(b_+-b_-))$$

Now, we see that for each experiment, either $$b_+ = b_-$$ or $$b_+ = - b_-$$ since $$b_+, b_-\in\{1,-1\}$$. So either $$|b_+ + b_-| = 2$$ and $$b_+ - b_- = 0$$, either $$|b_+ - b_-| = 2$$ and $$b_+ + b_- = 0$$. Then, $$E(a_+(b_+ + b_-) + a_-(b_+-b_-)) \leq 2$$. Then, $$u_{++}+u_{+-}+u_{-+}-u_{--}\leq 2$$. This is the classical prediction.

Quantum mechanics gives a way to build the two black boxes such that $$u_{++}+u_{+-}+u_{-+}-u_{--} > 2$$ (the maximum predicted value is $$2\sqrt{2}$$). Alice and Bob just experienced that. 

So at least one of the assumptions we made to model the experiment is wrong.

## Super determinism
The super determinism thesis denies the truth of hypothesis (HI) which states that the choice of inputs $$i_a$$ and $$i_b$$ are independent of the initial internal states $$s_a$$ and $$s_b$$. 

I won't say more about this. It sounds a bit crazy. It means that the random choices that Alice and Bob are not really random since they depend on the internal states $$s_a$$ and $$s_b$$ of the black boxes, they don't even know about !

There is a way to test this hypothesis though but I won't dig into details.

## Locality loophole


(HA) We assumed that the function $$F_a$$  which determines the output of Alice's black box depends only on Alice's choice of input and of Alice's black box internal initial state, and not on Bob's choice of input or Bob's internal state.

But it gets quite subtle here. First, Alice and Bob may not enter their inputs exactly at the same time. For example, Bob may enter his input one milisecond before Alice. Second, the blackbox may need some time (1 milisecond for example) to deliver its output once the choice of input has been made. So there is a delay of two miliseconds between the time when Bob sets his input and the time when Alice's blackbox displays its output.
 We could imagine that during this time, Bob's black box communicates to Alice's black box some information about its initial internal state and Bob's choice of input. Then Alice's output would also depend on Bob's choice and initial state.

This is called the *locality loophole* of Bell's experiments.

One way to circumvent this loophole is to position the black boxes at a large distance one from another. Indeed, the locality principle coming from relativity theory states that no signal travels faster than light. In particular, Bob's black box can't communicate its internal state or Bob's choice of input faster than light, so if Alice and Bob are separated by a distance which is bigger than the distance travelled by light during two miliseconds,  the locality principle ensures that the output of Alice's black box cannot depend on Bob's choice of input or Bob's black box internal state.

So it seems that the only way to deny the truth of hypothesis (HA) is to drop the locality principle. 

## Quantum reality : classical determinism is wrong
Quantum theory says that hypothesis (HA) is wrong, but do not deny the locality principle. How is it possible ?

Quantum mechanics denies the existence of such a function $$F_a(s,i)$$ which, given an initial internal state, a choice of input, gives without ambiguity the final output displayed by the black box. Instead, it replaces it with a random variable.

This implies that even if you know completely the state of the black box before the choice of input, even if you know which input was chosen, you could not say what would be the output. And this is not because you don't know enough of the system. It is not like when you throw a dice and argue that the result is random, because in this very case, if you know exactly how you throw the dice, you could write the equations of movement and compute on which side the dice will end.

So what is this bizarre kind of state that do not allow you to deduce with certitude what the future is going to be ? This is called in quantum terminology a *superposition state*. A quantum physicist would say that the black box is in a superposition of two states, one leading to the 1 output, and the other one to the -1.

To come back to the Schrödinger's cat, quantum mechanics predicts that the cat's state before one opens the box is indeterminate in the same sense : even if you knew the cat's state completely, you could not deduce whether it will be dead or alive when you will open the box.

## Quantum theory is incomplete

However there is a problem with the quantum theory. It says that the output of the black box is a random variable that depends on both the input and the internal state, but it says nothing about the exact time at which  the state of the black box is enough determined so that the output  of the black box is fully predictible. In quantum mechanics, this time is referred as the "measurement time", which is not a very precise description.

## Quantum theory is complete

Most physicists believe that the quantum theory is complete : they believe that the so-called "measurement time" is actually the time when the observation data come to the observer's consciousness but however that this "measurement time" may be different for each observer. This means for example that Alice and Bob are themselves in a superposition of states with respect to their friend John who waits for them outside the museum (because he was afraid of quantum black holes). Then, the measurement time for John would be when he meets again Alice and Bob after the experiment and that they tell him what happened inside. This was a kind of grossier example, but that's the spirit.

The many-world interpretation is the most mainstream interpretation among physicists to understand this weird fact : it says that each time there is a quantum experiment, the world is forked in two versions, one for each possible result. But we humans are only conscious of one world. The main issue with this interpretation is that the many-worlds hypothesis cannot be tested, so it may be questioned whether this should be considered as a serious scientific proposition

Relational quantum mechanics is another current among physicists, initiated by Carlo Rovelli, that just says that we should accept this fact in a similar fashion that Einstein's theory of relativity made us accept the fact that for example the speed of time is relative to the observer.

## Conclusion

This experiment, described in terms of abstract black boxes, does not justify the quantum theory, but at least it shows that the classical picture is wrong.

If some day we were able to build such black boxes (which is a technological challenge, no a theoretical one), everyone could do the experiment with a friend. No-one could deny the failure of the classical description of the world by arguing that physicists made mistakes, or that this is a scientist complot.



