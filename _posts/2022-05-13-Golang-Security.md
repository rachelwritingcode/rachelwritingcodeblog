---
title: Golang and Malware
layout: post
author: Rachel Wang
---

I thought I'd write a different flavour of blog post today and share my experience presenting about Golang malware in my cyber security class. In recent years, all the reasons why developers love Go are the same reasons why threat actors choose Go to write malware. The efficiency of the language, the ability to target all operating systems and the networking tools available in Go, make it a favourite amongst malware developers. We've seen all sorts of malware written in Go including ransomware, RATs and backdoors. What brought this issue to my attention was this [news article](https://www.zdnet.com/article/go-malware-is-now-common-having-been-adopted-by-both-apts-and-e-crime-groups/) about the "2,000% increase of new malware written in Go over the past few years". I thought to myself, "that's wild! 2000%?! What is going on with Golang and malware"? Before 2019, malware written in Go was a "rare occurence".

<br>

A key report that drove my research was written by Intezar Labs, which you can find [here](https://www.intezer.com/blog/malware-analysis/year-of-the-gopher-2020-go-malware-round-up/). This report breaks down the types of malware, threat actors and common attack vectors. What alarmed me the most was the extent that threat actors will go create attractive malware campaigns for unsuspecting targets. One attack that I covered in my presentation was the ElectroRAT malware attack. The threat actors created an extensive marketing campaign to target cyptocurrency users. They even hired crytocurrency influencers to attract victims. According to this [news article](https://cyware.com/news/electrorat-yet-another-golang-multi-platform-malware-12406d32) "The attackers lured cryptocurrency users to download trojanized applications by promoting them on cryptocurrency and blockchain-related forums, such as bitcointalk and SteemCoinPan, as well as on social media networks". 

<br>

Intezar labs, reports that Go malware will continue to increase. Malware written in Go is elusive to Antivirus programs and cyber security researchers find it challenging to analyze. Google built Go for the cloud, and as a result, attacks in the cloud are predicted to increase as more assets are stored there. I have a list of research references I used in my presentation slides, you can find a link to them [here](https://docs.google.com/presentation/d/1vMoJk-ybBnkJ7ATxASoPPo734Hw8i3n-sfLdbZQB6Ac/edit?usp=sharing). You'll also find that I summarize the key points of Go malware and provide my own insights on how to mitigate risk, using the Lockleed Martin cyber kill chain.  

<br>

On the topic of security, I'd also like to write a future post about secure coding practices. Last year at the [Women Who Go Toronto](https://www.meetup.com/women-who-go-toronto/events/278557652/) meetup we discussed a version of the [The Go Language Guide, Web Security & Go ](https://info.checkmarx.com/hubfs/Ebooks/The_Go_Language_Guide_Web_Application_Secure_Coding_Practices_OWASP_08.17.20.pdf). Since then, there's a been a renewed version of the whitepaper found [here](https://info.checkmarx.com/hubfs/GOwhitepaper0504.pdf) which I'd like to revisit. Stay tuned for more! 

Cheers! 👋