---
title: "Nerdy letters: reteaching math pt. 1"
parent: Nerdy Letters
layout: default
nav_order: 1
permalink: /nerdy-letters/reteaching-math-1/
description: "Understanding dy/dx — motivated by a block sliding down a ramp."
---

# Nerdy letters: reteaching math pt. 1

I was sitting in a car with a friend and we started discussing the implications
of many concepts learned in school. Many people who shift from engineering to
other professional jobs cite the lack of motivation of some engineering
concepts. It wasn't until I went to grad school I realized my undergrad math
professors and secondary (high) school teachers (I respect them a lot so this is
no shade to them) either did not understand the concepts to the depth required
to arouse excitement about a specific topic, or they lacked the tools (or tact)
to communicate and motivate those ideas properly.

Luckily for me, I was decent at recognizing patterns and thinking my way through
problems (similar to my strategy playing style of chess), but there is another
level which is more intuitive that comes from a place of deep understanding.

I decided to write this completely without any outside reference or use of any
tools, just pure understanding and visualization of how I've come to describe
the world.

## Understanding dy/dx

Bro, I remember I was introduced to calculus at 14 years old and I was like
"what the hell is \\(dy/dx\\)." I had resumed a bit later that year, so the class
had two weeks and I was playing catchup on an entirely new concept. I figured
for most basic polynomial functions, the rules underpinning \\(dy/dx\\) (formally
known as derivatives or differentiation) were straightforward to recall from
memory. That took me far enough.

It was not until later we started applying those concepts to calculate the time
at which a block will slide down from a ramp. IMO, this was backwards teaching.

### Motivating the concept: time to slide down

<figure>
  <img src="{{ site.baseurl }}/assets/images/ramp.svg"
       alt="A block resting at the top of a ramp, with the height labelled y, the horizontal run labelled x, and the sloped length labelled s.">
</figure>

Above is an example of a block on top of a ramp, and **we want to understand how
quickly the block will go down the ramp**. *How can we reason about this*? We
know the length and height of the ramp (or at least, let's assume we can measure
them), and to fully understand this, we may need a little understanding of the
world–physics.

Every item with mass has some inertia. Let's just call it weight and because it
has a weight, it will want to roll down the incline. Can we agree on that? I
think we can ;). Intuitively, we can because most of us have seen this happen?
As kids, we would spend time in playgrounds to slide, and no one had to convince
us that we would indeed slide down. We saw others doing it, it worked–we
experienced the world as we were prescribed–physics is a description of that
experience, and math is the language of that description. Feel me? Okay, let's
continue.

If we believe that the block will slide down, then we can wonder how fast it
will slide down. Let's reason about this together. We know if our "ramp" was
flat, like a race track, similar to how we experience the earth day to day
(mostly flat). I say "ramp" because if it is flat, then it's just a platform.
Okay, let's call it a platform then. If the platform was flat, and we sat on it,
we would remain in the same position, similar to what happens to the block as
well.

So if this is the case there must be something that pulls the object downwards
(as we experience it) but not sideways. And that thing is pulling with the same
amount of exertion (Force). I try not to say force so we don't have to define
that yet.

Now \\(dy/dx\\) simply addresses the Q: "***for tiny change in x, how does y
change?***" This is obvious because of the shape of the ramp; to go down, we must
go right and vice-versa. We know something forces us to go down. *What goes up
must come down*. Thus, for free when we go down (which we must), we go right as
well. The relationship between the change in y (coming down) and the change in x
(going right) is \\(dy/dx\\). Now, to understand "how fast," we must involve
time. Our perception of slow or fast is dependent on how we traverse a different
dimension.

Let us introduce another dimension, the **time dimension.** From experiments,
scientists (I think Newton?) have measured that on earth all objects with mass
(when ignoring drag and every other resistive force) accelerates at about
9.8m/s^2. Meaning any object dropped from a height is constantly increasing its
speed as it drops. Acceleration is the rate at which velocity (speed) is
increasing which is \\(dv/dt\\). So derivatives simply relate how things on earth
move through the world by relating various dimensions and axes.

$$
\frac{dv}{dt} = a = 9.81\,\frac{\text{m}}{\text{s}^2}
$$

But now, because the object is sliding, not free-falling, we lose some
acceleration due to the sliding, which depends on \\(dy/dx\\), which directly
measures the slope, which is equivalent to the tangent of the angle the ramp
makes with the horizontal ground.

$$
\frac{dy}{dx} = \tan(\theta) \quad \text{(in this case we can just say } y/x\text{)}
$$

So to resolve the component pulling the block down to a component sliding
diagonally down, we use the ratio of the height (\\(y\\)) and the length of the
ramp (we will call this \\(s\\)).

Thus

$$
\frac{a}{s} = \frac{y}{s}\,9.81 = \frac{y}{\sqrt{y^2 + x^2}}\,9.81
$$

If you think of it, it is intuitive, we all perceive that something makes all objects fall to the ground. It is one of the reasons reason we walk, not fly. Note, for the block to slide down, it has to traverse the x axis as well, so some of that force pulling it down is also used in creating the horizontal travel. As a result, the block will not move as quickly (or accelerate) as it would if it were a free fall in only the y direction. Notice in the equation below as x approaches 0, we recover the full 9.81 acceleration caused by said force pulling all objects on earth down (a.k.a Gravity). 

$$
dv = \frac{y}{s}\,9.81\;dt
$$

$$
\text{velocity} = \frac{y}{s}\,9.81\;\text{time}
$$

If we set our starting time and starting velocity to zero, then we can
approximate a linear relationship between time and speed, similar to y and x
(\\(dy/dx\\)).

Now remember speed is also a rate, the rate at which we cover distance. Let us
call distance \\(s\\)

$$
\frac{ds}{dt} = v = \frac{y}{s}\,9.81\,t
$$

$$
ds = v\;dt = \left(\frac{y}{s}\,9.81\,t\right) dt
$$

To get \\(s\\) here, we have to do something called "integrate" but to avoid
jargon here, let me describe what is happening.

The acceleration is constant, so the speed climbs evenly from zero — that is
\\(v = a\,t\\), the same straight-line story we just told. Distance is different.
It grows at the rate \\(v\\), and \\(v\\) is not constant, it is climbing the
whole way.

So let us reason about it like this. If we had travelled at our *final* speed
\\(a\,t\\) for the whole trip, the distance would just be that speed times the
time:

$$
s = (a\,t)\,t = a\,t^2
$$

But we did not travel at that speed the whole time. We started at zero and
climbed to it in a straight line. So we only cover half of it:

$$
s = \frac{1}{2}a\,t^2
$$

<figure>
  <img src="{{ site.baseurl }}/assets/images/slices.svg"
       alt="Speed plotted against time as a straight line rising from zero. A rectangle of height a-t and width t is outlined, and the triangle beneath the line, shaded and cut into thin vertical strips, fills exactly half of it.">
</figure>

That is the picture above. Speed against time is a straight line, the distance we
cover is the area underneath it, and the area under a straight line rising from
zero is a triangle — half the base times the height. The rectangle around it is
the trip we did not take, the one where we moved at the final speed the whole
way.

So we end up with \\(s\\) (distance travelled), if initial distance is 0.

$$
\frac{1}{2}\,\frac{y}{s}\,9.81\,t^2
$$

To make it easy, let's round 9.81 → 9.8. So we say

$$
s = 4.9\,\frac{y}{s}\,t^2
$$

So now we can calculate the time it will take to slide down since we know the
length \\(s\\) of the ramp that we built. Thus:

$$
t = \sqrt{\frac{s^2}{4.9\,y}} = s\sqrt{\frac{1}{4.9\,y}}
\quad \text{or} \quad \sqrt{\frac{y^2 + x^2}{4.9\,y}}
$$

To me, this is beautiful, don't you think? The travel time only depends on some distance \\(s\\), which
is the length of the ramp we built (thus prescribed) and the height of the ramp (or the slope). This allows
us to build things with some level of certainty about the outcome. For example, we can decide the maximum speed we
want kids (or adults, we like to play too!) to safely go down a water slide and the time from start to finish by fiddling with the slopes (height to length ratio) of the slides. All these ratios connect precisely to trigonometry,
but I delay treatment for now.

The world has prescribed constraints and boundaries we work with and mathematics
gives us a language to express those boundaries, and physics ponders about the
relationship of those boundaries.
