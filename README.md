# Learning
Let's just be automatons

**TL;DR anybody?**

> Look for TL;DR sections below.

## Purpose
We (Adimpression) will tell you how to transform into an automaton; to be truly selfless and be in services of others.

## Discalaimer
While most go by the license Adimpression uses, `Apache 2.0`, we would like to highlight that we are buildling this on-the-fly. Some call it building a ship in the sea. We call it DRA!

## DRA

- D: `Do it once` - The first time anybody does anything is a profound occurrence in the universe both in the eye of the observer and the the observant. Be it a unit test you write or something more profound, doing something the first time, should be well observed and recorded (ideally)
- R: `Repeat it twice` - Next time you do the same thing, you have a something thinking to do. From simple questions such as "what are the odds I'll have to do this again?" to the hard such as "How many different way can this happen?", you've got choices to make; such as "How do I make my life easy the next time I have to do this?" or "Do I even need to care about next time?".
- A: `Automate it the third time` - Well; the ones that you do often, you should automate; unless it is fun to do of course. But remember, automating could also be something you do all the time. So automating automation is something you should put your thought into. If you take a moment to think, you will realize the world is full of automatons commanding automatons. Like my fingers tapping on buttons which command the may laptop to display it the screen; which when I hit save; will command the github text formatter to format; which will then be saved somewhere in some server; thereby commanding the server to serve this content to you;

We like to think of DRA as a few other versions of things:

- D: Do it onces - Man does this
- R: Repeat it twice - Man uses a tool to get things done
- A: Automate it the thirt time - Man automates the tool or what the tool does

So we also call this `Man-Tool-Machine`. 

## "Hello World!"

Let's make a choice; a very important one (for reasons of sanity). We are going to either define a problem or a solution; not both. So we are going to pick one of these:

1. How do I say "Hello World!" as an automaton? (Problem)
2. Here is how to say "Hello World!" as an automaton. (Solution)

We find that while people like to complain a lot (us included; you too?!), they actually like to state what they want rather than blabber about their problems in situations that really matter. So an automaton, alwasys picks the solution based pparoach. Displaying "Hello World!"  is what matters. Hence we go by option 2:

> Here is how to say "Hello World!" as an automaton. 

Let's state that as something we've already done; be optimistic. State the end result; end state; 

> Displayed Hello World

In fact, we as an automaton that has not done anything remarkable, can say we have:

> Not Displayed Hello World

and as a automaton who has done something remarkable which:

> Has Displayed Hello World 

Ah! So we did manage to define our problem too (Not Displayed Hello World). And our solution (Has Displayed Hello World). 

To make things easier to manage form now on all "has" shall be written as "is". (Including "am", "are"). And we still will focus on the solution rather than the problem definition (Is Displayed Hello World).

So to summarize, our first task as an automaton would like to reach the state:

> Is Displayed Hello World

Automaton or not, we are still developers. So let's write this in a YAML like Syntax.

> Is Displayed Hello World:

Next, let's write the inputs and outputs needed. Oh, but we've only got an output txt and don't need inputs. So let's just get to it:


```
Is Displayed Hello World:
  - Is Display String
```

`String` is a type of data we would like to use (Others are `Integer`, `Float`, `Boolean` for arrays and of course, for arrays it is `Strings`, `Integers`, `Floats`, `Booleans`).

Is or Not is based on which state the 'Is Displayed Hello World' produces. 'Display' can be anything such as 'Msg' or 'Foo' or 'Bar.

But what if we have to deal with inputs? Experience has tought us to create two separate files for this:

**TL;DR**

We store the files using a convention

> File name: displayedhelloworld.displayedhelloworld.txt

```
Is Displayed Hello World:
  - displayedhelloworld.input / Not Input
  - displayedhelloworld.output / Is Output
```

We create a file which defines our inputs, but of course there are no inputs.

> File name: displayedhelloworld.input.txt
```
Is Input:
```

Here's the file which defines our outputs.

File name: displayedhelloworld.output.txt

```
Is Output:
  - Is Display String
```

Are we done yet? That is actually it; just some grunt work left that's all. There's always a bit of grunt work! Here's what happens next (hold on to your seat tight):

**TL;DR**

1. The YAML you wrote will go through [this](https://github.com/Adimpression/Scarcity) automatically. It generates a few .proto files, which you can access publicly [here](https://github.com/Adimpression/proto/tree/master/proto/displayedhelloworld):

Send a pull request to https://github.com/Adimpression/Dimensions (if you're trying out this tutorial, just add a few new lines (since these yamls already exists there).

Once we approve the pull request, CI/CD will make the .proto available via the above bucket in a matter of minutes.

2. Then you will implement [this](https://github.com/Adimpression/proto/blob/master/proto/displayedhelloworld/displayedhelloworld/index.proto) (If you did some other message, it should appear accordingly): note the service. (few lines of code). Basically a gRPC service.
3. Build  a docker image serving gRPC on port 8080. Push it to Docker Hub(public).
4. Create a discovery file (pull request) [here](https://github.com/Adimpression/Discovery/) and [example](https://github.com/Adimpression/Discovery/blob/master/displayedhelloworld.register.yaml) and send us a pull request. It is basically the image and tag (version) plus a few other configurations of which mainly needed are

```
  appState: 'IsDisplayedHelloWorld'
  appName: 'displayedhelloworld'
  appDomain: 'displayedhelloworld'
```

5. Done. You are now an automaton that can say Hello World! to anybody, using any language gRPC supports. You are at their service! To connect to this, you can use https://github.com/grpc/grpc-web based clients pointing to "s.qs.fyi". At the moment there is already a service running. Standard gRPC connections work too, but of course within the cluster. For that we need two services! Let's do that next :)
```

