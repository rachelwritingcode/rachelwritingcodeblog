---
title: Python Package Repositories & Supply Chain Attacks 
layout: post
author: Rachel Wang
---

>"Open source code repositories like PyPI and npm are increasingly being targeted by threat actors"

We are still gearing up for the upcoming Introduction to Python Workshop series for Cyber Security Professionals and while I have Python on my mind, it is uncanny timing that news broke out this week
about [malicious Python packages on PyPI](https://thehackernews.com/2022/08/10-credential-stealing-python-libraries.html). I was listening to [Cyber Security Today podcast](https://www.itworldcanada.com/article/cyber-security-today-august-10-2022-bad-apps-are-found-in-the-pypi-repository-six-backdoors-are-used-in-a-gangs-cyber-attacks-a-new-botnet-found-and-more/497104) and researchers at Check Point Software reported the vulnerabilities. These affected packages harvested developer passwords and API tokens.

According to the podcast, "open source code repositories like PyPI and npm are increasingly being targeted by threat actors are using the software supply chain as actor vectors". I did a bit of research and according to [this white paper](https://www.cisa.gov/sites/default/files/publications/defending_against_software_supply_chain_attacks_508_1.pdf) by CISA on software supply chain attacks, this is not the first occurence of an attack on the Python package index. In 2018, researchers also discovered 12 malicious Python libraries uploaded on PyPI.

In this recent attack, the threat actor used a technique called ["typosquatting"](https://www.kaspersky.com/resource-center/definitions/what-is-typosquatting) which tricks developers into downloading malicious python packages with common misspellings. Developers were lured into believing they were downloading django a popular web framework. This is not the only technique that threat actors will use to exploit the open source packages, threat actors will also target existing packages and infect them with malicious code. I recommend reading this paper by Meier et al., ["Backstabber’s Knife Collection: A Review of Open Source Software Supply Chain Attacks"](https://arxiv.org/abs/2005.09535) which goes into depth about how open source projects are vulnerable and exploited by threat actors. Meier et al. state that a "single open source package may be required by several thousands of open source software projects which make open source packages a popular target for software supply chain attacks". 

I wanted to find out more about what this means for organizations. How do we mitigate risk in software supply chain attacks? CISA's white paper outlines some preventative measures that organizations can take in order to prevent supply chain attacks. 


>"Due to the difficulty of mitigating consequences after a software supply chain attack occurs, network defenders should observe industry best practices before an attack has occurred". --- [CISA](https://www.cisa.gov/sites/default/files/publications/defending_against_software_supply_chain_attacks_508_1.pdf)


In the context of secure software development, CISA recommends some of the following best practices:

    ✅ Incorporate secure software development practices in all phases of SDLC.
    ✅ Identify weaknesses and vulnerabilities in source and compiled code through evaluation methods such as testing (automated code analysis tools etc.).
    ✅ Actively identify and disclose vulnerabilities.
    ✅ Maintain a vulnerability response program.
    ✅ Use proactive exploit mitigation technologies in code.
    ✅ Enable patch management.
    ✅ Develop, maintain and use approved software suppliers.


This is not an exhaustive list of preventative measures, CISA's whitepaper also outlines the implementation of a risk management program as well as security engineering frameworks. Are there any best practices missing from this list that your organization implements? 

One takeaway from Meier et al. is, "despite raising general awareness among stakeholders, countermeasures must be more accessible and, where possible, enforced...to prevent open source software supply chain attacks". My interpretation of this is, developing secure software is beyond just countermeasures, it is also part of an organization's culture to proactively mitigate risk from all levels.

If you're interested to find out more, you can read the full white paper from CISA [here](https://www.cisa.gov/sites/default/files/publications/defending_against_software_supply_chain_attacks_508_1.pdf) and paper by Meier et al. [here](https://arxiv.org/abs/2005.09535). I will be sharing more updates on the upcoming Python workshop series soon, so stay tuned! 

Cheers! 👋

<br>

----

#### References:

Cybersecurity and Infrastructure Security Agency. (2021). Defending Against Software Supply Chain Attacks. https://www.cisa.gov/sites/default/files/publications/defending_against_software_supply_chain_attacks_508_1.pdf

Meier, M., Ohm, M., Plate, H., & Sykosch, A. (2020). Backstabber's Knife Collection: A Review of Open Source Software Supply Chain Attacks. The 17th Conference on Detection of Intrusions and Malware & Vulnerability Assessment (DIMVA). https://arxiv.org/abs/2005.09535
