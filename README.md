These ideas will get spun off into separate repositories if and when they are started.

## Digital Audio Hub

This is a project I am just getting started on.  The idea is to take a Raspberry Pi 4B ($60) and
some USB sound adapters ($17 each) and create a centralized box in the airplane where everyone
plugs in his/her headset.  Analog versions of these exist.  The digital version will add these features:

* each person can airplay music from his phone/tablet to the box
* a flash drive containing a bunch of music that can be streamed out
* each person can decide using a simple web page (served by the box) which sound sources he/she wishes to hear:
  * aviation radio
  * which other people (up to 4)
  * which airplay source (1 of 4)
  * flash drive music (album, playlist, etc.)
  * and at which volumes for each of those

The box will provide analog output for each set of headphones, but audiophiles may feed USB output to their own headphone amp (such as the awesome FiiO Q5s).

There will be a switch that allows the pilot to force his voice to be broadcast to all and to 
hear everyone else.

There will be web options to control how music sources will be attenuated when someone is speaking.  For 
example, when the pilot is making an announcement, it may be wise to drastically attenuate all airplay sources
(better: pause them).  In other cases, 50% attenuation may be a better choice.

One safety issue is that the pilot must always be able to hear and speak on the radio.
At the very least, there will
be a physical analog switch to let the pilot switch his headset to the airplane's ports.  An open question
is how the pilot will know to do this.  One option is to add an analog device that detects radio audio
and lights up a green LED.  If the pilot doesn't hear anything through the box when he sees the green light, 
then he knows to flip the switch to fail-over to the analog ports.

Because the box acts as a wi-fi router, we could also add a low-earth satellite internet module to
give everyone some internet at higher altitudes.  Unfortuntely, the bandwidth from these satellites can be 
quite low.  Maybe that will change.

Software libraries used:
* portaudio
* airplay2-receiver

The Raspberry Pi ensures that all of this can be done in real-time with no glitches.

## Applying Artificial Intelligence to Predicting and Preventing Accidents

There are tens of thousands of NTSB reports on plane crashes.  I have downloaded all of them in text format.

I'd like to train a neural network to predict outcomes based on flight conditions and 
decisions by pilots.  Initially, just try to predict what kind of accident occurs using the data in the 
report.  And possibly gain a litle deeper insight into the root causes.

Ultimately, we'd like to be able to take in all kinds of data from preflight planning as well as realtime
systems monitoring, and then predict the pilot's chances of having an accident at any given moment.  
By doing stealth monitoring of systems and adjustments made by pilots, we may be able to 
learn to predict courses of action that pilots should take to correct issues in realtime, 
and then suggest them for subsequent flights.

Initially the data gathering would be done in a way that does not distract any pilot.  Ideally, we'd leave 
the probes on airplanes for numerous months without anyone even knowing besides the owners.

Software used:
* probably colab.google.com which is a Python notebook environment that makes deep learning easy and provides a farm of GPUs to crunch the neural net training (btw, Python notebooks such as this are great for many other
uses such as drawing graphs)
* neural net that is good at natural language (LSTM is the obvious choice, but these keep evolving, just
use the latest and greatest)
