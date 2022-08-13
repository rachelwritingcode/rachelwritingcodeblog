---
title: Python Package Respository & Supply Chain Attacks 
layout: post
author: Rachel Wang
---

>"Open source code repositories like PyPI and npm are increasingly being targeted by threat actors" --- Cyber Security Today Podcast

We are still gearing up for the upcoming Introduction to Python Workshop series for Cyber Security Professionals and while I have Python on my mind, it is uncanny timing that news broke out this week
about [malicious Python packages on PyPI](https://thehackernews.com/2022/08/10-credential-stealing-python-libraries.html). I was listening to [Cyber Security Today podcast](https://www.itworldcanada.com/article/cyber-security-today-august-10-2022-bad-apps-are-found-in-the-pypi-repository-six-backdoors-are-used-in-a-gangs-cyber-attacks-a-new-botnet-found-and-more/497104) and researchers at Check Point Software reported the vulnerabilities. These affected packages harvested developer passwords and API tokens.

According to the podcast, "open source code repositories like PyPI and npm are increasingly being targeted by threat actors are using the software supply chain as actor vectors". I found a [white paper](https://www.cisa.gov/sites/default/files/publications/defending_against_software_supply_chain_attacks_508_1.pdf) written by CISA on software supply chain attacks and this is not a unique incident. In 2018, researchers also discovered 12 malicious Python libraries uploaded on PyPI. As I put together curriculum to teach Python, installing third party packages from PyPI, is one of the topics to be covered. I think it will be important for participants to be aware of these types of attacks as they develop their Python skills and consider using open source dependencies for their own projects.

Threat actors commonly use a technique called ["typosquatting"](https://www.kaspersky.com/resource-center/definitions/what-is-typosquatting) which tricks developers into downloading malicious python packages with common misspellings. In the 2018 PyPI attack, developers were lured into believing they were downloading django, a popular web framework. I really recommend reading this paper by Meier et al., ["Backstabber’s Knife Collection: A Review of Open Source Software Supply Chain Attacks"](https://arxiv.org/abs/2005.09535) which goes into depth about how open source projects are vulnerable and exploited by threat actors. They state that since "open source packages may be required by several thousands of open source software projects, it makes it a popular target for software supply chain attacks". 

While we continue to see these types attacks in the open source community, I questioned how organizations could mitigate the risk in software supply chain attacks. CISA's white paper recommends some preventative measures however, they highlight the usage of best practices is important to prevent rather than respond to security incidents.


>"Due to the difficulty of mitigating consequences after a software supply chain attack occurs, network defenders should observe industry best practices before an attack has occurred". --- [CISA](https://www.cisa.gov/sites/default/files/publications/defending_against_software_supply_chain_attacks_508_1.pdf)

CISA recommends some of the follow countermeasures:

    ✅ Incorporate secure software development practices in all phases of SDLC.
    ✅ Identify weaknesses and vulnerabilities in source and compiled code through evaluation methods such as testing (through usage of automated code analysis tools etc.).
    ✅ Actively identify and disclose vulnerabilities.
    ✅ Maintain a vulnerability response program.
    ✅ Use proactive exploit mitigation technologies in code.
    ✅ Enable patch management.
    ✅ Develop, maintain and use approved software suppliers.


This is not an exhaustive list of countermeasures, CISA also recommends the implementation of a risk management program and security engineering frameworks. While I was reading this, I connected it back to Meier et al. who stated, "despite raising general awareness among stakeholders, countermeasures must be more accessible and, where possible, enforced...to prevent open source software supply chain attacks". My interpretation of this is, developing secure software is beyond just countermeasures, it is also part of an organization's culture to proactively mitigate risk from all levels. This means investing resources to develop a cyber security program and ecosystem that supports secure software development.

If you're interested to find out more, you can read the full white paper from CISA [here](https://www.cisa.gov/sites/default/files/publications/defending_against_software_supply_chain_attacks_508_1.pdf) and paper by Meier et al. [here](https://arxiv.org/abs/2005.09535). I will be sharing more updates on the upcoming Python workshop series soon, so stay tuned! 

Cheers! 👋

<br>

----

#### References:

Cybersecurity and Infrastructure Security Agency. (2021). Defending Against Software Supply Chain Attacks. https://www.cisa.gov/sites/default/files/publications/defending_against_software_supply_chain_attacks_508_1.pdf

IT World Canada. (2022, August 10). Cyber security today, August 10, 2022. Retrieved August 10, 2022, from https://www.itworldcanada.com/article/cyber-security-today-august-10-2022-bad-apps-are-found-in-the-pypi-repository-six-backdoors-are-used-in-a-gangs-cyber-attacks-a-new-botnet-found-and-more/497104 

Kaspersky. (2022, March 30). What is typosquatting? – definition and explanation. www.kaspersky.com. Retrieved August 10, 2022, from https://www.kaspersky.com/resource-center/definitions/what-is-typosquatting 

Meier, M., Ohm, M., Plate, H., & Sykosch, A. (2020). Backstabber's Knife Collection: A Review of Open Source Software Supply Chain Attacks. The 17th Conference on Detection of Intrusions and Malware & Vulnerability Assessment (DIMVA). https://arxiv.org/abs/2005.09535

Lakshmanan, R. (2022, August 10). 10 credential stealing python libraries found on Pypi Repository. The Hacker News. Retrieved August 10, 2022, from https://thehackernews.com/2022/08/10-credential-stealing-python-libraries.html 