---
layout: post
title: "Why imaginary numbers are for real"
author: "Vivek S. Handebagh"
date: "April 14 2025"
math: true
image: /assets/images/hammerhead_long.png
---

<div class="post-header-image">
  <img src="{{ '/assets/images/hammerhead_long.png' | relative_url }}" alt="hammerhead" />
</div>

## Introduction

The absurdity of imaginary numbers is inherent in its name. Maybe it would have been fine if it were a fun little intellectual experiment confined to the minds of socially secluded schizophrenic mathematicians. Yet, it is not so, and we would be unable to explain nor engineer our world without the fantastical, almost mystical, beings that are imaginary numbers. The relevance of \\(i\\) in the mathematical framework of the world is largely weighted in Euler's equation:

\\[
e^{ix} = \cos x + i\sin x,
\\]

However, as deep and powerful as Euler's equation truly is, it is perhaps one of the most shallowly introduced ideas. Most people are wildly bewildered by Euler's equation at first sight. Even though it had been mathematically derived for them, there might have still been a subtle feeling akin to forcing yourself to simultaneously swallow two flavors that should have never been plated together. Nevertheless, your bewilderment and confusion is washed away by a sea of plug-and-chug homework problems. But if you really pause and stare at this equation, it looks absolutely absurd.

In this document I hope to build a new and far deeper intuition that will actually motivate why such a relation must exist. I will do so by building on fundamental principles to ensure you really understand it, so I ask that you keep with me even if you feel like something is trivial. You might find yourself thinking about these things from a perspective you hadn't before, and you might even find yourself reading a handful of philosophical sentences intertwined with the math. Ultimately, the Euler equation encodes a deeper truth about the universe, but it's often wholly ignored.

## Looking to the left

The absurdity starts with the definition of the imaginary unit $i$ as $\sqrt{-1}$. Actually, I must correct myself. The craziness starts with negative numbers itself. If I am going about my day and see one friend to my right and another friend to my left, my brain observes their simultaneous positions with respect to itself as the center. To observe or describe this situation accurately, the brain must carry some quantifiable measure of relative distance and an additional piece of qualitative information that is apparent from the fact that I must move my head to look at each of my friends. That is, the description must carry a notation that specifies the direction relative to the arbitrary center of reference. This should seem trivial, but what I mean is that negative numbers arise from some arbitrary definition of a 0 as the midpoint of an infinite set, and this slightly unintuitive weirdness of negative numbers can be tolerated as they can still describe physical observables.

Now, when we say we are multiplying two numbers together, what we mean is that we have a particular quantity that we want to scale (stretch or squeeze) by a particular factor. While my ability to stretch a quantity is unlimited, my ability to squeeze a quantity is ultimately bounded by only being able to squeeze something until it is practically no longer there (i.e. 0). So, in order to access the space that's to the left of my point of reference, I need not just squeezing and stretching, but I also need flipping, which we denote with the negative sign ($-$). Again, this may seem trivial, but keep with me for a second.

The existence of negative numbers, or the need for this flipping operator, characterizes a fundamental symmetry of the world. Because what does it mean to flip? To flip really means that there are two sides to flip between—that there are two and only two sides to flip between, for flipping twice puts you back on the side you started with. What negative numbers are really doing is saying that you cannot approach the world without a point of reference to approach from, and doing so divides the world in two. It tells us that you cannot move forward without having moved away from what was behind you. In other words, contrast creates existence.

## Cycling through the sets

In our notation, we just stick a ($-$) in front of numbers, but in reality, this flipping operation is carried out by multiplying a number by $-1$. Thus, taking $-1$ to some power $n$ means to flip some quantity $n$ times.

$$
(-1)^1 = -1, \quad (-1)^2 = 1, \quad (-1)^3 = -1, \quad (-1)^4 = 1, \quad \ldots
$$

$$
(-1)^n = 
\begin{cases}
-1, & \text{if $n$ is odd},\\[1ex]
1, & \text{if $n$ is even.}
\end{cases}
$$

In doing so, we observe this simple oscillatory pattern of period two, which cycles through the states of the set [1, $-1$]. Coming to the random thing that we defined as the square root of $-1$, what does it mean? Well it explicitly doesn't mean anything or correspond to anything physical. While $i$ is heavily used in physics and engineering, it does not represent something real. What it represents rather, is a new type of symmetry. Analogous to this idea of $-1$ as a flipping operator, what kind of operator is $i$? In other words, what happens if I multiply some value by $i$?

If we borrow our intuition of $-1$ as an operator that takes a point some distance away on the axis to our right, and places it the same distance away on the axis to our left, then $i$, as an operator, takes some point on this real axis (left and right axes combined) and places it the same distance away on some new made-up axis. When I say "same distance," I mean that we choose an arbitrary center for this new axis that is the same as the center for the real axis. Or in other words, $i$ applied to 0 remains 0.

Notice that I am not telling you that this new axis goes up and down in contrast to the real axis going left and right. The basic precalculus and trigonometry-based explanation for Euler's relation would start by defining the imaginary axis as vertical or orthogonal to the real axis, and thus drawing an analogy to the unit circle and its geometry. But this doesn't make sense to me because there is no motivation to define the imaginary axis as orthogonal to the real axis, for it is after all a made-up axis. How absurd is it to make up some imaginary axis of fake numbers and start entangling them with real ones through geometry and the properties of triangles! So, for now there is no constraint on the *direction* of this new made-up axis.

The true significance of imaginary numbers emerges from asking what happens if we keep applying the operator $i$? What we see here is a new type of oscillatory behavior of period four, cycling through the set [$i$, $-1$, $-i$, $1$]. But what does this imply? What deeper symmetries is this supposed to reveal?

$$
i^1 = i,
$$ 
$$
i^2 = \sqrt{-1}^2 = -1,
$$
$$
i^3 = -1\cdot i = -i,
$$ 
$$
i^4 = -i \cdot i = -(-1) = 1,
$$
$$
i^5 = i, \ldots
$$

This by itself doesn't reveal anything about the physical world. At the end of the day we just invented some mechanism by which we gain two more tokens to cycle through in some particular order. We do know that there must be some important role that this pattern plays in our description of the world. So what can we find from the real world that has this sort of oscillatory behavior of the same periodicity?

## Steadfast in motion

Since we are dealing with some type of oscillations, we may as well check to see if there is something that our fellow \\(\sin()\\) and \\(\cos()\\) operators have to say. If we look at a plot of either \\(\cos()\\) or \\(\sin()\\), there are four points of interest to notice within one period of oscillation: the trough, the crest, and the two points where the slope of the curve is the steepest, all of which are separated by a distance \\(\frac{\pi}{2}\\). Hmm, a cycle of four, maybe there is a hint here?

But perhaps, the most intriguing or magical property of the sinusoidal function is that the rate of change of the function oscillates with the same frequency. That is, the derivative of a sinusoidal function remains unaltered except for it being shifted over by a distance \\(\frac{\pi}{2}\\). Okay, so let's try and probe this a little deeper. What happens if we keep differentiating a sinusoidal function?

$$
\frac{d}{dx} \sin x = \cos x
$$

$$
\frac{d}{dx} \cos x = -\sin x
$$

$$
\frac{d}{dx} (-\sin x) = -\cos x
$$

$$
\frac{d}{dx} (-\cos x) = \sin x
$$

Notice a pattern? It takes us four steps of repeated differentiation to return to our initial condition. This makes sense given that we had just seen that there were four points of interest separated by \\(\frac{\pi}{2}\\). Each time we differentiate, we are iterating to the next point of interest. Looking closer, it shouldn't take much effort to perform some pattern matching and draw analogies between 1 and $i$ with $\sin x$ and $\cos x$. The intuition that I aim to build here is that these sinusoidal functions, which are as universally fundamental and physically rooted as a mathematical concept can get, have really special relationships with each other and their negatives that look eerily similar to the cycles of $i$. In other words, it is this pattern of cycling through a set of four that we are observing and using to construct bridges across these seemingly unrelated mathematical objects.

So let me reiterate here that the derivative of a sinusoidal function remains a sinusoidal function. The crazy part is that there is another function that exhibits this sort of resilience and steadfastness. This function remains completely unchanged under differentiation, almost as if it was so deeply rooted in its purpose that its motion looked still, completely pure and inseparable from its identity. It was not like this because it belonged to a particular family or nationality of functions. Rather, it was its one-pointedness, or its focus on exactly one particular unending string of numbers. That is

\\[
f(x) = e^{x}
\\]

where

\\[
e \approx 2.7183818\ldots
\\]

Why this particular number? Well, that is a question that you must ask the day you meet your God. But even if you do, he may likely laugh at you for trying to find meaning in some random number that he generated. Nevertheless, it is still a real number, so we can marvel at it as long as we want while still being okay with it showing up in the real world. The beauty of mathematics here is in recognizing that there is this qualitative similarity of retaining a sense of identity under differentiation (which I will call *steadfastness in motion*) between two separate families of functions, and thinking (dare I say knowing) that it must be more than a coincidence. There must be some bridge to build.

## Tracing the clues

Up until now I have been focused on providing intuition, patterns, and qualities that can help one say "Oh yeah, as absurd as Euler's equation is, it makes sense that all of these components are connected in some way or another." The formal proof of Euler's identity is something you may have already seen. But if you are this far into this document you might as well revisit it and pause to think deeper about what is actually happening.

Every function can be locally approximated by a series of polynomial functions that are preceded by the correct coefficients. If the series becomes infinite, it is no longer a local approximation, but a complete representation. Here are the infinite series representations for $e^x$, $\sin x$, and $\cos x$.

$$
e^x = \sum_{n=0}^{\infty} \frac{x^n}{n!} = 1 + x + \frac{x^2}{2!} + \frac{x^3}{3!} + \cdots
$$

$$
\sin x = \sum_{n=0}^{\infty} \frac{(-1)^n x^{2n+1}}{(2n+1)!} = x - \frac{x^3}{3!} + \frac{x^5}{5!} - \frac{x^7}{7!} + \cdots
$$

$$
\cos x = \sum_{n=0}^{\infty} \frac{(-1)^n x^{2n}}{(2n)!} = 1 - \frac{x^2}{2!} + \frac{x^4}{4!} - \frac{x^6}{6!} + \cdots
$$

At first glance, we see that each of these functions have the same coefficients for each of the corresponding powers of $x$. This similarity might have been something that you had brushed over the first time you saw this derivation. But it should make sense now that these similarities in the series representations are a consequence of the aforementioned *steadfastness in motion* that is shared by each of these functions. You are welcome to check the *steadfastness in motion* by actually differentiating the series representations. I have done it for $e^x$, but you are welcome to do it for $\cos x$ and $\sin x$.

$$
\frac{d}{dx} e^x = \sum_{n=0}^{\infty} \frac{nx^{n-1}}{n!} = \sum_{n=1}^{\infty} \frac{x^{n-1}}{(n-1)!} = \sum_{n=0}^{\infty} \frac{x^{n}}{n!} = 1 + x + \frac{x^2}{2!} + \frac{x^3}{3!} + \cdots = e^x
$$

Now, there is something qualitatively similar about the nature of the exponential and sinusoidal functions, and we want to find a relationship between them. So let us try to approach the construction of this bridge from different angles. We realize first that $e^x$ only has positive coefficients in front of every term, whereas the sinusoidal functions alternate between $(+)$ and $(-)$. So for our first step, maybe we should try $e^{-x}$?

$$
e^{-x} = \sum_{n=0}^{\infty} \frac{(-x)^n}{n!} = 1 - x + \frac{x^2}{2!} - \frac{x^3}{3!} + \cdots
$$

Cool. It can be seen that the sinusoidal side of this possible relation must be some form of addition because we need both the even and odd terms combined. So let us try that first and see if we are missing anything.

$$
\cos x + \sin x = 1 + x - \frac{x^2}{2!} - \frac{x^3}{3!} + \frac{x^4}{4!} + \frac{x^5}{5!} - \frac{x^6}{6!} - \frac{x^7}{7!} + \cdots
$$

$$
e^{-x} \neq \cos x + \sin x
$$

Nope! What about $\cos x - \sin x$?

$$
\cos x - \sin x = 1 - x - \frac{x^2}{2!} + \frac{x^3}{3!} + \frac{x^4}{4!} - \frac{x^5}{5!} - \frac{x^6}{6!} + \frac{x^7}{7!} + \cdots
$$

$$
e^{-x} \neq \cos x - \sin x
$$

Nope! Same problem. Note that there is no use in trying $\cos (-x)$ or $\sin (-x)$ because the negative is either extinguished or pulled out by the symmetries of these functions. Clearly, we must find a way to change the pattern of negatives and positives on either or both sides of the possible equation, but we have run out of ways to do so with the simple flipping pattern of the $-1$ operator. Therefore, it is the need for a new type of cyclic pattern of signs that truly motivates trying to include imaginary numbers in the cement that will be used to build this bridge.

Now the question is: How do we find the right way to introduce $i$ into the equation? It would be easier if we start with the exponential side. It would do us no good if we just scaled every term in the series by $i$. The whole point is to create a new oscillating pattern of positives and negatives. The only way to do this is to place $i$ in the input of the exponential. Or, $x$ must become $ix$, and the left-hand side should be $e^{ix}$. Expanding this out, we get:

\\[
e^{ix} = \sum_{n=0}^{\infty} \frac{(ix)^n}{n!} = 1 + ix - \frac{x^2}{2!} - \frac{ix^3}{3!} + \frac{x^4}{4!} + \cdots
\\]

From this, it is clear that only the odd terms carry a factor of \\(i\\). If we rearrange the series:

\\[
e^{ix} = \Bigl(1 - \frac{x^2}{2!} + \frac{x^4}{4!} + \cdots\Bigr) + \Bigl(ix  - \frac{ix^3}{3!}  + \cdots\Bigr)
\\]

\\[
e^{ix} = \cos x + i\sin x,
\\]

and there we have it—the celebrated Euler's formula!

## Geometric consequences

The sinusoidal functions, which are the fundamental functions that describe the oscillatory aspects of the universe, happen to also describe the fundamental relationships of geometry. At first, these trigonometric functions represent lengths and ratios of triangles. But at a deeper glance, what they are really trying to reveal is the relationship between the concepts of distance and direction.

If we are in a 2D space, we would need a direction and a distance to describe any point in space. What happens if we take away one degree of freedom by holding the distance constant? How do we describe the space of orientations? While the number of possible directions is infinite, there is the peculiar property that if I keep turning in a particular rotational direction, eventually I will end up facing the direction I started in. In other words, though the number of possible directions is infinite, they are bounded by some sort of periodicity. This periodicity reflects a fundamental symmetry of space itself, and it is this symmetry that relates oscillation with geometry.

![The complex unit circle. The cosine component extracts the horizontal or real component, while the sine component extracts the vertical, imaginary component. This evidently corresponds to the \(i\) being in front of only the sine component in Euler's equation.](image.png)

All of these ideas put together is what truly suggests that we portray the imaginary axis as geometrically orthogonal to the real axis, as opposed to the idea that the geometric relationship between the two axes is the motivating reason for Euler's equation. This geometric interpretation allows us to treat the input of $e^{ix}$ as an angular parameter, and thus, we can now work with complicated combinations of sinusoidal functions by leveraging Euler's equation and the powerful properties that exponential functions possess. In the real world, one might encounter many situations where different physical oscillations interact with each other while being in different phases. For example:

$$
f_1(t) = \cos (\omega t) \quad \text{and} \quad f_2(t) = \cos (\omega t + \phi)
$$

If we want to understand the resulting wave that is a superposition of $f_1$ and $f_2$, we would need to first calculate $f_1 + f_2$. But to do this in the form of cosines and sines, we would have to go and invoke the inconvenient trigonometric identities that nobody bothers to memorize. Invoking the identity 

$$
\cos (x) + \cos (y) = 2\cos\Bigl(\frac{x + y}{2}\Bigr)\cos\Bigl(\frac{x-y}{2}\Bigr),
$$

we get

$$
f_1 + f_2 = \cos (\omega t) + \cos (\omega t + \phi) = 2\cos\Bigl(\omega t + \frac{\phi}{2}\Bigr)\cos\Bigl(\frac{\phi}{2}\Bigr)
$$

But let us write this in the complex exponential form and see what it looks like. Remember that a cosine function is just the real part of the corresponding complex exponential.

$$
f_1(t) = \operatorname{Re}\Bigl[e^{i\omega t}\Bigr] \quad \text{and} \quad f_2(t) = \operatorname{Re}\Bigl[e^{i(\omega t + \phi)}\Bigr]
$$

$$
f_1 + f_2 = \operatorname{Re}\Bigl[e^{i\omega t} + e^{i(\omega t + \phi)}\Bigr] = \operatorname{Re}\Bigl[e^{i\omega t}\Bigl( 1 + e^{i\phi}\Bigr)\Bigr]
$$

In this form of the sum, we are able to separate the terms involving $\omega$ and $\phi$. The benefit of this type of separability is subtle in this form but more evident when you consider products of two waves.

For instance, consider the product:

$$
f_1(t) \cdot f_2(t) = \cos (\omega t)\cos (\omega t + \phi) = \frac{\cos(2\omega t + \phi) + \cos(\phi)}{2}
$$

Writing this in the complex exponential form:

$$
f_1(t) \cdot f_2(t) = \operatorname{Re}\Bigl[e^{i\omega t} \cdot e^{i(\omega t + \phi)}\Bigr] = \operatorname{Re}\Bigl[e^{2i\omega t} \cdot e^{i\phi}\Bigr]
$$

This shows that whenever there is a phase difference, the extra phase term can be simply factored out, allowing us to avoid dealing with complicated trigonometric identities. Note that this works just as well with sine functions instead of cosines if you remember to add a global phase of $\frac{\pi}{2}$.

## Conclusion

Hopefully, by now you feel that Euler's formula is not just some absurd mathematical relation that should not make any sense. While Euler's formula does act as an identity that can be used as a trick to simplify computations, it is a profound and marvelous equation that is motivated by a logical effort to uncover a deeper unity behind strange concepts in our universe. What began with a seemingly nonsensical quantity—the square root of negative one—has unfolded into a journey that ties together the symmetries of space, the symmetries of oscillation, and the symmetries inherent in differentiation. Really, the square root of negative one is a mechanism that represents the rhythms of nature. It does not just complement the real; it completes it.
