# av-doc
Documentation for AV at HasGeek events

This documentation will serve as a guide to deploy a basic A/V setup at an external event or for a single track event.


# Preparing the Laptop/Computer

The computer is the most crucial part of the setup and needs preparation and testing beforehand. The main computer used for streaming has to be powerful enough to encode three 1080p 60fps streams simultaneously, while also producing a stream for online viewers and recording to disk.

## MacBook Pro

MacBook Pros can be used as the main machine, but paired with the right broadcasting & recording software, as well as the right capture cards. Remember that MacBooks cannot have external drivers installed, so the compatibility is limited compared to Windows.


## Linux

We have not explored Linux as an option, but professional broadcast studios have known to use FreeBSD or CENTOS to run their production software. This setup would need end to end integration of equipment such as SDI or NDI and some advanced technical expertise.

## Windows 10

Windows 10 works as the most versatile and stable setup for streaming. Windows has many options such as Xsplit, OBS, Wirecast and more. XSplit has proved to be the best balance between usability for relatively inexperienced users and customizability to get a good stream.

### The following software are needed to run the setup:

1. A browser, preferably Google Chrome to control the stream and to keep an eye on the chat
2. Xsplit/OBS/Wirecast
3. Elgato software and drivers as needed
4. Epiphan drivers
5. Avermedia drivers (if using)

**Note that as of April 2019, Elgato has experimental support for using two of the same brand capture cards in one machine. This does cause issues, but can quickly be resolved by taking care to plug the two devices in two separate USB Root hubs**

### Graphics support

Running a good livestream involves customising what the viewers can see instead of just two video streams side by side. Some ways we can customise the livestream:

1. Adding the brand and HasGeek TV logos to the stream. The convention here is to add the HasGeek/HasGeek TV logo on the right bottom corner and then the brand logo on the left bottom corner. The logos have to be moved up among the layers to make sure that they are not being blocked by the video streams.
2. Adding transitions between scenes. Often you’ll be setting up multiple scenes such as speaker only, slides only, audience Q&A etc. Transitions are added between these scenes. Currently, we’ve settled on the ‘Fade’ transition for 700ms.
3. Keep intro and outro posters ready. These are posters which fit the full screen, with details about the session and the event where it’s recorded. The experiences of audience online and at the venue is vastly different, with online viewers missing a lot of context on happenings at the venue. For instance, we’ve had stretching sessions at our events before and this has confused online viewers. It helps to add context about the session happening a few mins before the session, so the expectations are set. Similarly, transitions added before and after breaks, and non recorded sessions keep the audience informed. For samples on these, check the thumbnails of videos in 2018.

### Setting up capture cards

If using a desktop PC, connect the external capture cards to the ports on the back of the computer. Use the ports which have a red, blue or yellow marking in them, since these indicate the fastest ports. Alternatively, if you see a USB C port, avoid it unless you are sure about the USB C standard it uses.

For a laptop, the options are much more limited. If you find a USB C port, check for a lightning symbol next to it, as this indicates a Thunderbolt 3 port. This port will deliver the maximum bandwidth, at about 20Gbps, when used with a thunderbolt dock. You can also use older USB C hubs, but have to be tested more than usual.

When using a USB Hub, try to pair devices to the same port, which have opposite requirements for bandwidth. For example, a USB 3.1 Capture card pairs with a USB Audio interface, since the audio interface most likely runs on USB 2.0. These two would work together much better than two USB 3 capture cards.

Label the capture cards according to the usage scenarios. If a capture card can only deliver lower frame rates or resolution, it’s best delegated to a stream which won't need that much attention. Slides are always put on lower frame rates, since the content will not refresh that quickly. The speaker feed on the other hand, is a high frame rate feed, thus requiring better capture cards.

#### Setting up Xsplit with capture cards

In Xsplit, add a new video capture source. If you don't see your capture cards listed, check if the drivers are correctly installed and make sure that the video feed is showing up in the OEM capture software (Elgato Game Capture for instance). 

Next, label them as per the use case. Remembering which feed you plugged into which capture card is hard to remember, and even more difficult to handover to someone.

Resize the feeds as needed. Try to keep the experience similar to what would be at the venue, such as matching the orientation of the camera relative to the screen as on the feed. A collection of scenes is called as a presentation on Xsplit. You can save this presentation as a file and use it for later.

**Setting the Audio**:

Connect an audio source to the computer and in settings > audio, set the audio source to the device you connected. Turn off any other options and set the audio preview to the speaker/headphones you’re using. 

Next, in the presentation screen, you’ll see the audio indicator. Adjust the output from the audio source till the small thin orange bar below the indicator reaches the max level. Adjust till only when the audio peaks, the level hits the edge. What you hear over the headphones is also dependent on the headphone output volume you’ve set. Keep this at 50% or 75% when testing to hear like how a person would be hearing the audio.

**Eliminating noise:**

1) Noise is most likely due to poor grounding in the electrical supply. Make sure that any source of power is coming from a single point, such as the UPS point at the venue. 

2) It can also be due to rouge audio sources such as the cameras used. This can be fixed in the video source settings and setting the audio to none. Do not refresh after doing this, since refresh will reset the settings. 

3) Noise can also be due to bad cables. To eliminate this, try unplugging and listening for the noise. When you’ve isolated the source, swap cables to check the problem. Make sure that you’re using similar types of cables, XLR-XLR. The 1/4” cables are not balanced and will have more noise than XLR.

4)Also check with headphones through a mixer and the audio interface as well.

**Setting up the microphones**

The current model of mics we use at events is GTD Audio. There are two types of mic kits we have:

1) 2 collar + 2 hand mics
2) 4 hand mics

Each kit comes with a 4x1 mic receiver which talks to 4 mics and gives output from them. Each microphone has to be paired with a receiver. The configuration is done with groups and channels. Groups and channels can be thought of different spectra in the signals. Each group is divided into multiple channels.

To correctly configure the mics with the receivers, turn on the receiver first and all the microphones. Don’t connect any output yet.

1. Check that all the mics have pairings with a receiver.
2. No two mics should have the same combination of group + channel.
3. Avoid channels being too close to each other. For instance, start with Group 1 Channel 3, Group 1 Channel 6, Group 1 Channel 9 etc.
4. If two mics have the same configuration, you can end up with overlap of the audio signals. We've had a case were audio from one auditorium would feed into the other due to misconfigured microphones.
5. Pair the microphones in order as it’s continent for the operator. 
6. All microphone usage is not similar. Speaker mics will need much more control over volume, mute etc and will have to have separate controls.
7. Audience microphones on the other hand are used only for a fraction of the duration of the speaker microphones and hence can have coarse controls.
8. Each receiver can output individual mics over XLR or one receiver can mix and send all four channels through one out, 1/4” jacks.

Once the configuration is done, remember to replace the batteries with fresh ones. Swap batteries when they’re down to 30% capacity. Do not wait for the charge to run out completely. 

## Setting up video

There are 3 main feeds we need to capture:

1. Speaker’s slides
2. Audience camera
3. Speaker feed

Speaker feed (Face) and the audience camera will never have to appear on the projection, and hence will directly feed to the computer with capture cards. The speaker’s slides on the other hand will have to be copied twice for the projection + TelePrompTer.

To do this, we use a HDMI splitter or a switch. A switch allows you to mix outputs and inputs and change them on the fly, whereas a splitter will simply split the signal into two/three copies.

The slides are split first to provide a copy to the projection, one copy as the recording and one to the TelePrompTer. 


