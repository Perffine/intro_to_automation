<!--
slides.md - Reveal.js Markdown deck authoring notes

How this file is used:
- Loaded by `site/reveal/index.html` via `<section data-markdown="slides.md">`.
- Parsed by Reveal Markdown plugin into HTML slide `<section>` elements.
- Styled by `site/reveal/assets/whimsy-theme.css`.

Slide structure and separators:
- Use `---` to start a new horizontal slide.
- Use `--` to start a vertical child slide under the current horizontal slide.
- Keep one clear topic per slide; use vertical children for supporting/source slides.
`
Slide-level metadata syntax:
- Add slide classes/attributes with HTML comments directly above slide content:
  - ` !-- .slide: class="content-slide dense" -- `
  - ` !-- .slide: data-background-image="/images/example.png" -- `
- These values are applied to that slide's generated `<section>` and are targeted by CSS.

Naming conventions in this deck:
- Slide class names are lowercase-kebab-case and composable.
- Prefer reusable behavior classes (`dense`, `compact`, `source-page`, `hero-bg`) over one-off names.
- Keep optional manual markers like ` !-- Slide N -- ` for human navigation while editing.

Authoring patterns used here:
- Markdown for most content (headings, lists, links).
- Inline HTML where needed for richer layout/components (`<div class="pill-row">`, `<img ...>`).
- Image paths are site-root style (`/images/...`) to match this site's routing.

Quick edit checklist:
- Add/update slide content first, then set ` !-- .slide: ... -- ` metadata.
- Reuse existing classes before creating new ones in CSS.
- Check navigation flow (left/right and up/down) after separator changes.
- Preview in desktop + mobile dimensions after layout-heavy edits.`

-->


<!-- Slide 0 --> 
<!-- .slide: class="title-splash" -->
# Intro to Automation
### Full Deck in Reveal.js + Markdown

This deck now mirrors all class slides from the legacy HTML pages.

<div class="pill-row">
  <span class="pill">Markdown-authorable</span>
  <span class="pill">Reveal navigation</span>
  <span class="pill">Legacy pages preserved</span>
</div>

Use arrow keys to navigate. Press `S` for speaker notes.

---

<!-- Slide 1 --> 

<!-- .slide: class="content-slide-centered" -->

## 2 question survey

### 100% optional - not required

### 100% private - do not sign in

<img src="/images/survey1.png" alt="Survey graphic" class="spot-image" />

[https://forms.gle/KEjxEiy7ZkK4ZaNLA](https://forms.gle/KEjxEiy7ZkK4ZaNLA)

---

<!-- Slide 2 --> 

<!-- .slide: class="hero-bg hero-bg-clear hero-top-10" data-background-image="/images/intro_to_automation_p1.png" data-background-size="contain" data-background-position="center" data-background-repeat="no-repeat" data-background-color="#000" -->

<h1 class="red-font">intro</h1>
<h1 class="red-font">to</h1>
<h1 class="red-font">automation</h1>

<h3>(apr 2026)*</h3>

<h3 class="bottom-text">*-best before Sept 2026</h3>

---

<!-- Slide 3 -->

<!-- .slide: class="content-slide dense" -->
#### Land Acknowledgment

The Toronto Reference Library is on Indigenous land. This is the traditional territory of the Haudenosaunee (ho-den-oh-sho-nee) Confederacy (aka. the Six Nations Confederacy), the Wendat, and the Mississaugas of the Credit First Nation. Toronto Public Library gratefully acknowledges these Indigenous nations for their guardianship of this land. We would also like to remind and reaffirm, as Torontonians and Canadians, our accountability to these Indigenous nations, and to all Indigenous peoples and communities living in Toronto.

This land is also part of the Dish with One Spoon territory, a treaty between the Haudenosaunee Confederacy (aka. the Six Nations Confederacy), the Anishinaabek (Ah-nish-nah-bek) and allied nations, to peaceably share and care for this land, its waters, and all of the biodiversity in the Great Lakes region. All those who come to live and work here are responsible for honouring this treaty in the spirit of peace, friendship, and respect.

<img src="/images/land_ack.png" alt="Land Acknowledgment" class="spot-image" />

#### *-image by NotebookLM

---

<!-- Slide 4 -->

<!-- .slide: class="content-slide dense" -->
## Discussing Today

- AI (particularly LLMs and generative), robotics (particularly humanoid) = automation
- History, and the current state of automation
- Demonstrate current tools
- Possible impacts of automation
- Controversies

## Not Discussing Today

- Religion
- Psychology
- Conspiracies

Automation is a spicy topic! Please be respectful.

---

<!-- Slide 5 -->

<!-- .slide: class="content-slide dense" -->
## Mythological/Sci-Fi AI

Talos (Greek. 3rd C BCE), Golem and Brazen Heads (Middle Ages), Homonculus (16th C), Frankenstein (1818), “Rossum’s Universal Robots” (1920), Iron Man (1960s), J.A.R.V.I.S (2008) [[1]](https://en.wikipedia.org/wiki/History_of_artificial_intelligence) [[45]](https://en.wikipedia.org/wiki/Iron_Man_(comic_book)) [[46]](https://en.wikipedia.org/wiki/J.A.R.V.I.S)

## Automata:

King Mu of Zhou’s work (900's BC), Leonardo’s Robot (late 15th C), “The Turk” (1769), Industrial Revolution (Late 1700s - 1800s), Walt Disney World “Hall Of Presidents” (1971) [[1]](https://en.wikipedia.org/wiki/History_of_artificial_intelligence)

Disney World “Hall Of Presidents”

Da Vinci’s Robot

Iron Man

Automata:

King Mu of Zhou’s work (900's BC), “The Turk” (1769), Industrial Revolution (Late 1700s - 1800s), Walt Disney World “Hall Of Presidents” (1971) [[1]](https://en.wikipedia.org/wiki/History_of_artificial_intelligence)

--


<!-- .slide: class="source-page compact" -->
### Sources

- [en.wikipedia.org](https://en.wikipedia.org/wiki/History_of_artificial_intelligence)
- [en.wikipedia.org](https://en.wikipedia.org/wiki/Iron_Man_(comic_book))
- [en.wikipedia.org](https://en.wikipedia.org/wiki/J.A.R.V.I.S)

---

<!-- Slide 6 -->

<!-- .slide: class="content-slide dense" -->
## Compute

Aristotle's syllogisms (350 BC)

Early Calculators (1600s)

Nerves and brain have electrical signals (1800s)

*** 1940s Computational AI Research begins ***

1943 “Artificial neurons” proposed, later called “Neural Network”

1950 “Turing Test”

1956 Dartmouth Workshop

1997 Deep Blue defeats Gary Kasparov

*** Early 2000s “Big Data” era begins ***

2010 Deep Mind founded

2011 Watson wins Jeopardy

2012 “Deep Learning”

2015 OpenAI founded

2017 “Attention Is All You Need”

*** 2022 ChatGPT is the fastest-growing consumer software application in history ***

2025 Xania Monet, Disney/Sora.ai, Nano Banana

2026 Clawdbot/moltbot/openclaw

[[1]](https://en.wikipedia.org/wiki/History_of_artificial_intelligence) [[47]](https://www.cbc.ca/news/entertainment/ai-artist-xania-monet-radio-billboard-chart-9.6967542) [[48]](https://www.reuters.com/business/media-telecom/disney-makes-1-billion-investment-openai-brings-characters-sora-2025-12-11/) [[57]](https://gemini.google/overview/image-generation/)

Gottfried Leibniz

b 1646

--
<!-- .slide: class="source-page compact" -->
### Sources

- [en.wikipedia.org](https://en.wikipedia.org/wiki/History_of_artificial_intelligence)
- [www.cbc.ca](https://www.cbc.ca/news/entertainment/ai-artist-xania-monet-radio-billboard-chart-9.6967542)
- [www.reuters.com](https://www.reuters.com/business/media-telecom/disney-makes-1-billion-investment-openai-brings-characters-sora-2025-12-11/)
- [gemini.google](https://gemini.google/overview/image-generation/)

---

<!-- Slide 7 -->

<!-- .slide: class="content-slide dense" -->
## Have We Been Here Before?

1st Industrial Revolution (1760s-1840s): Steam Power

Steam engines replaced human and animal power for labor and transportation

2nd Industrial Revolution (1870s-1914): Electricity & Assembly Lines

Mass production, electric lighting, communication networks

3rd Industrial Revolution (1950s-2010s): Computers & Internet

Automated information processing and global communication

4th Industrial Revolution* (2010s-present): Cognitive Automation, Advanced Robotics

Automating human cognition, creativity, physical labour and dexterity, empathy and emotional intelligence decision-makingo more -

*- the concept of the 4th Industrial Revolution (4IR) is not universally accepted. Proponents point to recent, rapid improvements in automation, and how such improvements played out in history [[36]](https://www.mckinsey.com/featured-insights/mckinsey-explainers/what-are-industry-4-0-the-fourth-industrial-revolution-and-4ir) Opponents argue it is aspirational, overemphasizes ‘technological determinism’, and lacks the profound societal restructuring that true industrial revolutions historically entailed [[37]](https://wiredspace.wits.ac.za/items/c9964d23-2fdf-486b-8c3d-1b4926c14042)

What do you think

--
<!-- .slide: class="source-page compact" -->
### Sources

- [www.mckinsey.com](https://www.mckinsey.com/featured-insights/mckinsey-explainers/what-are-industry-4-0-the-fourth-industrial-revolution-and-4ir)
- [wiredspace.wits.ac.za](https://wiredspace.wits.ac.za/items/c9964d23-2fdf-486b-8c3d-1b4926c14042)

---
<!-- Slide 8 -->
<!-- .slide: class="content-slide concise" -->
## Is it different this time?

---

<!-- .slide: class="content-slide" -->
## Slide 11: Is it different this time?

Are we automating the thing that makes us uniquely human

thinking

---

<!-- Slide 8 -->

<!-- .slide: class="content-slide dense" -->
## Tools you can use free today

ChatGPT/Claude/Gemini/Grok/Perplexity - web/app chat-based

Cursor, Anti Gravity, Github CoPilot - code assistants with free tier

NotebookLM - research and education tool, produces podcasts and videos

Ollama/LMStudio - locally run/tune LLMs for free (requires ‘beefy’ computer)

ChatGPT (Dall-e), Nano Banana - Image generation

Suno, Udio - music generation

Google Flow, Veo2, Sora2 (invitation link required) - video generation

Nano Banana - image editing

Canva Magic Studio - all-in-one production

Opal, Lovable.dev - “vibe coding”, app development

clawdbot/moltbot/openclaw - Autonomous agents able to do complex work

---

<!-- .slide: class="content-slide" -->

<!-- Slide 9 -->
## Ethical Concerns

Data scraping without permission [[8]](https://cybersecuritynews.com/meta-trained-its-llama-ai-models-using-81-7-tb-of-books-stolen-from-torrent-shadow-libraries/)

Use of copyrighted works without compensation or attribution [[9]](https://authorsguild.org/news/new-york-times-sues-openai-and-microsoft-for-copyright-infringement/)

RLHF workers exposed to PTSD-causing content [[5]](https://www.equaltimes.org/the-filipino-workers-at-the-sharplang=en)[[6]](https://time.com/6247678/openai-chatgpt-kenya-workers/)

LLM’s exhibiting bias [[25]](https://venturebeat.com/ai/musks-attempts-to-politicize-his-grok-ai-are-bad-for-users-and-enterprises-heres-why)

Lacking safeguards for users with mental illness or distress [[38]](https://www.cbc.ca/news/world/ai-lawsuit-teen-suicide-1.7540986)

--
<!-- .slide: class="source-page compact" -->
### Sources

- [cybersecuritynews.com](https://cybersecuritynews.com/meta-trained-its-llama-ai-models-using-81-7-tb-of-books-stolen-from-torrent-shadow-libraries/)
- [authorsguild.org](https://authorsguild.org/news/new-york-times-sues-openai-and-microsoft-for-copyright-infringement/)
- [www.equaltimes.org](https://www.equaltimes.org/the-filipino-workers-at-the-sharplang=en)
- [time.com](https://time.com/6247678/openai-chatgpt-kenya-workers/)
- [venturebeat.com](https://venturebeat.com/ai/musks-attempts-to-politicize-his-grok-ai-are-bad-for-users-and-enterprises-heres-why)
- [www.cbc.ca](https://www.cbc.ca/news/world/ai-lawsuit-teen-suicide-1.7540986)

---
<!-- Slide 10 -->
<!-- .slide: class="content-slide" -->
## Societal Concerns:

Job loss - Amazon announced (via confirmed leak) that they plan to hire 600K fewer warehouse/logistics workers by 2027, replaced by robots [[2]](https://www.nytimes.com/2025/10/21/technology/inside-amazons-plans-to-replace-workers-with-robots.html) Is this a bellwether

AI use linked to social isolation [[18]](https://publichealth.gmu.edu/news/2025-09/ai-loneliness-and-value-human-connection)

We are in an early, chaotic stage. Not unlike when cars and horses shared the road.

--
<!-- .slide: class="source-page compact" -->
### Sources

- [www.nytimes.com](https://www.nytimes.com/2025/10/21/technology/inside-amazons-plans-to-replace-workers-with-robots.html)
- [publichealth.gmu.edu](https://publichealth.gmu.edu/news/2025-09/ai-loneliness-and-value-human-connection)

---
<!-- Slide 11 -->
<!-- .slide: class="content-slide dense" -->
## Safety Concerns:

AI Hallucination - when an AI model generates confident but incorrect information.

AI sycophancy - The tendency of an AI system, particularly a large language model, to excessively agree with, flatter, or validate a user's opinions, beliefs, or reasoning, even at the expense of accuracy, objectivity, or truthfulness.

AI Psychosis - (currently not a recognized clinical diagnosis and there is little scientific research) individuals reportedly developing or experiencing worsening psychosis in connection with their use of chatbots

Significant development concerns about AI use in children and Teens [[4]](https://www.technologynetworks.com/informatics/news/us-psychologists-calls-for-guardrails-for-teens-using-ai-400522)

Parasocial relationships with AI [[4]](https://www.technologynetworks.com/informatics/news/us-psychologists-calls-for-guardrails-for-teens-using-ai-400522)

“Jailbreaking” AI models - confidential or private info can be found with prompting [[7]](https://www.youtube.com/watchv=O7BI4jfEFwA)

Careless use of new AI tools, policy and compliance issues [[58]](https://natlawreview.com/article/ai-notetaking-tools-under-fire-lessons-otterai-class-action-complaint)

AI mistakes sending innocent people to jail [[14]](https://innocenceproject.org/news/when-artificial-intelligence-gets-it-wrong/)

Deepfakes and AI assisted crime [[15]](https://www.weforum.org/stories/2025/07/why-detecting-dangerous-ai-is-key-to-keeping-trust-alive/)

Self Driving accidents [[41]](https://incidentdatabase.ai/entities/tesla)

Web Prompt Injection - A new form of social engineering [[63]](https://openai.com/index/prompt-injections/)[[64]](https://openai.com/index/hardening-atlas-against-prompt-injection/)

--
<!-- .slide: class="source-page compact" -->
### Sources

- [www.technologynetworks.com](https://www.technologynetworks.com/informatics/news/us-psychologists-calls-for-guardrails-for-teens-using-ai-400522)
- [www.youtube.com](https://www.youtube.com/watchv=O7BI4jfEFwA)
- [natlawreview.com](https://natlawreview.com/article/ai-notetaking-tools-under-fire-lessons-otterai-class-action-complaint)
- [innocenceproject.org](https://innocenceproject.org/news/when-artificial-intelligence-gets-it-wrong/)
- [www.weforum.org](https://www.weforum.org/stories/2025/07/why-detecting-dangerous-ai-is-key-to-keeping-trust-alive/)
- [incidentdatabase.ai](https://incidentdatabase.ai/entities/tesla)
- [openai.com](https://openai.com/index/prompt-injections/)
- [openai.com](https://openai.com/index/hardening-atlas-against-prompt-injection/)

---
<!-- Slide 12 -->
<!-- .slide: class="content-slide dense" -->
## Environmental Concerns:

Rare Earth Elements mining - incredible amounts of REE’s required for humanoid robots/EVs at great environmental cost - often in developing world [[60]](https://www.nytimes.com/2025/07/05/business/china-rare-earth-environment.html)

Data Centers causing acute local water and electricity demand increase [[22]](https://www.eesi.org/articles/view/data-centers-and-water-consumption)

USA has over 4000 Data Centers (Canada has over 100) [[61]](https://www.pewresearch.org/short-reads/2025/10/24/what-we-know-about-energy-use-at-us-data-centers-amid-the-ai-boom/) [[62]](https://www.globenewswire.com/news-release/2025/12/04/3199536/28124/en/Canada-Colocation-Data-Center-Portfolio-Report-2025-2028-Detailed-Analysis-of-116-Existing-Data-Centers-19-Upcoming-Data-Centers-and-45-Major-Operators-Investors.html)

7000+ estimated data centers in USA by 2030 [[23]](https://www.mckinsey.com/industries/public-sector/our-insights/the-data-center-balance-how-us-states-can-navigate-the-opportunities-and-challenges)[[24]](https://openai.com/index/announcing-the-stargate-project/)

--
<!-- .slide: class="source-page compact" -->
### Sources

- [www.nytimes.com](https://www.nytimes.com/2025/07/05/business/china-rare-earth-environment.html)
- [www.eesi.org](https://www.eesi.org/articles/view/data-centers-and-water-consumption)
- [www.pewresearch.org](https://www.pewresearch.org/short-reads/2025/10/24/what-we-know-about-energy-use-at-us-data-centers-amid-the-ai-boom/)
- [www.globenewswire.com](https://www.globenewswire.com/news-release/2025/12/04/3199536/28124/en/Canada-Colocation-Data-Center-Portfolio-Report-2025-2028-Detailed-Analysis-of-116-Existing-Data-Centers-19-Upcoming-Data-Centers-and-45-Major-Operators-Investors.html)
- [www.mckinsey.com](https://www.mckinsey.com/industries/public-sector/our-insights/the-data-center-balance-how-us-states-can-navigate-the-opportunities-and-challenges)
- [openai.com](https://openai.com/index/announcing-the-stargate-project/)

---
<!-- Slide 13 -->
<!-- .slide: class="content-slide dense" -->
## A New “gold rush”

California 1848-1855

Acute population rise in California

Prices soared for most goods

Inflation caused by increase in monetary supply (gold) and demand for goods

Worldwide labour shortages, labour wages soared

Implicit government support

Jensen Huang

Silicon Valley 2022--

Acute rise in water and electricity use

Prices soaring for Computer

Inflation caused by scarcity of natural resources and critical components

Explicit government support

---

<!-- .slide: class="content-slide concise" -->
## Slide 18: “Figure AI CEO Brett Adcock announced this week that one of the company's humanoid robots has now been operating for fiv

“Figure AI CEO Brett Adcock announced this week that one of the company's humanoid robots has now been operating for five consecutive months on the BMW X3 body shop production line in Spartanburg, South Carolina [...] the robot has been running for 10 hours per day, every single day of production” [[39]](https://www.humanoidsdaily.com/feed/figure-claims-humanoid-robot-has-worked-five-months-on-bmw-production-line) [[59]](https://interestingengineering.com/ai-robotics/figure-humanoid-robots-retires-bmw)

[[40]](https://www.tomshardware.com/tech-industry/artificial-intelligence/grieving-family-uses-ai-chatbot-to-cut-hospital-bill-from-usd195-000-to-usd33-000-family-says-claude-highlighted-duplicative-charges-improper-coding-and-other-violations)

--
<!-- .slide: class="source-page compact" -->
### Sources

- [www.humanoidsdaily.com](https://www.humanoidsdaily.com/feed/figure-claims-humanoid-robot-has-worked-five-months-on-bmw-production-line)
- [interestingengineering.com](https://interestingengineering.com/ai-robotics/figure-humanoid-robots-retires-bmw)
- [www.tomshardware.com](https://www.tomshardware.com/tech-industry/artificial-intelligence/grieving-family-uses-ai-chatbot-to-cut-hospital-bill-from-usd195-000-to-usd33-000-family-says-claude-highlighted-duplicative-charges-improper-coding-and-other-violations)

---

<!-- Slide 14 -->
<!-- .slide: class="content-slide dense" -->
## AI Wins:

AlphaFold - solved “protein folding”, accelerating medical research by decades [[16]](https://deepmind.google/science/alphafold/)

popEVE - AI powered genetic variant detection [[44]](https://ellipse.prbb.org/ai-model-revolutionizes-rare-disease-diagnosis/)

Fraud Detection [[17]](https://blogs.nvidia.com/blog/how-ai-helps-fight-fraud/)

Education (eg. Khanmigo)

Accessibility - real time transcription, translation, and image detection [[43]](https://blog.google/products/search/gemini-capabilities-translation-upgrades/)

Grok integration into X allows integrated social media fact checking

2nd order consequences of AI research

“Move 37”

--
<!-- .slide: class="source-page compact" -->
### Sources

- [deepmind.google](https://deepmind.google/science/alphafold/)
- [ellipse.prbb.org](https://ellipse.prbb.org/ai-model-revolutionizes-rare-disease-diagnosis/)
- [blogs.nvidia.com](https://blogs.nvidia.com/blog/how-ai-helps-fight-fraud/)
- [blog.google](https://blog.google/products/search/gemini-capabilities-translation-upgrades/)

---
<!-- Slide 15 -->
<!-- .slide: class="content-slide dense" -->
## Early tech fails in history:

Water use by California almond industry

6.8 Trillion L/year [[28]](https://farmonaut.com/usa/amount-of-water-to-produce-almonds-ca-almond-water-use-2025)

Early steam engine boiler explosions

Early electricity accidents [[21]](https://rytecelectric.com/blog/the-history-of-home-electrical-system-safety/)

Early internet security and moderation was limited [[20]](https://blog.mesltd.ca/a-history-of-information-security-from-past-to-present)

AI water use:

1 Google search = 0.5mL (.0005L)

5 to 50 ChatGPT prompts = 0.5L

Estimated Total AI Data Center use in 2027 = 4-6 Trillion L/year [[29]](https://www.cloudcomputing-news.net/news/data-centre-water-consumption-crisis/)

AI energy use:

Currently AI use represents about 4% of total US energy use [[61]](https://www.pewresearch.org/short-reads/2025/10/24/what-we-know-about-energy-use-at-us-data-centers-amid-the-ai-boom/)

Projected 2030 US use is 8% [[61]](https://www.pewresearch.org/short-reads/2025/10/24/what-we-know-about-energy-use-at-us-data-centers-amid-the-ai-boom/)

--
<!-- .slide: class="source-page compact" -->
### Sources

- [farmonaut.com](https://farmonaut.com/usa/amount-of-water-to-produce-almonds-ca-almond-water-use-2025)
- [rytecelectric.com](https://rytecelectric.com/blog/the-history-of-home-electrical-system-safety/)
- [blog.mesltd.ca](https://blog.mesltd.ca/a-history-of-information-security-from-past-to-present)
- [www.cloudcomputing-news.net](https://www.cloudcomputing-news.net/news/data-centre-water-consumption-crisis/)
- [www.pewresearch.org](https://www.pewresearch.org/short-reads/2025/10/24/what-we-know-about-energy-use-at-us-data-centers-amid-the-ai-boom/)

---
<!-- Slide 16 -->
<!-- .slide: class="content-slide dense" -->
## Emergent Properties

"There's no love in a carbon atom, No hurricane in a water molecule, No financial collapse in a dollar bill." [[49]](https://warzel.substack.com/p/how-to-perform-a-social-media-autopsy)

Multi-digit addition [[53]](https://arxiv.org/pdf/2206.07682)

Learning through ego-centric video footage [[56]](https://www.physicalintelligence.company/research/human_to_robot)

Few-shot learning

Chain Of Thought Reasoning

Cross-Lingual Transfer

Analogical Reasoning

** These all emerged during the training process. They were not explicitly taught **

For Example ..

Oxygen and Hydrogen are not wet, but H2O is

Cake ingredients aren’t spongey, but cake is

Ant colonies develop organization and communication

Emergent Properties In AI ..

What properties will emerge from agent swarms

*-image by Gemini

--
<!-- .slide: class="source-page compact" -->
### Sources

- [warzel.substack.com](https://warzel.substack.com/p/how-to-perform-a-social-media-autopsy)
- [arxiv.org](https://arxiv.org/pdf/2206.07682)
- [www.physicalintelligence.company](https://www.physicalintelligence.company/research/human_to_robot)

---
<!-- Slide 17 -->
<!-- .slide: class="content-slide dense" -->
## The Accelerating Timeline:

Zeitgeist → Mainstream Use

Electricity: 1878 Paris Exposition, 70% adoption in US households by 1930 [[54]](https://en.wikipedia.org/wiki/Electrification) [[55]](https://en.wikipedia.org/wiki/History_of_electric_power_distribution)

Telephone: 1876 Centennial Exposition in Philadelphia, 45% household adoption by 1945

Television: 1926 London Royal Institution, 50% US household adoption by 1953

Internet: 1991 Commercial internet available, 50% US household adoption by 2003

SmartPhone: 2007 iPhone launch (Macworld Conference, SF), 50% US household adoption 2012

AI: Nov 2022 ChatGPT launch, 200+ million users globally by late 2024

2-5yrs

*-image by Gemini

--
<!-- .slide: class="source-page compact" -->
### Sources

- [en.wikipedia.org](https://en.wikipedia.org/wiki/Electrification)
- [en.wikipedia.org](https://en.wikipedia.org/wiki/History_of_electric_power_distribution)

---
<!-- Slide 18 -->
<!-- .slide: class="content-slide" -->
## Copyright Holders and Publishers

There is no historical precedent for the scope of copyright issues caused by copyright training.

Who’s gonna insure this?

---
<!-- Slide 19 -->
<!-- .slide: class="content-slide dense" -->
## Recommended Reading:

Klara and the Sun (2021, Kasuo Ishiguro)

DUST Podcast: Chrysalis (2020, SH Serrano)

What Is ChatGPT Doing … and Why Does It Work (2023, Stephen Wolfram, free eBook)

## Recommended Viewing:

Memento (2000, Christopher Nolan)

Youtube: Anastasia In Tech, Boston Dynamics, David Shapiro, Dylan Curious, Dwarkesh Patel, Fireship, Gabriel Torch, Gatherverse (Christopher Lafayette), Julia McCoy, Lex Fridman, Matty McTech, Nate B. Jones, Neil DeGrasse Tyson, Rational Animations, Ray Dalio, Walt Disney Imagineering, Wes Roth

## Recommended Gaming:

Detroit Become Human (2020, Quantic Dream)

kohel.itch.io/galli (2022, Kohel)

humanornot.so (2023, Nederev Oleg)

Pimantle (2022, @pimanrules)

realvsai.com (2025, jerieth)

---
<!-- Slide 20 -->
<!-- .slide: class="content-slide dense" -->
## Next Steps:

Follow AI news. There are new, game changing tools developed regularly.

Follow job loss news, “precarious employment” and “gig work”

Engage with AI tools according to your comfort level.

0 - No AI

1 - Suggestions, or starting points

2 - Analysis, explanations, or a second opinion

3 - Feedback and fact-checking

4 - Organization of deliverables, or formatting

5 - Original content generation based on your specifications

---
<!-- Slide 21 -->
<!-- .slide: class="content-slide dense" -->
## Give them a follow:

Sam Altman - ceo of OpenAI

Dario Amodei - ceo of Anthropic

Anthropic Research - AI research

Apollo Research - AI safety research

Demis Hassabis - co-founder and ceo Google DeepMind

Geoffrey Hinton - professor, “Godfather of AI”, nobel prize winner (physics, 2024)

Andrej Karpathy - co-founder of OpenAI, AI director at Tesla

Emad Mostaque - ceo Stability AI

Elon Musk - ceo x.AI (Grok)

Ilya Sutskever - co-founder and former chief scientist OpenAI, Founder of Safe Superintelligence Inc.

Eliezer Yudkowsky - researcher, author of “If Anyone Builds It, Everyone Dies” (2025)

---

<!-- Slide 22 -->

<!-- .slide: class="content-slide" -->
## More Learning:

[https://grow.google/intl/en_ca/](https://grow.google/intl/en_ca/) - Google AI Essentials

[https://www.bluedot.org/courses/future-of-ai](https://www.bluedot.org/courses/future-of-ai) - free course

LinkedIn Learning - many classes, all free with library card

--
<!-- .slide: class="source-page compact" -->
### Sources

- [www.cilar.ca](https://www.cilar.ca/ai-powered-futures)
- [grow.google](https://grow.google/intl/en_ca/)
- [www.bluedot.org](https://www.bluedot.org/courses/future-of-ai)

---
<!-- Slide 23 -->
<!-- .slide: class="content-slide" -->
## 3 question survey

100% optional - not required

100% private - do not sign in

[https://forms.gle/64whoTKHMzWhbZRg6](https://forms.gle/64whoTKHMzWhbZRg6)

--
<!-- .slide: class="source-page compact" -->
### Sources

- [forms.gle](https://forms.gle/64whoTKHMzWhbZRg6)

---
<!-- Slide 24 -->
<!-- .slide: class="content-slide dense" -->
## Terms and concepts:

Machine Learning - The foundation - the broad field of teaching computers to learn from data and improve at tasks without being explicitly programmed for every scenario. This concept subsumes all AI technology.

GPU / TPU / NPU / ASIC - GPUs excel at doing thousands of simple calculations simultaneously - perfect for the matrix math that neural networks require. TPUs are Google's specialized chip designed specifically for AI workloads. NPUs are chips built directly into consumer devices specifically for running AI models on the local device. ASICs (Application-Specific Integrated Circuit) are custom chips designed for one specific task.

Neural Networks - Technology inspired by how human brains work, these are computing systems made up of interconnected layers of "nodes" that can recognize patterns in data. They are the basic, brain-inspired structure that enables machine learning.

Training Data - The examples (or "raw material") used to teach an AI system. The quality and quantity of this data fundamentally determines what the AI can learn and how well it performs.

Gradient Descent - A fundamental training technique - this is how neural networks learn. Imagine trying to find the lowest point in a valley while blindfolded: you feel which direction is downward and take steps that way. Gradient descent helps the AI figure out how to adjust itself to make fewer mistakes, step by step.

Parameters (or Weights) - The adjustable "knobs" inside a neural network that gradient descent tweaks during learning. A model with billions of parameters can capture more complex patterns . These are what actually store the AI's learned knowledge.

Backpropagation - The specific mechanism that makes gradient descent work in neural networks. When the AI makes a mistake, backpropagation sends that error information backward through all the layers of the network, telling each part how much it contributed to the mistake. This is how the network knows what to adjust.

Supervised Learning - A training approach where the AI learns from labeled examples - like flashcards with questions and answers. You show it "this is a cat" and "this is a dog" thousands of times until it learns to distinguish them. This is distinct from reinforcement learning and helps explain different learning paradigms.

Reinforcement Learning - A specialized training approach where AI learns through trial and error, receiving rewards for good actions and penalties for bad ones - like training a dog with treats. This builds on basic neural network learning but adds the concept of goals and consequences.

Word Embedding - A technique that converts words into mathematical representations (lists of numbers) that capture their meanings and relationships. Words with similar meanings end up as similar numbers, allowing computers to understand that "king" relates to "queen" similarly to how "man" relates to "woman."

Transformer Architecture - The breakthrough design (2017) that made modern LLMs possible. It uses an "attention mechanism" that lets the AI focus on relevant parts of text when understanding context - like how you emphasize certain words when reading. This is the "T" in GPT (Generative Pre-trained Transformer).

Token - The basic unit LLMs work with - roughly ¾ of a word. AI sees language as chunks, not individual characters. This helps explains some strange outputs you will see. Due to hardware constraints, the amount of input tokens will be limited, though some models boast 1 million+ token “context windows” (not unlike the limit of one’s attention span)

Large Language Model (LLM) - Putting it all together for language - these are massive neural networks (like ChatGPT or Claude) trained on enormous amounts of text using the techniques above. They use word embeddings to understand language and can generate human-like text by predicting what words should come next.

Fine-tuning - Taking a pre-trained model and training it further on specialized data - like teaching a general doctor to become a cardiologist. This explains why there are medical AI assistants, coding assistants, etc.

RAG (Retrieval-Augmented Generation) - A technique where AI refers to a database before answering. The (usually user created) database is considered the primary source of information, and is referred to before the training data.

Generative AI - The category that includes both LLMs and diffusion models - AI that creates new content (text, images, music) rather than just analyzing or classifying existing content. This umbrella term helps distinguish these creative AIs from other types.

Prompt - The instructions or question you give to a generative AI.

Diffusion - A related AI technique, primarily used for media generation. Diffusion models learn by gradually adding noise to images until they're pure static, then learning to reverse the process step-by-step to create images from random noise. Music is generated with spectrogram images of audio.

Moore's Law - An observation from 1965 that computing power doubles approximately every two years while costs stay relatively constant. This explains why AI has accelerated so dramatically in recent years.

Jevon’s Paradox - As a technology becomes more efficient, we often end up using more of it, not less.

The Alignment Problem - The fundamental challenge of ensuring AI systems do what humans actually want them to do, not just what we literally tell them to do.

X-Risk (Existential Risk) / p(doom) - The possibility that advanced AI could pose an existential threat to humanity - literally endangering our survival as a species.

Anthropomorphism - The attribution of human-like characteristics, such as emotions or personality to AI systems

Ambient AI - The concept of “always on”, “always improving”, and “proactively working” AI. This type of AI doesn’t require user prompt to act. Eg- “moltbot”

---

<!-- Slide 25 -->

<!-- .slide: class="closing" -->
## Bibliography

Full consolidated references remain available here:

[Open All Sources](../sources.html)

