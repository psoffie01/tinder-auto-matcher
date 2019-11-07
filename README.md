# Tinder Auto-Matcher

<p align="center"><img src="https://user-images.githubusercontent.com/9092290/68332558-53ac7080-00d7-11ea-920c-aea6b49972e7.png"></p>

## Overview
The goal of Tinder Auto-Matcher is to dehumanize as much as it can social interactions. This is achieved by automatically
liking back people who liked you Tinder to create a match without having to swipe one second. The next step would be to
send you an email everyday with recapitulation of today's matches.

## Usage
- First you need your Tinder's authentication token. Log in to [tinder.com](https://tinder.com), open the developer console, filter by XHR
  and find a request with an _X-Auth-Token_ header in the request headers. Save its value.
- Write the _X-Auth-Token_ value in the token key in Tinder.AutoMatcher/appsettings.json.
- Install [.NET Core 3.X](https://dotnet.microsoft.com/download).
- Finally, `dotnet run -p Tinder.AutoMatcher` to launch the worker.

## How does it work?
Tinder has a section where one can see the blurred pictures of the people who liked you.
![tinder-likes-blurred](https://user-images.githubusercontent.com/9092290/68334140-42189800-00da-11ea-85aa-bcf4ea8392d3.jpg)

However the Tinder API send unblurred pictures and the blurring is computed on the client side.
Thereby, you can see the real pictures just by disable some CSS rules. These pictures are in very low definition though.
<p align="center"><img src="https://user-images.githubusercontent.com/9092290/68334139-42189800-00da-11ea-976d-8a786a783e35.jpg"></p>

This project works by saving the ids of the "blurred" images and then finds them in your recommendations feed.

## F.A.Q
**Q:** I didn't get any match even tough Tinder tells me that I got X+ likes!?

**A:** Several reasons could explain that:
- These users are now out of range
- They are not in your elo anymore
- You swipe them left when you were swiping like a muggle


**Q:** Son, how did you meet your girlfriend?