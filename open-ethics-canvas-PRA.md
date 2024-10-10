# The Open Ethics Canvas v1.0.2   <!-- omit in toc -->
modified: 2021-11-16

---

- Prepared For: Responsible AI, Open University, Assignment 2
- Prepared By: Bas Kaptijn (studentnumber 852500964)
- Date: 9-10-2024
- Version: 0.1 (initial working version)

---

## Contents  <!-- omit in toc -->

- [1. Scope](#1-scope)
- [2. Users](#2-users)
- [3. Training Data](#3-training-data)
- [4. Algorithms & Source Code](#4-algorithms--source-code)
- [5. Decision Space](#5-decision-space)
- [6. Key Stakeholders](#6-key-stakeholders)
- [7. Values & Interests](#7-values--interests)
- [8. Personal Data Processing](#8-personal-data-processing)
- [9. Components & Subprocessing](#9-components--subprocessing)
- [10. Failure modes](#10-failure-modes)
- [11. Explainability](#11-explainability)
- [12. Human in the Loop (HITL)](#12-human-in-the-loop-hitl)
- [13. Model Performance Metrics](#13-model-performance-metrics)
- [14. Decision Feedback & Objection](#14-decision-feedback--objection)
- [15. Impact Assessment](#15-impact-assessment)
- [16. Regulatory Landscape](#16-regulatory-landscape)
- [17. Mitigation](#17-mitigation)
- [18. Changes in Behavior](#18-changes-in-behavior)
- [19. Group Interactions](#19-group-interactions)
- [20. Comments](#20-comments)

---

## 1. Scope
- What is this product designed for?

The Personal Regulation Assistant (in the remainder of this canvas referred to as the "tool") is to be used by citizens for awareness building of needs for, knowledge sharing about, personal testing of and applying for governmental services like benefits, permits and exemptions, but also getting support or retrieval of your own information (GDPR right to data portability as best practice). Governmental services can be defined as broad, as it could also be internal services to be used by professionals within government only, or just giving information on a specific topic as has been agreed on how to describe it consistently (then there is nothing to apply for other than getting support for understanding, a complaint, feedback or change for request).

- What context does it operate in?

As a tool that a government can offer to citizens for interacting with them it operates within society as a whole.

## 2. Users

- What type of users does this product have?

The tool is intended for all citizens of a nation state, yet their ability and willingness will vary so we can distinguish certain groups of people the last one of which is not expected to use the tool:

1.    citizens that can and are willing to use the tool
2.    citizens that are willing but must be helped using the tool
3.    citizens that are not willing to use the tool because they prefer other ways of interaction with government
4.    citizens that are not willing to use the tool because they oppose interaction with government in general


- What are their roles?

There are citizens that use the tool for themselves or for others in a non-professional way and there are volunteers and professionals in non-governmental organizations as well as in government that use the tool to help citizens as well as for the purpose of their own work.

## 3. Training Data
- How was the training data collected?

There have only been paper and partly working prototypes. In general, official information on laws and to some extend explanatory information are publicly available but mostly not in a precise machine consumable form. Also, a lot of information on policies and decisions are often not freely available or even just missing, as in that, parts of it, especially how these came to be, has been lost. The training data will grow as the tool will get introduced for a minimal viable set of governmental services. As of yet, no service has adequately been described that training on qualitative data can take place. The Dutch healthcare benefit might be the first one to be published in a more precise rules as code kind of form. But how to add explainability to this remains an open research question as of this moment. The training data mostly will form a big rules-based expert system that will allow for variability where it needs a HITL. Within the content making / maintenance, which includes "executable" rules based on agreements like laws, policies and so on in a fine-grained manner, AI tools might get to be of use, but this is out of scope of the PRA project. The PRA tool envisioned using a chatbot based on client side LLM's, so not that large, but based on large LLM's, but after user research had to revert its strategy as people mostly do not want to have to chat for most functions of the PRA. Also at the time, the feasibility of using AI technology client side on devices as smartphones was found to be a problem. There was also a lack of qualitative data (though the commercial project Postbus 42 shows a promising path based on existing information). Besides the big expert system, that consists out of all agreements made in a collaborating society, which can also be seen as a Model Based AI solution, the PRA tool experimented with generative AI for two subfunctions:

1.    a smart search for matching questions to information citations in the content the PRA tool disseminates. This could be extended with real LLM's that apply RAG on content but is out of scope for now.
2.    a one-shot matching algorithm that tries to match a search string to governmental services using content on these services.

The training data for these functions are based on existing generic language datasets and the models for these experiments were made multilingual. The PRA tool can function without these smart functions however too by giving users other ways to search too limiting the risk of for instance bias and accuracy of the models that implement these functions. The most ethical considerations are with the quality and impact of the expert system that is made from all content (including rules, model-based AI) that is created and maintained by a large number of stakeholders. In a sense this can be seen as a smart AI system with a lot of HITL too.


- How do you ensure its representativeness?

Training data must be officially published through a governmental platform like as in envisioned with the Dutch website regels.overheid.nl (rules.government.gov) in compliance with officially published laws like in the Dutch website wetten.overheid.nl (laws.government.gov). Note that continental bodies might impose standardization and that continental wide official laws and rules also do apply and have their own publishing platforms. Also, there can be cross border relations between all these.

- Does your training dataset contain personal data?

No this is not allowed out of privacy considerations and because all content must be available online publicly and freely for transparency and the intended reuse of the official information by private organizations. So, at most only data of fictive persona's'. Note the PRA is intended for personal advice only, not for statistic research based on large datasets based on personal data.

- Who annotates the data and how quality is controlled?

There is not one team as the tool itself does not contain the content to be provided officially by governmental organizations that are responsible for the governmental services and that have to do this in compliance with national or continental regulations related to the governance of the tool. These regulations will need to specify how data is to be published and annotated and how quality is to be managed and also involves continuously addressing ethical aspects as far as this is not part of law / policy making and execution thereof it self (and note that most is). This will involve a necessity for national as well as continental bodies that overlook quality as also commonly is the case with governance relating to privacy laws.

- What is the data labeling process that you employ?

For content data this is to be standardized through standards around Rules as Code but also apart from this, the tool has an awareness building function for which content has to be labelled in certain ways. The proposal for this is to label data in such way, the content can be hierarchically grouped per governmental (public) service and linked to:

- an open but limitative standardized set of life events
- an open but limitative standardized set of non-controversial needs (aligning with nonviolent communication)
- references to official agreements for both the content itself as well as official content (agreements, rules, guidelines, explanation etc) about the content making and maintenance to be used. Actually, the content on the making and maintenance of content might be made accessible as a governmental service itself.
- metadata about versioning
- other metadata about the government (public) service (common name etc.)..
- responsible organizations for the government (public) service (both directly as indirectly higher up in hierarchy)

## 4. Algorithms & Source Code
- Do you use open or proprietary sources? Which?

Due to the tool mostly needs to build trust between citizens and with government through transparency and a high quality of explainability along with the high protentional for politicalization of its 'content the tool itself should be entirely open source.
 
- Who in the team is setting the heuristics/rules that influence the output?

There is not one team as the tool itself does not contain heuristics/rules which are part of the content to be provided officially by governmental organizations that are responsible for the governmental services and that must do this in compliance with national or continental regulations related to the governance of the tool. These regulations will need to specify how rules and heuristics are to be managed and also involves continuously addressing ethical aspects as far as this is not part of law / policy making and execution thereof itself (and note that most is). This will involve national as well as continental bodies that overlook quality of heuristic/rules as also commonly is the case with governance relating to privacy laws.

- How do you ensure the quality of used third-party codebases?

Governments in the end are responsible for making sure the organization that develops and operationalizes the tool for citizens in a member state do this according to governed architectural choices, which involves continuous hardening by testing and ethical hacking and involving the continuous due diligence of all third party codebases used.

- What is your process of making the key architectural choices?

The overarching architectural choices come from established bodies within government responsible for e-Government architecture, which will depend on the nation state implementing the tool. There can also be continent wide (like the EU) governance on the tool that prescribes architectural choices like is done for the European Digital Identity Wallets through the EiDAS 2 regulation and which promotes the realization of reference implementations in a public-private setting as well as demands member states to provide the tool for its citizens with their own official content. This also involves standardization on governance on how to create, disseminate and improve content which involves machine consumable rules methodically extracted from agreements (laws, regulations, policies, regional, local and personal decisions) specified in natural language.

## 5. Decision Space

- What exactly does the product do?

It helps users get aware of their needs and find information on governmental services that might help. It helps explaining these services. Using their personal information only in the tool on the client side (or on a centrally hosted version for which the user will have to need to log in with a high level of identity assurance), the users can get personalized advice, directly showing the impact services could have on their personal situation once the user gathered all information necessary, though in an effortless way through for instance improved verifiable credential wallets and or secure dataspaces / data platforms. The user can then decide to officially apply for (change in) services, after which the responsible organization takes over the interaction in which on most cases, given the envisioned high quality of content the advice is based on, it will quickly react with a formal decision the user can either accept or not accept and can get help for when necessary.

- Can you provide the list of all possible outputs?

No, this depends on the input

- How incorrectly supplied inputs are spotted?

This must be addressed to quality assurance before publication of content before the tool picks this up in production.

- Is there anomaly detection in place?

Not outside of what can be implemented in the content itself as this should also be in place outside of the tool, though it is not in place as a governmental service as far as we know. This has yet to be addressed. One can think of when the tool calculates an impact on a personal situation that is considered harmful and an anomaly, an escalation path for this is to be provided. This could also be defined and operationalized as a government service, and as the tool already will have to support the interaction between multiple changes within a person's situation this could be implemented. How the tool functions in relation to the interaction of multiple services must be elaborated on though. The tool itself could also implement anomaly detection for anomaly’s that point to the working of the tool itself not related to the content. This is not in place.

## 6. Key Stakeholders
- Who are the key stakeholders?

In a sense all citizens are key stakeholders. Yet those responsible for operationalizing the tool and for all content as well as the governance of all this are to be considered key stakeholders in terms of organizations where citizens are more the end users (though sometimes also working for key stakeholder organizations). This is pretty much all NGO’s and governmental organizations who all have their own responsibilities. They are all responsible for content. For the tool itself, key stakeholders are probably a certain ministry for each nation as well as bodies that are responsible for cross border governance (including standardization). Within the Netherlands, this would be the Ministry of Internal Affairs, which may delegate certain parts to other organizations.

- What influence do they have over the product?

How stakeholders (including citizens) have influence is to be determined through standardization and agreements as governance. Typically, the ministry responsible for the tool itself has most influence on the tool but will have to comply with cross border standardization for interoperability. Other organizations are responsible for content so have influence on this, yet this always is the execution of agreements with other stakeholders that have most influence. Citizens will only have indirect influence through mentioned stakeholder organizations and or politics.

- How do stakeholders interact with each other?

This should be part of the governance on content creation and maintenance, which includes rules and hooks into all the relevant decision-making processes for this. Any information, agreements like guidelines and such can be published as (internal) government services only intended for relevant professionals but can be governed in the same way as other governmental services. These determine how stakeholders are to interact.

- How is the power distributed?

This is entirely determined by law and the governance around rules and content and this particular PRA tool.

## 7. Values & Interests

- What values do stakeholders/users have?

At the core it is about integrative decision making within the whole of society, and the core value involved is Trust. Privacy, Transparency, Explainability, Accessibility and inclusiveness feed into Trust. Users also want simplicity, as complex knowledge easily overwhelms most people (even highly educated professionals).

- Where these values can clash or create tensions?

Feasibility is often an obstacle and as such enabler for all this. Transparency and explainability can also create tensions around topics that easily can get politicalized while the tool only supports personal conflict engagement and not resolving group conflicts such as political ones. But this is not unique for a tool as the PRA, as when content quality is good, it will only help in overcoming knowledge gaps and big problems that are created because of that. The best thing to do with conflicts is to engage with them effectively. The PRA tool is an essential tool for knowledge sharing and a starting point for decision making around conflicts. Inclusiveness can be troublesome when the tool is too rigid. The tool should allow for overriding agreements locally within established agreed bounds because tacit knowledge of stakeholders can make a difference sometimes and laws often allow for this explicitly, but in general the PRA tool should always allow for applying to services even when its advice seems to indicate it probably will be denied. Government should not automatically deny services without a HITL that evaluates a situation critically in interaction with the applicant that can let itself supported in this, to overcome this.

- What is known at the moment and how assumptions are tested?

User research on prototypes of the PRA revealed citizens would really like such a tool. It revealed why people do want to feel to have control and access to knowledge, they do not want to put effort into it. They just want to be able to get things done in an easy way while still having full insight and control which is a key focus for explainability, and UX. Professionals are worried about feasibility on the short term and also clueless as how to address something like the PRA in the complex context of the constellation of governments and their organizations within society.

- How can you align your technology to the values you want to support/people desire?

The tool entirely depends on the maintenance of agreements (from personal to global) and offering support for putting people in control to address their desires in relation to all these agreements.


## 8. Personal Data Processing

- Which personal data is collected by the product?

The product collects all data that is referenced in published content of governmental services for the purpose of the functions of the PRA tool. These references refer to standards (for instance in EU dataspaces) and ultimately to specific parts in published agreements like laws and policies from which it is clear the data has its purpose in.

- What is the purpose of collecting personal data?

personal advice on governmental services.

- How is this data processed? Used? Stored? Deleted?

Data loaded from sources and held locally (within a connected wallet) are processed client side for advice to the end user. No data is sent to servers apart from how the wallet itself operates up until an end user decides to apply for a government service in which case all relevant data is safely sent to the responsible organization by means of the wallet solution. The receiving organization acts as a verifier and servicing party that only keeps the data necessary to deliver the service. Data that is used for decision making does not have to be part of the data that is sent to the receiving organization when the data is verifiable and verifiably actual. 

Note that the current EiDAS regulation as well as the ARF do not support these kind of advanced functions where apps can act on locally installed wallet apps directly as a verifying party (and thus governed solution) and can determine data actuality (through revocation being supported) but moreover can automatically update a previously issued credential through some sort of subscription function and single sign on for one’s own data from a wide range of sources so the end user does not have to identify for each and every single credential all the time (one identification per usage of the tool itself for retrieving data should suffice whereas applying for services will involve one identification for all services being applied for in bulk). 

The wallet has to accept and hold data from the PRA tool as an issuer when the end user is applying for services, and there for all PRA tools must have been certified to be accepted as such. The PRA tool must read personal data out of verified EuDI wallets (request it) and issues personal data back into it during the use of the PRA tool. When the PRA tool app is stopped all personal data in the PRA tool (in memory) is forgotten in a secure manner. The PRA tool does not fetch/sends personal data in other ways. The PRA tool does fetch public non personal content about the governmental services it advises on which is publicly available. The PRA tool loads this information when needed and can automatically check for updates and update it's local cache of this information.


## 9. Components & Subprocessing
- Which third parties are engaged by the product?

possibly wallet providers, ICT organizations that work for stakeholders (yet watch out for power recentralization) for hosted services that receive applications, organizations that help stakeholders make and maintain content and so on.

- How do you evaluate the potential impacts of API on the quality of your product’s output?

The tool interacts directly with EiDAS 2 compliant verifiable credential wallets (in a broad sense as these also could include hosted data services) and indirectly with application receiving services that act as a verifiable credential verifier and or issuer. These all have API's that will have to conform to standards and are governed through the EiDAS regulation. The quality of the PRA tool depends on the quality of such wallets and the standardization and governance under EiDAS 2.

- How do you check the reliability of your data processing contractors?

Processing only takes place at governmental organizations that have the obligation to comply to standards and laws like the GDPR. This should be addressed within the governance framework applied probably like as in EiDAS 2.


## 10. Failure modes
- How are failures detected and monitored?

Too soon to tell. It is envisioned that anonymous usage statistics are collected (with the permission of end users) of the tool apart from applications.
Also anonymous statistics on applications for governmental services (what kind of application for what and when) can be collected. These statistics can be published within a public dashboard. In the same way, any detected failure can be monitored and acted upon.

- What are the possible failures of the product?

A software or content update that fails to work to some extend or at all despite thorough quality assurance and testing.

- What happens when the product fails?

Then the tool might have to be temporarily taken out of service, only for the affected part of people will have to be able to rely on other channels of interaction with government. These must hold on the same standards yet might be overwhelmed if the entire product fails for all people.


## 11. Explainability

- How is interpretability defined for the system?

Explainability is a context dependent socio technical aspect and has to be taken into account for all possible stakeholders, also citizens, where agreements are made and interpreted into more detail (which in itself is an additional agreement too). At any moment stakeholders involved must focus on how agreements are explained in several contexts taking into the account the vast diversity of stakeholders involved. This is not a simple thing and often overlooked in the Rules as Code domain. For strategies on how to deal with this we refer to Hans de Bruijn, Martijn Warnier, Marijn Janssen, The perils and pitfalls of explainable AI: Strategies for explaining algorithmic decision-making, Government Information Quarterly,
Volume 39, Issue 2, 2022, 101666, ISSN 0740-624X, https://doi.org/10.1016/j.giq.2021.101666. (https://www.sciencedirect.com/science/article/pii/S0740624X21001027)

The tool supports explanations of agreements in multiple alternative types of language, language style, degree of detail without losing correctness, degree of complexity without losing correctness but this depends on proper content making. The tool also requires transparence and linkeability with all official documents containing agreements that form the source that is being explained in a fine grained way.

- What interpretability methods are used?

The PRA tool allows for a range of methods to be used in content generation (including the rules).

- What metrics are used in result interpretation?

when things are not explained effectively this will be measurable in usage statistics and amount of requested support.

- How are interpretations of the output communicated?

through the tool itself and other channels.

The PRA tool helps setting a standard for content providers to make their interpretations of agreements explainable to the greater community

## 12. Human in the Loop (HITL)
- What is the role of a human agent in the validation/verification of the outputs?

Any time a citizen experiences getting stuck in the tool, or with content the tool enables them to come into contact with professionals within relevant organizations in a timely way to help out and if whished by the citizen to start a complaint handling, improvement (request for change) process and so on. Applications being received by organizations also can involve a HITL when additional questions and the tacit knowledge of professionals are to be taken into account but that depends on the service.

- What is the role of a human agent in refining the model performance?

In the end there cannot be a single human agent involved in refining content or the tool itself but the first human agent addressed to help with the end user's "conflict" has to be a case manager that engages on behalf of the citizen in need until it has been resolved in a way that is accepted by the end user. Indirectly this refines the content or tooling.

- What is the decision-making power assigned to human agents responsible for the quality of output?

The decision-making power is determined by who is responsible for the relevant content and or tool. Often this might involve multiple organizations that need to come to a collaborative agreement to a feasible extend, possibly indirectly together with the end user as stakeholder helped by the HITL.

## 13. Model Performance Metrics
- Which metrics are used to evaluate the product performance?

Once in production this can be measured through statistics on anonymous usage data. But governments should notice a better usage of benefits than is currently seen for which there are existing monitoring tools.

In general, methods for applying rules as code involves defining test cases that can also be used for accuracy measurements or anomaly detection within content-units, resembling both unit as integration testing in software development. But this content is also not available (yet) and it does not seem possible to generate these using AI in a reliable way (yet). Where information on agreements to test for is not (yet) available this will not be possible in the first place either. For the generic models for the search function, just the generic metrics of these models have been used.

- Which measures are used to re-evaluate Accuracy, Recall, Precision, and F1- Score?

NA (yet)

## 14. Decision Feedback & Objection
- How does the product allow for structured feedback?

through a HITL focusing on feedback

- How can the user challenge the application output?

through a HITL relevant to what content the output applies to.

- Which are the third parties involved in resolving claims and objections?

responsible organizations could outsource service by a HITL to third parties.

## 15. Impact Assessment

- What potential harms can your product cause? (loss of opportunity, discrimination, economic loss, social stigma, detriment, emotional distress, etc)?

potentially the harm the product can cause is caused by content. The product has been designed to mitigate this by offering easy access to support and not relying on content to be correct all to easily, but this also is a matter of governance on how organizations cope with this. The product itself, unrelated to the content, could give emotional distress when it does not work flawlessly almost all the time (people are not that patient), or fails to include people because of its design. It can bring business opportunities but also disruption and perceived economic loss when business live of the thing the PRA effectively overcomes. It can give people more transparency and information but that can also feed into (political) conflict.

- What are the risks of the product’s failure?

When professionals start to rely on the tool, failures that make the tool unavailable might disrupt their work when there are no alternatives to rely on. When content is not having the required quality despite quality assurance measures, this might lead to a range of problems and conflicts, both small as big in a local or more global way. Therefor the PRA is explicitly designed to support the start of the collaborative decision making processes to overcome these problems and conflicts however

- What impact can the product cause when deployed at scale?

Political conflicts due to enlarged transparency, Business disruption for businesses that live on the current lack of transparency of content and so on. It however can generate new businesses to offer HITL services for instance or tooling and support for content making and maintenance (tools for denoting agreements following standardization for instance).

- How is the product influencing the existing markets?

It is not (yet) really, however only the idea of the PRA is bringing people on idea's to extend wallets with PRA kind of functionality. In the Netherlands, the Financieel Paspoort is such a project (which is great by the way, but does not has the same bigger scope as the PRA as described in this document). Within the Dutch government they are looking into a step stone project that would help start generating the content to some extend while not yet introduce it as an app with seemingly AI functionality. This could be an extension of MijnOverheid into people being able to get a quick oversight on what benefits they have a right for, yet not getting it yet.. and whether this could be used to proactively automatically apply them for them, though where this results in a form of automated decision making without a HITL possibility, this has a risk for failures that feed into distrust when there is no guarantee that people will not have to pay back money in case of errors, given the history of the childcare benefit scandal and other big problems that reached national news. Also at EU and global level (WHO) people noticed the project.

## 16. Regulatory Landscape
- What is the regulatory context in which the product operates?

The product disseminates the entire regulatory context itself, and of course also operates in the context of it. As described the project requires a regulation at probably continental as well as national level (just like EiDAS), along with its regulatory context, for instance the GDPR and the AI Act of the EU.

- Is the model portable to other market verticals?

In general, it is portable or extended to markets also. There is already a business version of the tool envisioned that helps businesses interacting with government instead of citizens. But also, citizens could be helped with services, and products in markets too, though this would require a redesign as this is more like.

- What regulatory risks are involved?

Current legislation may be blocking putting a tool like the PRA in production and will have to be adjusted. In the Netherlands this seems to apply for instance to the WDO (Wet Digitale Overheid). This requires more analysis.

## 17. Mitigation
- How do you test for bias and fairness? What fairness definitions do you employ and why?

This depends entirely on the content and is addressed by standardization for the methodic elaboration on agreements into machine consumable rules and other content like explanatory text sources and governance on the quality of all this, both the content itself as the processes that created and maintained them. "Fairness cannot be automated" (S. Wachter) and is also a socio-technical aspect and the also is a matter of explainability and decision making using tacit knowledge of human professionals involved. The tool relies entirely on the quality of the content in terms of bias and fairness but is aware of the inherent shortcomings in it by always denoting the advisory tool itself can not to be hold entirely authoritive and offering easy accessible help when in the experience of the user something cannot be right.  

- Does your team reflect a diversity of opinions, backgrounds, and thoughts?

Content, including rules and heuristics come from many teams. As well as the professionals that support people with it. These teams are to be diverse also however which might be addressed within governance.

- Do you have a process for redress if people are harmed by the outputs?

The tool and governance on it must provide in several ways for redress even on advice in which no official decisions are made as of yet. There must always be alternative accessible ways to apply for governmental services for people that want to use these; the tool cannot ever be allowed to be the only channel through which to interact with government. First of all, one could be helped by other citizens, by volunteers or professionals of NGO's in the applicable domain or governmental organizations themselves from local to national or continental organizations. People must be able to contact a national helpdesk for both any content as well as the tool itself and or specific organizations appointed to address complaints as well as overarching organizations for these like an Ombudsman.

- How fast can you shut down your product in production if it behaves badly?

Governments must be able to effectively disable the tool from working for applying for services as well as visualizing a warning about this and the potential for bad behavior when and where applicable.

- Who and how should be informed?

This depends on whether the tool itself behaves badly in a harmful way or it is the content and in which content. If it is the tool than the responsible organization for maintaining the tool within government is to be informed automatically. For content-matters the executive originations that are responsible for the governmental services should be informed automatically. In general, the public must be able to see any known problems at any time from a central publication channel which is also accessible for organizations and anyone anywhere. All this should be addressed through governance.

## 18. Changes in Behavior

- Do the automated decisions have significant legal or similar effects on the users/stakeholders?

The tool does not officially make decisions, yet as it functions as an advisor and when it is accepted as being of high quality in general it does influence citizens to make decisions for themselves that have significant legal or similar effects on themselves or others the tool is being used for.

- How might users change their behavior after use?

They might get aware of the existence of governmental services / information and how they apply to their personal life and needs and act accordingly

- What are the potentials for power imbalance?

Being an official tool provided by government, when it has proven to be of sufficient quality, people, both citizens as professionals will hold the tool's advice as being authoritive very easily even when government disclaims this and the content the tool processes might contain or result in errors. It is important the tool addresses this by enabling functionality to overcome any probably flaw in the content or in the experience of its users no matter what the truth is as this is often context dependent.

## 19. Group Interactions

- What group interactions can you anticipate?

People will start to use the information from the tool also in conflict engagement within (large) groups. For instance, addressing perceived bias. This might reveal a need within these groups to extend the tool to support this, which hooks into judicature.

- What are potential changes in group behavior?

If the tool reaches its goal, people will start to rely on it, and this might have impact on group behavior. 

- How is the product addressing group interests?

In general, for citizens, the PRA tool addresses group interests around getting personalized qualitative oversight on government services, allowing them to easily use a single dedicated channel (this is a sort of MyGovernment app on steroids instead of the current MyGovernment portal (mijnoverheid.nl). Moreover, the PRA tool addresses interests of people, volunteers and professionals to use this not only for themselves but also others in their support work. In essence, the PRA tool is to be one of the official channels to help society with the awareness, explainability, transparency, accessibility and inclusiveness of all agreements that are made within society along with giving access to support and collaborative decision-making processes to improve on agreements and or make new ones. Because it requires non existing content which is also necessary for other kind of channels the project also helps those other channels. When the PRA tool also functions as access to the vast knowledge base of agreements, for citizens but also volunteer / professionals, it can be part of those other channels (think of helpdesks at libraries).

It has been foreseen, the PRA tool can be extended to support collaborative decision making in groups or even e-democracy, but this is out of scope because of feasibility: the PRA tool for personal advice is already an ambitious goal which may require subgoal solutions as steppingstone.

- What new groups could be born due to the product deployment at scale?

Depending on the degree of nonviolence of the tool and the content, language matters, and how it is perceived it ensures privacy and so on feeding into trust, it may create enthusiasts as well as a group of people that feels threatened by the introduction of the tool. This could be citizens that decide to be convinced the tool is a threat to them, as for some people everything a government does just is, or it could be professionals that think the tool is a threat to their established work as there are a lot of people involved already in disseminating knowledge through a diverse set of channels (mostly websites). This may prevent sufficient funding for the realization of a tool of the PRA when it is not supported by decision makers high in the hierarchy of government. It may even need a push from a continental level first to get the level of understanding and interoperability needed for a tool as the PRA. 

## 20. Comments

This version is only an initial version based on the experience by just one person that participated as a product owner / lead architect in the PRA project and tried to incorporate all experiences and conclusions the diverse team that worked on the PRA project have had in a best effort. The canvas should be evaluated and improved continuously in a diverse team however.

---

The Open Ethics Canvas v1.0 © 2021 by Open Ethics contributors
Designed by Nikita Lukianets, Alice Pavaloiu, Vlad Nekrutenko
Licensed under Attribution-ShareAlike 4.0 International
https://openethics.ai/canvas

