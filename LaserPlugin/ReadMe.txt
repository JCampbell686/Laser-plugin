Info:

(This looks like a lot of "work", but there's like 3 minutes worth of tasks here, its also all screenshots so you can just copy it bar for bar)

By default, the system immediately works to simply deflect.
> To do that, just place a laser source down, and it will spawn a static laser on begin play. The source laser isn't designed to move, as that would make it miles more complicated and resource heavy.

How to activate an object via the relay:

Create an actor, go to class settings and implement the relay interface
Then on the left, in the same panel with variables, you should see a "interfaces" drop down, in there you can implement events. To make a relay power this actor in particular, you click on the relay, and click the button on "AllActorsToActivate" variable (its a public variable, don't open the actor to do this). Then press the drop icon and select the actor you want to activate in the world (or search for it if you want).

Mirror:

Rotating the mirror should work on start too, but in order to give the player the ability to pick up the mirror, you will have to do some things in the animation blueprint (Although the animation is NOT blended at all, because I cannot figure it out with whatever is going on in this template file)

To get the animation set: ---------

Head to the character animations and open "ABP_TemplateCharacter", then head to the event graph and make it look like the following:

https://prnt.sc/f3efBwUJD1vZ

Then, create a variable here called "Grabbing", make it a float with default value 0

For the last thing in this blueprint, head to the tab called "AnimGraph" and add this:

https://go.screenpal.com/watch/cTXu6EnqgJR

^ Once you make the "Layered blend per bone", you need to click on it and add this:

https://go.screenpal.com/watch/cTXu6dnqgKh

^ Bone Name is "spine_01" and must be written exactly like that

Now finally just create a Boolean variable inside the player blueprint, with a default value of false and name it *exactly*:

CurrentlyGrabbing?