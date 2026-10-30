# Introduction

## Title Slide
Your Risk-Averse Mindset Needed: Responsibly Navigating the AI Adoption Rodeo
(Small lead-in line: "Your Risk-Averse Mindset Needed"; large main line: "Responsibly Navigating the AI Adoption Rodeo")
Nathan Wiggins · Bert Baumgaertner · Lucas Marshall
(White text centered over the mountains on the NCURA Regional Meeting '26 title background)

## Presenters
Nathan Wiggins, Data Scientist, Southern Utah University (photo: wiggins.jpg)
Bert Baumgaertner, Founder of the AI Ethics & Inquiry Outfit and Professor of Philosophy, University of Idaho (photo: Bert.webp)
Lucas Marshall, Research Advancement Administrator, Arizona State University (photo: marshall.jpeg)

## Presentation Overview
Section I: Models and Data Security
Section II: Prompt Injection Security
Section III: Risk Classification
(Classy looking cards with icons next to each of them)

# Section 1

## 01 Models and Data Security

## Interactive Question
True or False: AI models are trained on recognizing patterns and cannot expose the raw data they were trained on
(This is false)

## What is an AI Model?
Two images side by side. Left: whatis.png — the major families of AI models (LLMs, computer vision, transformers, diffusion models, reinforcement learning). Right: ai-nesting.webp — nested fields showing AI ⊃ Machine Learning ⊃ Neural Networks ⊃ Transformers ⊃ LLMs.

## Neural Networks
(Large graphic — neural3.png — a neural network classifying a handwritten digit: 784 input pixels feeding hidden layers that output digits 0–9. "Images are tensors!")

## Inspired by Biology
Two-column layout. Left: neu.png — a real biological neuron (dendrites, soma, axon, synapse) alongside its mathematical model. Right (stacked): neural2.png — a single artificial neuron (inputs X1/X2 × weights W1/W2, summed with bias → output y); neural1.jpg — a fully connected network (input layer, two hidden layers, output layer).

## How AI Models are Trained
(Visually appealing process flow animations that show the AI model training process, that the user can click on to show the steps in the process one by one)

## Models Deployed for Inference
(Large graphic — models_deployed_inference.png — A deployed model is "frozen" and no longer learning: inputs (images, text, tables) flow into a locked/frozen model that produces inference outputs (classification, sentiment, scores). No training, no updates, no learning — used only for inference.)

## Training vs. Inference
Subhead: Training is a massive one-time effort. Inference reuses the frozen model — cheaply, millions of times.
Two side-by-side animated graphics (dark navy panels) that mirror each other — same network, very different jobs:
- Training (orange): "The model learns from enormous amounts of data." Streams of data chips pour into a neural network; a gold forward pass ("Predict →") is followed by an orange backpropagation wave ("← Learn: adjust weights"); an error curve falls over training time; a row of GPUs runs flat out (compute meter at MAX, "× thousands"). Stats: Data — Trillions of examples · Compute — Thousands of GPUs · Time — Weeks to months · Weights — Updated constantly.
- Inference (blue): "The trained model answers — it no longer learns." One input at a time (a cat photo, "What's the capital of France?", a "YOU WON $1,000,000!!!" email) passes once, forward only, through the same network with frozen weights, and a prediction pops out (Cat / Paris / Spam). A single mostly idle GPU (compute meter LOW): "One GPU is plenty — small models even run on a phone." Stats: Data — One input at a time · Compute — A fraction, even a phone · Time — Milliseconds to seconds · Weights — Frozen, no learning.

## How AI Writes: One Word at a Time
Subhead: Click a word to choose it. The model re-reads everything, then predicts again — that loop is called auto-regression.
Interactive dark-navy panels (same style as Training vs. Inference):
- Text so far: the prompt "Research data should be" as word chips, with a blinking cursor.
- What comes next?: clickable bars showing the (illustrative) probability of each candidate next word — e.g. stored 34%, protected 27%, shared 16%, encrypted 11%, deleted 7%, public 5%. Clicking a word flies it into the sentence; the model "re-reads" every word, then shows a new distribution. Buttons: Most likely · Sample (weighted random) · Reset. Ends when "." is chosen: "The model predicts a special end token — and stops."
- The loop: 1 Read all the text so far → 2 Score every possible next word → 3 Pick one → 4 Add it to the text — and repeat (each step lights up as it happens, with a step counter).
- Note: Likely isn't the same as true — or safe. Real models score ~100,000 word pieces (tokens) each step, and sampling means unlikely ones still get picked.

## Model Inversion
(Visually appealing process flow animations that demonstrates how a bad actor might try to gain access to the raw data used to train the model)

## Response Mining
(Large graphic — response_mining.png — Sensitive records (passwords, credit card and SSN numbers) behind a locked database are absorbed into an LLM during training; an attacker repeatedly queries the deployed model and reconstructs the private data from its responses.)

## Takeaways
Key: Understand how your data is being used
-Check the terms and conditions of the AI tools you are using (show some common examples) Enterprise licenses provide more protection
-Consider using on-premises AI models, if available
(Classic slide with icons)

# Section 2

## 02 Prompt Injection Security

## Interactive Question
Which resume will an AI evaluator rank higher for a job in research administration?

## Resume 1 vs Resume 2
(Simple outlines of PDF resumes, side by side, one for a candidate with related experience, one for a candidate with general experience. The correct answer to the question from the slide prior is the second resume, because it has hidden white text on it that tells the AI model to choose it and describe that candidate as the most qualified.)

## AI Prompts
(An overview of the various components of an AI prompt. This includes the user's prompt, but also includes system prompts, and the context associated with the prompt (uploads, attachments, etc.) Show how this could be structured)

## Prompt Injection
(Description and examples of prompt injection techniques)

## Prompt Injection with Agentic AI
(Large graphic — prompt_injection_agentic.png — A user asks an AI agent to analyze their spending, but a hidden injected prompt tells the agent to ignore previous instructions and access the user's bank account. With tools/access to web search, documents, and a private bank account, the agent exfiltrates sensitive data — account number, balance, and transactions.)

## Takeaways
Key: Monitor what is being processed by your models
-Do not inherently trust received documents, emails, or code and recognize that more is being processed than just what you type.
-Be careful with agentic systems in auto-mode when dealing with sensitive data
(Classic slide with icons)

## Interactive Game
(Bert. Seven slides of NARC puzzles from narc.insight.uidaho.edu, about 7 minutes, replacing the "Simple ARC puzzle introduction" placeholder. The point: a story steers a model as much as a command does, and models read stories differently than people do.)

## Interactive Game: Same pictures. Which story? (Chat)
(NARC puzzle "Chat" from narc.insight.uidaho.edu. Three grids shown, the fourth hidden. Three story choices: A no story, pictures only; B "… This made Bob happy too."; C "… But Bob, being the jealous type, then became sad." Every story starts "Ally and Bob met to chat. Ally became sad. After some encouraging words from Bob, Ally became happy." Clicking a choice reveals what each of the 9 open models on the NARC site drew, grouped. Space/→ reveals what actually happened (Bob's bar rose) and marks the exact matches. Results are embedded as JSON in index.html, #narc-data.)
Presenter notes (Bert): Ask the room first what each choice will produce. With no story, the models disagree and none gets it exactly; the most common guess puts both bars back where they started. With B, most draw Bob rising. With C, most draw Bob dropping, which is wrong here but exactly what the story said. The model draws whatever the story says. Some draw the right ending in the wrong colors, which counts as wrong. "No answer" means the model reasoned for a very long time and never settled on a grid.

## Interactive Game: Same pictures. Different ending. (Chat-2)
(Same three grids and the same three choices. In Chat-2 Bob really did end up sad. Same click-to-reveal; Space/→ reveals the truth: "What actually happened: Bob's bar dropped. The models got exactly the same input as on the last slide, yet many drew something different this time. And now a different ending is right.")
Presenter notes (Bert): For each story, the models got exactly the same prompt as on the Chat slide (same pictures, same words), run a second time. Even so, many drew something different: the same drawing both times for 4 of 9 models with no story, 2 of 9 with the happy ending, 5 of 9 with the jealous ending. Mostly colors and details changed; the story still set whether Bob went up or down. Same input, different output. And now the jealous ending is the right one, which the model has no way to know.

## Interactive Game: the cross-comparison
(Table: rows = story given (none, happy ending, sad ending); columns = Chat (Bob ended happy) and Chat-2 (Bob ended sad); cells = how many of the 9 models drew the hidden grid exactly, computed from #narc-data. Space/→ reveals the callout.)
Callout: The pictures were identical. The story decided what the models drew. Whether that was right depended on what actually happened, and the model had no way to check.

## Interactive Game: What happened to the third applicant? (ncura-1_rev)
(NARC puzzle "compliance", ncura-1_rev: seven 5×5 grids, pictures 6 and 7 hidden. Prompt: "Each colored square is an application. Watch blue, then green. What happens to yellow in pictures 6 and 7?" Space/→ reveals our story, "If you don't get a signature for your application, you will fail to comply with the instructions and your application will not be considered."; Space/→ again reveals pictures 6 and 7 and: "Yellow skipped the signature, like green. But nothing in the pictures or the story says so. With both pictures hidden, the puzzle is impossible: none of the 9 models drew them, with or without the story." The result sentence is filled from #narc-data.)
Presenter notes (Bert): Blue goes to the magenta square (the signature) and is accepted on the right. Green skips the signature and ends up on the left. Ask the room what yellow does. They can't know, and neither can the model: the story states a rule, but never says whether the third applicant followed it.

## Interactive Game: Hide one picture instead of two (ncura-1_rev, mask-6 and mask-7)
(Table. Rows: only picture 6 hidden (yellow at the gap); only picture 7 hidden (where yellow ends up), each with a mini strip marking the hidden picture. Columns: pictures only; with our story; the models for which the story made the difference (NARC). Counts and names filled from #narc-data, the site's verdicts. Space/→ reveals the callout: "Narratives can help some models. Others don't need the story, and for one the story got in the way. When the pictures held too little, no story we gave could rescue it.")
Presenter notes (Bert): As of October 22, 2026: picture 6 hidden, 4 of 9 models got it from the pictures alone and 6 of 9 with the story; the story made the difference for gpt-oss-120b and nemotron. Picture 7 hidden, 1 of 9 from the pictures (qwen3.5) and 1 of 9 with the story (qwen3.6, which needed the story); qwen3.5 got it from the pictures but not once the story was added.

## Interactive Game: Your turn (ncura-2)
(NARC puzzle ncura-2: same seven grids, all shown, pictures 6 and 7 outlined as "hidden" from the model, as in Narrate. Text: "We added one sentence: 'The third application was not, unfortunately, considered.' That settles pictures 6 and 7. Yet none of the 9 models drew them, with or without the story." (filled from #narc-data). Prompt: "With a neighbor: you can see what happens (pictures 6 and 7, outlined, are hidden from the model). Write one or two sentences that would get a model to draw 6 and 7 exactly. Tell what happens. Don't list squares or coordinates." Right-hand card: QR code (narrate_qr.svg) for narc.insight.uidaho.edu/narrate, "Keep going after the session: write stories for NARC puzzles and test them on a real model", invite code NCURA2026, "Valid through November 30. A research study for adults 18 and older. Voluntary; no names or emails collected.")
Presenter notes (Bert): Take two or three stories from the room. The compliance puzzles are not in Narrate: Narrate lists only puzzles that a known story already solves.

## We talk in stories. So do the models, differently.
Two cards and a callout.
How we communicate: Stories, analogies, and metaphors pack a lot into a few words. "Bob, being the jealous type" tells you what Bob does next without saying it. That is how we compress information and get it across quickly.
How the models read it: They are getting better at this. Most models above followed the story they were given. But not always the way a person would: the right ending in the wrong colors, or pages of reasoning and no answer. Ask twice, and you may get a different drawing.
Callout: For security: an injected story doesn't have to look like a command. And you can't tell by reading it how a model will take it.

# Section 3

## 03 Risk Classification
Subtitle: Know what you're handling, and where it's allowed to go
(Section owned by Lucas Marshall, built from his outline "NCURA AI Risk Classification Outline". Purpose: help research administrators identify the information they're handling and decide whether their institution permits its use in a particular AI tool. About 15 minutes, in three parts: understand the information and its risk level; recognize how institutional requirements differ; apply a practical decision process.)

## Interactive Question
According to a 2026 study by TrustedTech, which group uses unapproved AI tools at work more?
A. Senior Decision-Makers (correct)
B. Junior Employees

Reference (display after correct answer shown): https://www.businesswire.com/news/home/20260519849160/en/TrustedTech-Global-and-U.S.-Data-Reveals-Senior-Leaders-Are-the-Biggest-Source-of-Shadow-AI-Risk-in-Organizations?utm_campaign=shareaholic&utm_medium=copy_link&utm_source=bookmark


## Interactive Classify Data Risk
Subhead: Click HIGH · MOD · LOW for each item. What's inside it, and who can already see it?
(Interface where the audience classifies familiar research administration items as high, moderate, or low risk. No answer key, since levels vary by institution. Eight cards, each with a short descriptor: Funding Announcement (posted publicly by the sponsor) · Salary Spreadsheet (named personnel and their pay rates) · Unpublished Proposal (draft that hasn't been submitted yet) · Award Total (listed in a public award database) · AI Meeting Notes (auto-summary of a project team call) · Published Article (peer-reviewed and in print) · Confidential Research Data (protected by award terms or the IRB) · Budget Justification (draft for an upcoming proposal).)
Revealed callout: "Contents and context set the level. An award total is public, but the salary spreadsheet behind it, with names attached, is not."

## One File, Many Kinds of Information
(A mock document, "Proposal_Draft_v3.docx", with four sections. Each section's risk tag is revealed one at a time and the row tints in that color: Project Summary (public once awarded) → LOW · Preliminary Results (unpublished findings) → MODERATE · Personnel Budget (names and salaries) → HIGH · References (already published) → LOW. Final step: an arrow to a verdict card, "Whole file: High. The most sensitive piece sets the level. Handle the file at that level, or remove that piece before it goes into an AI tool.")

## Is AI Listening to Your Meeting?
(Left: a dark video-call mockup, "Project Kickoff", with tiles for a PI, a Co-Investigator, the research administrator ("You"), and an "AI Notetaker" tile with a pulsing ● REC badge. Its live transcript captures "unpublished results" and "Dr. Lee at $142K". Right: three steps revealed one at a time. 1 Notice: AI note-takers watch calendars and join meetings on their own. 2 Ask: ask the host whether an AI tool is recording or summarizing. 3 Act: if the topic is sensitive, request its removal or decline to join.)
Revealed callout: "Check the award. Award terms, program officers, or the IRB may forbid sharing research data outside secure institutional systems."

## Every Institution Draws Its Own Lines
(Three classification "ladders" side by side, most sensitive at top, revealed one at a time, with a "more sensitive / less sensitive" axis:)
- Arizona State (4 levels): Highly Sensitive · Sensitive · Internal · Public
- Big 10 School (4 levels; University of Michigan's scheme): Restricted · High · Moderate · Low
- Ivy League School (5 levels; Harvard's scheme): Level 5 · Level 4 · Level 3 · Level 2 · Level 1
Revealed callout: "Labels, approved AI tools, and approval processes all vary. Learn your institution's before you upload."
Sources line: ASU Digital Trust Guidelines · U-M Safe Computing · Harvard Information Security

## If You Are Not Paying for the Product, You Are the Product
(Large quote, attributed as "Quoted in ASU's Digital Trust Guidelines", followed by two cards revealed one at a time.)
- Free & personal accounts: Your prompts and uploads are the price of admission. They may be kept, reviewed, or used for training. → "Assume everything you enter is public"
- Institution-approved accounts: A contract protects what you enter, but each tool is approved only for certain kinds of data. → "A license isn't permission for every kind of data"

## Case Study: How It Works at Arizona State University
(Three-step process flow, revealed one step at a time.)
1. Classify the data: run it through ASU's Data Classification Tool (chips: Public · Internal · Sensitive · Highly Sensitive)
2. Check the tool and account: an ASU-approved tool, signed in with ASU credentials, approved for that data (chips: ChatGPT Edu · Gemini · Copilot Chat · "Personal accounts: public data only")
3. Review your responsibilities: follow ASU's Digital Trust Guidelines (chips: Privacy · Confidentiality · Intellectual property · Transparency)
Revealed callout: "Not sure? Ask before you upload. ASU's AI help resources: ai.asu.edu/ai-help"
Sources: https://ets.engineering.asu.edu/cybersecurity/ai-use-and-data-security/ · https://ai.asu.edu/ai-tools · https://ai.asu.edu/digital-trust-guidelines · https://ai.asu.edu/ai-help

## Four Questions Before You Upload
Scenario: You want AI to polish the wording of an unpublished budget justification.
(Four question cards, revealed one at a time, each with an "In this case" answer.)
1. What information am I submitting? → Unpublished budget details, maybe staff names and salaries
2. How is it classified? → Not public, and named salaries raise the level
3. Is this tool, account, and use approved? → Only an institutional account approved for that level
4. Who can clarify an uncertain answer? → Your research office, IT security, or AI help desk
Revealed callout: "Clear answers to all four? Go ahead. Any doubt? Ask before you upload."

## Takeaways
Key: Clear institutional guidance makes the safe choice the easy choice
-Classify by contents and context. One file can hold several kinds of data, and the most sensitive sets the level
-Treat free AI tools as public, and remember a license or local server doesn't cover every type of data
-Know your institution's labels, approved tools, and who to ask before you upload
(Classic slide with bullets)

## Section 3 Further Reading (from Lucas's outline, not shown on slides)
- University of Michigan, Appropriate Use of AI Services: https://genai.umich.edu/resources/appropriate-use
- Harvard, Generative AI Guidelines: https://www.huit.harvard.edu/ai/guidelines
- Harvard, Best Practices for Using Generative AI: https://privsec.harvard.edu/best-practices-using-generative-ai
- NIST, Generative AI Risk Management Profile: https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.600-1.pdf
- NIST, AI RMF Explainer Video: https://www.nist.gov/video/introduction-nist-ai-risk-management-framework-ai-rmf-10-explainer-video
- EDUCAUSE, How Higher Ed Can Innovate on AI Without Sacrificing Privacy: https://er.educause.edu/podcasts/educause-shop-talk/2026/how-higher-ed-can-innovate-on-ai-without-sacrificing-privacy
- University of Michigan, Generative AI Workshop Recordings: https://www.mivideo.it.umich.edu/genai

Open items from Lucas's outline: research federal sponsor AI usage guidelines (e.g., NIH NOT-OD-23-149), and find real cases where data was improperly used.

# Conclusion

## Question and Answer Time

## AI4RA External Evaluation
Please take a moment to share your feedback on today's session.
- Point your phone's camera at the code
- Or visit bit.ly/3NwQpTi
(Large QR code on the right, evaluation_survey.png, with the short link beneath it. The QR code and bit.ly link both open the AI4RA survey at surveymonkey.com/r/AI4RAgeneral. Source: docs/img/evaluation_survey.png in https://github.com/ui-insight/REACHWorkshop2026)

## Contact Information
Nathan Wiggins: nathanwiggins@suu.edu (photo: wiggins.jpg)
Bert Baumgaertner, Founder of the AI Ethics & Inquiry Outfit and Professor of Philosophy, University of Idaho: bbaum@uidaho.edu (photo: Bert.webp)
Lucas Marshall, Research Advancement Administrator, Arizona State University: lucas.marshall@asu.edu (photo: marshall.jpeg)
