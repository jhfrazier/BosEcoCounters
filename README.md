# BosEcoCounters

## Why?

Eco Counters are devices that provide cities with automated bicycle and pedestrian counting at a specific point. Counts are uploaded to an [easy to use site](http://eco-public.com/public2/?id=100023038) where you can create quick little bar charts and get daily, weekly, and monthly trends. If you want machine readable information, to build a dynamic tool, or to pull data in hourly and 15 minute increments you have to dig a little deeper. This page documents the counters in the Boston area and shares notes for working with them.

Right now there is only one installed. Cambridge installed it last year to count the number of bikes that pass along Broadway between Third and Ames. The Connect Historic Boston cycletrack may be getting one soon. 

## THANK YOU

- to Cambridge for installing the counter
- to the Helen and William Mazer Foundation for funding it
- to Eco Counter for developing one of the most robust bicycle and pedestrian counting systems in the world
- to [Chealion](https://github.com/Chealion) for documenting the Eco Counter API with their work on [yycbike](https://github.com/Chealion/yycbike). Most of this is lifted from there!

## General API notes
The Eco Counter website pulls from their API, which you can inspect using your favorite browser. You can make a request like so:
    
    http://www.eco-public.com/api/[API KEY]/data/periode/[ID]/?begin=YYYYMMDD&endYYYYMMDD&step=[NUMBER]
  
- Get the API key by inspecting traffic to the public counter page in your browser.
- Get the ID simply by looking at the public counter page's url.
- Enter in the date span that you want in the begin and end field.
- The step ID field requests data in either daily [4], hourly [3], or 15 minute increments [2]

Here's an example request:

	http://www.eco-public.com/api/cw6Xk4jW4X4R/data/periode/102023038?begin=20161001&end=20161002&step=3

This is requesting hourly eastbound bike counts from Cambridge's Broadway counter for October 1st.

You can also get some general information en français about a counter in question:

	Data Set Names for Installation:
   	http://www.eco-public.com/api/cw6Xk4jW4X4R/counter/channels/[ID]
    	Public Page Details:
	http://www.eco-public.com/api/cw6Xk4jW4X4R/public/page/[ID]

## Information for counters in the Boston Area

Installation Name |     ID    |     API key    | Start Date
------------------|-----------|------------|------------
**Broadway/Cambridge**  | 100023038 | cw6Xk4jW4X4R | Mid-day, June 23rd, 2015
Bikes Westbound  | 101023038 | 
Bikes Eastbound  | 102023038 | 
**Connect Historic Boston?**  | tbd | tbd | 2017 at the earliest

