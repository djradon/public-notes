---
id: bxt5kkgpz91qwks4tomx39h
title: How We Made Ai Diplomacy Work
desc: ''
updated: 1750897498487
created: 1750885121412
---
- https://every.to/p/how-we-made-ai-diplomacy-work
- topics: [[game.ai-diplomacy]]

## Lessons Learned

Inference speed matters more than most people realize

Gemini Flash 2.5 was amazing to test with. It balanced cost, quality, and speed—when Flash 2.5 agents played all seven player slots, they finished entire games in minutes. Conversely, DeepSeek-R1-05-28, despite being incredibly capable and cost-effective (around 200 times cheaper than o3), took nearly three days per game because of how slowly it typed (i.e., its tokens per second). Speed isn't everything, but it matters if you want people to use your system regularly. I'd love to see tokens per second as a more talked-about form of evaluation.
Parsing nearly killed us

Every model had slightly different opinions on how to add enough structure to their output to make it possible to turn their musings into the right format for the game to use. We kept adding Band-Aids until our code worked well enough, but it looked like spaghetti. Each new model meant new edge cases, failures, and patches. We considered the tool Pydantic AI, specifically built to handle the changing outputs of language models with exhaustive checks and auto-retries if they got it wrong—but the cost and time of regular retries add up (each game can cost over $100 without any retries). Upon reflection, I think the best approach is likely not forcing an output structure at all from the models initially; instead, we should use a second, smaller model, whose only job would be to take the raw response and give back something properly formatted for the game engine. Research has shown that structured outputs can hurt the creative abilities of these models, so while it might cost a bit more to run a second call to an LLM for formatting, I would bet that quality goes up. Intuitively, it makes sense that asking models to do too much confuses them, as they predict one word at a time. We'll be testing this next, so stay tuned.
Combining reasoning and final actions reduces hallucinations dramatically

Maybe unsurprisingly, giving the agents a chance to think step by step and explain their reasoning before they submit their final orders greatly improved the quality of play. Next on our list: applying this same technique to negotiations (which happen between players and are separate from the orders each player gives to make their moves). We suspect this will lead to more strategic discussions and reduce errors even further.
Good context allows models to be themselves

Giving agents more context about the game in fewer words translated into an improved quality of gameplay and clearer strategic differentiation. You could think of these differences as the models’ in-game personalities: R1 showed off its flair for dramatic prose, Gemini 2.5 Pro got confused when smaller models would make mistakes, and Claude got upset when o3 began "gaslighting" it. There are many real, measurable ways to evaluate how well different models understand and leverage context. We're pouring over the data now to try and put it into a paper—coming soon.

If you're curious to see more technical details or even get hands-on yourself, the codebase is on GitHub. Star it, fork it, or—even better—join us. We're looking for collaborators to expand AI Diplomacy into a game where humans customize agents to play against each other, or to explore reinforcement learning with our data. Reach out to Alex@every.to if you'd like to get involved; I’d love to hear from you.