---
layout: post
title: Melville Cruise, Day 03
---

{{ page.title }}
================

<p class="meta">16 Sep 2014 - Pacific Ocean, West of Astoria, OR</p>

### Last two day's events

#### CTD Profiles
  * Performed several CTD (conductivity, temperature, density) casts to measure
    the ocean sound speed profile (SSP). With an accurate SSP we can predict
    how the ocean will affect the sound that we send out and that the array will
    receive.  For the first cast, we lowered it to nearly the bottom at 2850
    meters (about 2 miles).  
![CTD and water sample rig]({{site.url}}/images/2014-sep/############.jpg)
    The sound speed doesn't change much below 1000 meters despite what happens
    near the surface.  To save time on subsequent CTD casts, we only measure the
    first 1000 meters and then use an average of the first measured SSP and
    historical data to fill in the remainder of the profile.  The following is
    the raw SSP from the first cast near the array location.  
![SSP near array]({{site.url}}/images/2014-sep/ssp-near-array.jpg)
    You can interpret the line as the sound speed being greatest near the
    surface (depth near 0 meters) due to the higher temperature, and then it
    decreases at middle depths due to lower temperature, but at large depths,
    sound speed increases again due to the increasing density of the water. It's
    an interplay between salinity, sound speed, temperature, and density.

  * I setup a ray tracing calculation. This is when you imagine lasers pointed in
    many different directions in the ocean that change direction according to
    the sound speed (refraction).  Think of how water makes things look
    stretched or out of place; that is refraction of light.  This is a picture
    of a ray trace calculation for the ocean sound speed profile that we
    measured.
![Ray trace]({{site.url}}/images/2014-sep/########.jpg)
  * The weekly safety drill.  This time we practiced putting on survival suits
    and gathering at the life rafts.  The crew calls them Gumby suits for good
    reason.
![Gumby suits]({{site.url}}/images/2014-sep/gumpy-suits-small.jpg)

### Today's Events
  * Use a ray-trace to compute the phase and group speed for sound in this ocean
    at 3.5 kHz (low end of our array band). This required integrating the ray
    paths for path-length and also computing travel time along the ray. To
    calculate group velocity, the horizontal distance between source and
    receiver is divided by the ray travel time.  
![Phase speed vs Group speed]({{site.url}}/images/2014-sep/######.jpg)
