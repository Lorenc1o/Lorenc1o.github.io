---
title: "Part I: Introduction to Air Traffic Management (ATM)"
date: 2023-07-10
categories: [ATC]
author: Jose Antonio Lorencio Abril
permalink: /posts/en/introduction-to-atm/
usemathjax: true
lang: en
es_link: /posts/es/introduction-to-atm/
toc:
    -
        title: Introduction
        url: '#intro'
    -
        title: The different aspects of Air Traffic
        url: '#air-traffic'
    -
        title: Why do we need ATC?
        url: '#why-atc'
    -
        title: Airspace Structures and Classification
        url: '#airspace-structs'
        subsections:
            - 
                title: ATS Routes
                url: '#ats-routes'   
            -
                title: Control Services
                url: '#control-services'
    -
        title: Conclusion
        url: '#conclusion'         
    -
        title: References
        url: '#references'
---

## Introduction {#intro}

I will be delving in the world of Air Traffic Management (ATM) and Control (ATC) in the near future[^1], and I will try to document my learning process in this blog. 

<div style="border:1px solid black; padding:10px; background-color: #A4DDFF;">
  'ATC is all the systems that contribute towards managing air traffic and the airspace that the air traffic flies in. The main purpose of ATC is to make sure that all this is done safely, efficiently and economically.'
  <br>
  <span style="float:right; font-weight:bold;">- The International Civil Aviation Organization</span>
  <br>
</div>

Let's break this down, to understand what this really means.

## The different aspects of Air Traffic {#air-traffic}

The most well-known and obvious aspects of air traffic are those directly involved in the flights and the airports. These are the ones that we can see and hear, and the ones that we are most familiar with. We can classify them into three groups:

- **Air traffic service providers**: these are the people that ensure the safety of the flights. They are the ones that control the air traffic, and they are the ones that provide the information to the pilots. They are the ones that we can hear in the radio.

- **Airspace management**: this is the part that deals with the airspace. It is the part that defines the different airspaces, and the rules that apply to them. It is the part that defines the routes that the flights can take, and the rules that apply to them.

- **Air traffic flow management**: is the regulation of air traffic in order to avoid exceeding airport or air traffic control capacity in handling traffic, and to ensure that available capacity is used efficiently.

But there are other aspects of air traffic that are not so obvious, and that are not so well-known. These are the ones that we cannot see or hear, and the ones that we are not so familiar with. For instance, there are several systems that are needed for the previous three groups to work properly. For instance, the most important ones are:

- **Communication systems**: these are the systems that allow the different actors to communicate with each other. They are the ones that allow the pilots to communicate with the air traffic controllers, as well as the the air traffic controllers to communicate with each other.

- **Navigation systems**: these are the systems that allow the pilots to know where they are. They allow the pilots to know the position and the direction of the aircraft.

- **Surveillance systems**: these are the systems that allow the air traffic controllers to know where the aircraft are. They are the ones that allow the air traffic controllers to see the aircraft, and they are the ones that allow the air traffic controllers to know the position of the aircraft.

And even given all these systems, there are yet more important systems that aid the previous ones:

- **Meteorological systems**: these are the systems that allow the air traffic controllers to know the weather conditions.

- **Aeronautical information systems**: these are the systems that allow the air traffic controllers to know the information about the flights.

- **Rescue systems**: these are special systems that are used when an aircraft goes missing or if there is a need for a rescue operation after an accident.

This whole ecosystem is what we call **Air Navigation Services** (ANS). It is the whole system that allows the aircraft to fly safely and efficiently. Air Traffic Control is the most visible part of Air Traffic Management and sits in the Air Traffic Service Providers group.

## Why do we need ATC? {#why-atc}

Let's go through a few situations, so that we can understand the need for ATC.

1. Picture an aircraft going from one airport to another. This aircraft is alone in the world. In this situation, there is no danger that the aircraft will collide with another plane.

2. Now, imagine the same aircraft going from one airport to another. Just before takeoff, the pilot sees another plane approaching the airport. Should the pilot take off anyway? He would probably asks himself questions like:
    - What is the speed of the coming plane?
    - What is its exact direction?
    - Will it land in the same airstrip I need for takeoff?
    - Is this plane in some kind of trouble or emergency landing?
Without an answer to these questions, taking off is a bet which could cost tons of money, materials and, the worst of all, lives. 

If the pilots of the two aircraft were able to communicate with each other, they could probably come to an agreement, and decisions could be made safely. 

3. However, that is still a fictional scenario. Reality is thousands of aircrafts are going in and out hundreds of airports. It is not rare at all to have a situation in which 15 aircrafts want to land in the same airport, while another 6 are passing through the same aerial zone to go somewhere else. In addition, there might be a couple helicopters patrolling the area, as well as another 12 airplanes on the ground, in the wait to go to different places: some of them will take off soon, some others will park the plane in their designated area, or must be moved to the area where the hangars are. 

Not only this, but the aircrafts are of different types. They can be **big long haul passenger carrying aircrafts**, or **training aircrafts**, or **short hop commuter aircrafts**.

<figure>
<img src="/assets/images/ATM/passenger_aircraft.png" alt="A passenger aircraft" width="300" class="centered-image"/>
<figcaption style="text-align-last:center; font-weight:bold;">A big long haul passenger carrying aircraft<a href="#ref2" id="ref2inline"><sup>2</sup></a>.</figcaption>
</figure>
<span style="color:white" hidden>[^2]</span>


<figure>
<img src="/assets/images/ATM/training_aircraft.jpg" alt="A training aircraft" width="300" class="centered-image"/>
<figcaption style="text-align-last:center; font-weight:bold;">A training aircraft<a href="#ref3"><sup>3</sup></a>.</figcaption>
</figure>
<span style="color:white" hidden>[^3]</span>

<figure>
<img src="/assets/images/ATM/commuter_aircraft.avif" alt="A commuter aircraft" width="300" class="centered-image"/>
<figcaption style="text-align-last:center; font-weight:bold;">A short hop commuter aircraft<a href="#ref4"><sup>4</sup></a>.</figcaption>
</figure>
<span style="color:white" hidden>[^4]</span>

This situation can rapidly become chaotic and it would be bold to think that the pilots could solve any possible issue, and coordinate with each other effectively in such a complex scenario, just by talking to one another.

There is the need for a mechanism that can ensure:

- Planes don't collide.
- Planes arrive to where they want to go.
- With the side objective to minimize the delay.

Note also that the problem is not just happening at the surroundings of the airports, but this kind of complex scenario can occur in the sky, where many aircrafts can be flying from one place to another, at speeds of more than 1000 km/h and with limited visibility.

A mechanism that can provide a solution for all these problems needs to have a big picture of what all aircrafts are doing, so that coordination can be done effectively and safely.

This immense responsibility lies on the shoulders of air traffic controllers. To this end, they must:

1. Ensure that the aircrafts are safely separated from one another both in the air and the ground.
2. Enable the aircrafts to meet their objectives, orderly, and with the least amount of delay possible.

In the characterization of air navigation services that we did before, we saw that the ATC is part of a wider system, the Air Traffic Services. Apart from ATC, this system is formed by the Flight Information System, the Advisory Services and the Alerting Services, which we will cover later. It is worth noting that an air traffic controller can provide one or more of these services at the same time, depending of where they work, how large the system is, how complex the air space is,...

## Airspace Structures and Classification {#airspace-structs}

The **airspace** is any specific three-dimensional portion of the atmosphere[^5]. It can be understood in terms of substructures, and, at the most basic level, it can be divided into two categories:

- **Controlled airspace**: The controlled airspace refers to the segments of airspace that are monitored and controlled by air system control systems.
- **Uncontrolled airspace**: refers to the rest of the airspace, that is not controlled.

ATC takes several factors into account to work out where and what service needs to be provided:

- Number of aircrafts using that segment of space.
- The activities that these aircrafts are performing (landing, takeoff,...).
- Types of aircrafts involved.
- Weather conditions.
- Terrain.
- ...

When ATC has determined where a control service is needed, the next step is to define how high, how wide, and what shape should those segment in the airspace be. Once this is done, these segments are designated as controlled airspace.

In the following figure, I depict a 2D analogy:

<figure>
<img src="/assets/images/ATM/airspace_example.png" alt="A 2D airspace definition example" width="500" class="centered-image"/>
<figcaption style="text-align-last:center; font-weight:bold;">A 2d airspace definition example.</figcaption>
</figure>

In this analogy, we can see the Earth, and above it, the airspace. In the left, the airspace is completely uncontrolled, and in the right, we can see a possible definition for a controlled airspace, after all the considerations explained before are taken into account.

Now, how are these segments or chunks in real life? Around airports, the chunks usually start at ground level, and go up to 4000 ft (~1.2 km), but in some cases they can go up to 10000 ft (~3 km). This kind of airspace around an airport is called a <span style="color:red"> control zone</span>. 

Sitting just in top of the control zone, there is another chunk of space, called a <span style="color:#0092EA"> terminal control area</span>. These areas may have more than one airport below it and it is in this kind of airspace where aircrafts are climbing out of the airports to get to their cruising levels, or descending to land and will be positioned into a landing sequence by ATC.

Joining the terminal control areas together, we find corridors of airspace, called <span style="color:#EA9800">airways</span>. The airways are around 10 nautical miles (~18.5 km) wide.

The airways, together with the terminal control areas, are part of what is called a <span style="color:#C300EA">control area</span>. 

Sometimes, ATC recognizes that a very large segment of airspace needs to be controlled, and instead of having airways joining the different terminal control areas, they declare the entire upper airspace between the airports as <span style="color:#C300EA">control area</span>. 

No matter how these chunks of airspace are configured, they are all contained within a larger chunk of airspace: a <span style="color:#17A900">flight information region</span>. Sometimes, these regions are so big that a horizontal split is made, and the top part is called the <span style="color:#17A900">upper information region</span>, while the bottom part keeps the name <span style="color:#17A900">flight information region</span>. This split is made for practical reasons, so that the upper part can be managed by an ATC unit, and the lower part by another ATC unit.

### ATS Routes {#ats-routes}

To help pilots and controllers identify how an aircraft plans to go from point A to point B, **Air Traffic Service routes (ATS routes)** are defined, joining together several locations. These are like the highways of the sky. There are hundreds of ATS routes defined, and states publish the structure of their airspace and the ATS in a document called the **Aeronautical Information Publication**, and they make it available in aeronautical charts.

### Control services {#control-services}

At this point, we have defined the chunks of airspace that are controlled, but we still need to determine what kind of control the controllers will be providing to the aircrafts that are flying inside this airspace. To this end, we need to know the different ways to fly:

- When students pilots first learn to fly, they navigate from one place to another by using a map and looking at the cockpit window, identifying landmarks along their route. They can only fly if the weather is good enough for them to see a fair distance out the window.
This type of flying is known as <span style="color:#0092EA"> flying under VFR (visual flight rules)</span>. It is not just student pilots who do this, but many general aviation pilots fly like this when the weather allows it.

- When a pilot flies mainly using the navigational instruments in the aircraft, they are <span style="color:red"> flying under IFR (instrument flight rules)</span>. Every airline pilot must be qualified to fly under these conditions.

Now that we know the different kinds of flight rules under which a flight can fly, we can delve into what services do controllers provide inside the controlled airspace chunks. To do this, a classification of each chunk is done:

- **Class A airspace**: only IFR flights are allowed to fly in that chunk, and the controllers will make sure that they are all safely separated.
- **Class B airspace**: both IFR and VFR flights are allowed into the airspace chunk, and they will all be separated from each other by ATC.
- **Class E airspace**: both IFR and VFR flights are allowed into the airspace chunk, but only IFR flights will be separated from other IFR flights by ATC, while VFR flights must keep themselves separated from the rest of the flights. ATC will only tell IFR flights about VFR when they are near to them.
- **Uncontrolled airspace (Class G)**: in the uncontrolled airspace, aircrafts are allowed to fly VFR and IFR, but it is the responsibility of the flight crew to ensure their separation from other aircrafts. The Air Traffic Services does not (of course!) completely ignore them, and pilots are provided by information that might be useful for their safety, such as weather information, traffic in their surroundings that may interfere with them, or conditions at the airport in which they plan to land.

The following table[^6] summarizes the different airspace classes:

| Class | Type of Flight | Separation Provided | Service Provided |
|-------|----------------|---------------------|------------------|
| A | IFR only | All aircraft | Air traffic control service |
| B | IFR | All aircraft | Air traffic control service |
|  | VFR | All aircraft | Air traffic control service |
| C | IFR | IFR from IFR, IFR from VFR | Air traffic control service |
|  | VFR | VFR from IFR | 1) Air traffic control service for separation from IFR 2) VFR/VFR traffic information service (and traffic avoidance advice on request) |
| D | IFR | IFR from IFR | Air traffic control service, traffic information about VFR flights (and traffic avoidance advice on request) |
|  | VFR | Nil | IFR/VFR and VFR/VFR traffic information (and traffic avoidance advice on request) |
| E | IFR | IFR from IFR | Air traffic control service and, as far as practical traffic information about VFR flights |
|  | VFR | Nil | Traffic information as far as practical |
| F | IFR | IFR from IFR as far as practical | Air traffic advisory service; flight information service |
|  | VFR | Nil | Flight information service |
| G | IFR | Nil | Flight information service |
|  | VFR | Nil | Flight information service |



## References {#references}

[^1]: I will start this journey via the free courses delivered by [Eurocontrol Learning Zone](https://learningzone.eurocontrol.int/ilp/pages/internal-dashboard.jsf?menuId=1107&locale=en-GB#/?dashboardId=7).

[^2]: <a id="ref2"></a> Passenger Aircraft Image: [source](https://www.aerotime.aero/articles/25619-top-10-largest-passenger-aircraft-that-never-flew)

[^3]: <a id="ref3"></a> Training Aircraft Image: [source](https://www.piper.com/models/trainer/)

[^4]: <a id="ref4"></a> Commuter Aircraft Image: [source](https://www.google.com/imgres?imgurl=https://images.theconversation.com/files/484951/original/file-20220915-37168-hs6bel.jpg%3Fixlib=rb-1.1.0&q=45&auto=format&w=754&fit=clip&tbnid=zCpsT639CmoG8M&vet=12ahUKEwjK-ujPqYaAAxUKkicCHehbAXwQMygDegUIARDFAQ..i&imgrefurl=https://theconversation.com/electric-planes-are-coming-short-hop-regional-flights-could-be-running-on-batteries-in-a-few-years-190098&docid=5jPsE1lN_vKsnM&w=754&h=424&q=short hop commuter aircraft&ved=2ahUKEwjK-ujPqYaAAxUKkicCHehbAXwQMygDegUIARDFAQ) 

[^5]: Visit [Airspace in Wikipedia](https://en.wikipedia.org/wiki/Airspace).

[^6]: Table adapted from [this blog in SkyBrary](https://skybrary.aero/articles/classification-airspace)