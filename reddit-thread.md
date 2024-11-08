# I think i figured out how to build AGI. Want to get some feedback.

It is theorized in neuroscience field that human brains work by the free energy principle.

[https://en.wikipedia.org/wiki/Free\_energy\_principle](https://en.wikipedia.org/wiki/Free_energy_principle)

The free energy principle proposes that biological systems, including the brain, work to minimize "surprise" (or prediction error) between their internal models and their sensory inputs. In essence, organisms try to maintain their state within expected bounds by either:

\* Updating their internal models to better match reality (perception)

\* Acting to change their environment to match their predictions (action)

Think of it like a thermostat that both predicts room temperature and acts to maintain it within an expected range. This principle suggests that all biological self-organizing systems naturally work to minimize the difference between what they expect and what they experience.

If this theory was true, it seems likely that such a system could be replicated in machine learning field. And turns out, it was successfully implemented, in this reinforcement learning algorithm SMIRL.

SMiRL: Surprise Minimizing Reinforcement Learning in Unstable Environments

[https://arxiv.org/abs/1912.05510](https://arxiv.org/abs/1912.05510)

Interesting things from this paper:

\* This algorithm works without explicitly stating any goals.

\* It is great at imitation learning.

\* It is a great additional reward signal, when the main reward signal is sparse and rare.

\* You would think that the surprise minimizing agent, would not do any kind of exploration. But it actually did. **It seems, that curiosity, exploration, naturally emerges from surprise minimization, because even if it increased short term surprise, it decreased the long term surprise considerably.**

I then realized, that the way this SMIRL model works, is very similar to how Liquid Time Constant Networks work.

[https://arxiv.org/abs/2006.04439](https://arxiv.org/abs/2006.04439)

**They are similar in a sense, that it would explain WHY Liquid neural networks work at all,** as even people who invented it have little clue why it actually works.

Here is the video, of a LTC network driving a car, with just 19 neurons: [https://x.com/MIT\_CSAIL/status/1316033611368366080](https://x.com/MIT_CSAIL/status/1316033611368366080)

Here is the full video from which that twitter video clip was taken from:

[https://youtu.be/IlliqYiRhMU?si=nstNmmU7Nwo06KSJ&amp;t=1971](https://youtu.be/IlliqYiRhMU?si=nstNmmU7Nwo06KSJ&amp;t=1971)

Closed Form Continuous Time Neural network, is an updated version of liquid neural networks. In its paper, the car driving task is examined.

[https://arxiv.org/abs/2106.13898](https://arxiv.org/abs/2106.13898)

In comparison, it would have taken 1000s of neurons for other models to do the same task of driving this car.

Remarkable things about it:

\* It can achieve the same things as other neural networks, with 10-20x less neurons.

\* It somehow learns true causality relationships of the world.

\* It has excellent skills of generalizing out of distribution, doing the same task with completely different context.

\* It can work without stating any goals.

\* It is great at imitation learning.

The new modification that LTC models bring, is that they allow variable speed of change for each neuron, in real time. And that alone, led to all those innovations.

This LCT model was trained using offline backpropagation. **But then, i stumbled upon a version of LTC model, that learned in real time, online.** Like how actual human brains learn.

"Accurate online training of dynamical spiking neural networks through Forward Propagation Through Time"

[https://arxiv.org/abs/2112.11231](https://arxiv.org/abs/2112.11231)

This is a combination of Forward Propagation in Time+ Liquid Time Constants+ Spiking Neural Networks.

Some remarkable things about it:

\* Spiking Neural Networks, is how our human brains work.

\* Addition of LTC fixed many prior problems of SNN training, bringing it to the SOTA level.

That made me interested in how Spiking neural networks worked. I learned that spiking neural networks, is how real human brains work. And the learning is done via spike timing dependent plasticity (STDP). Problem was, that no one prior was able to create an effective algorithm for STDP learning for artificial neural networks.

That might be because STDP learning is actually incredibly diverse, variable. Meaning that the standard model of STDP was insufficient to describe all variations of STDP learning.

"Beyond STDP-towards diverse and functionally relevant plasticity rules"

[https://www.researchgate.net/publication/326690440\_Beyond\_STDP-towards\_diverse\_and\_functionally\_relevant\_plasticity\_rules](https://www.researchgate.net/publication/326690440_Beyond_STDP-towards_diverse_and_functionally_relevant_plasticity_rules)

That made me stumble upon this research paper.

"Sequence anticipation and spike-timing-dependent plasticity emerge from a predictive learning rule"

[https://www.researchgate.net/publication/373262499\_Sequence\_anticipation\_and\_spike-timing-dependent\_plasticity\_emerge\_from\_a\_predictive\_learning\_rule](https://www.researchgate.net/publication/373262499_Sequence_anticipation_and_spike-timing-dependent_plasticity_emerge_from_a_predictive_learning_rule)

What those researchers did, was that they basically made a learning algorithm that tried to minimize its surprise, and to make accurate predictions. **And that individual neuron level surprize minimization behavior, led to the emergence of STDP learning**. So surprise minimization based learning rule for neural networks, by itself emerged into STDP learning rule. And this learning rule, also was able to create different variations of the STDP learning rule, that matches the diversity of it in the human brain.

So those neuroscience researchers basically discovered an effective learning algorithm for Spiking Neural Networks.

**So it truly seems, that surprise minimization, underlies literally everything inside the brain. From the general cognition, to the level of individual neurons.**

So what if we combine Liquid Time Constant Neural networks, with this new surprise minimization based learning rule for individual neurons? Here is what i theorize what this model would be like:

\* It can learn in real time, without the need for backpropagation. 10-20x lowering the training time and costs.

\* Surprise minimization naturally leads to curiousity, exploration, so as to minimize total long term surprise. So this model will naturally conduct self-play, exploration, etc. and be capable of learning without any supervision.

\* The SMIRL model was capable of playing videogames by itself. You can create a video game around learning and using language, using an LLM. And this model will be able to master this videogame by itself and learn language that way by itself.

And it would learn language, with 100x less training material, compared to LLMs. Because it already had ability to reason prior. While in LLMs, reasoning emerges only while learning language.

**So now you would have an AI, that can continuously learn, improve, and which learned to use the language as a tool.** Its cognition, reasoning would would have been there before learning Language, not after. Learning to use language would just enhance its reasoning.

Why would this be AGI? Why would this be better than LLMs? We can find that out, by looking at what LLMs are bad at. LLMs are bad at true learning. They need millions of examples of text about some topic, about some skills, to be good at it. It can't learn things with few examples, for the life of it. This is brilliantly illustrated, by the ARC-AGI benchmark.

[https://arcprize.org/](https://arcprize.org/)

Why are LLMs bad at solving those new problems that are out of distribution from its training data? **LLMs are bad at solving ARC-AGI puzzles, because they have no knowledge, of the PROCESS of problem solving, puzzle solving.** It doesn't have the mental ROUTINES, habits, that we constantly use for problem solving, and living in general. What do i mean?

It can be explained by this research paper about AI, from 1987.

"1987-Pengi: An Implementation of a Theory of Activity"

[https://citeseerx.ist.psu.edu/document?repid=rep1&amp;type=pdf&amp;doi=cb53a49a1187650196cf10835a0193ae0201a75f](https://citeseerx.ist.psu.edu/document?repid=rep1&amp;type=pdf&amp;doi=cb53a49a1187650196cf10835a0193ae0201a75f)

And by this paper from 2007, by Hubert Dreyfus.

"Why Heideggerian AI Failed and how Fixing it would Require making it more Heideggerian"

[https://leidlmair.at/doc/WhyHeideggerianAIFailed.pdf](https://leidlmair.at/doc/WhyHeideggerianAIFailed.pdf)

What they basically say:

\* Temporal nature of the world (things happening in real time, continuously) and the constant interaction of the humans with it, is critical for the functioning of human intelligence.

\* Humans constantly use routines, to function in the world. It allows them to save tons of computational energy.

\* Humans use mental routines, when they are achieving goals, solving problems, puzzles.

\* You cannot model good intelligence, without a mechanism for formation of routines and their usage.

Why do they say, that good AI cannot be created, if it is not in constant contact with continuous time, real time environment? **Because this constant interaction with the environment, allows us to remove the need to make prediction in 95% of cases.** It allows you to use much simpler routines, that still achieve highly accurate results. Saving tons of energy, computation, memory. It allows you to remove the need for 95% of memories.

Example:

Lets say you want to dive into a pool. But then realize that it might be very cold.

There are 2 things you can do:

1. make a prediction about probability of the pool being cold, from the previously known information. Make plans, predictions, and then decide in the spot, to jump into the pool, cannon ball style.
2. Just put your finger in the pool. If its cold, you would decide to not dive into the pool.

For 95% of the tasks that humans constantly encounter, the second way of achieving goals, of doing tasks, is sufficient. **Because truly, if you used your full cognition for literally every single micro-decision you have to make, your brain will just get fried.** It simply won't be able to keep up with updating time. By the time you make a prediction, plan, goal, and decide to take an action based on it, the time already went by, and you have 10 more tasks you need to urgently finish.

**In this particular instance, the second solution, is a routine for automatic error-correction, self correction.** Sure, your finger is now wet. But that is not a tragedy, it is a trivial loss. Yet it allowed you to avoid having to plan, predict, define goals, etc. in this scenario, saving tons of brian energy.

There are 100s of such error-correction, self-correction routines in the human brains, that allow you to avoid having to make predictions, plans, etc. saving tons of brain power and time.

Second example:

* You guys probably have PC or laptops. Well, you don't need to plan every day, to sit in front of it. What happens, is that you see your PC, and that activates a habit/routine in your brain, that makes your turn it on and scroll reddit. **Planning is unnecessary here, because the environment itself serves as a trigger, for an appropriate action, in appropriate time and place.**

Now this makes it more obvious, why LLMs are very problematic for achieving general intelligence. Because they are cut-off from the constant interaction with the world. Making them hugely reliant, on planning, prediction making, goal driven behavior, because it cannot leverage the interaction with the real world, to develop simple routines, to course correct its behavior along the way.

By this analogy, Language models do use their full 100% cognition for every micro decision they have to make. Unlike us humans.

Fun fact - a "disadvantage" of liquid neural networks, is that they can only be trained on temporal, continuous-time data. Like video, audio. And not on text. **Constant interaction with the world, is the life and blood of liquid neural networks! I**t literally cannot function without it. Just like real human cognition.

(To clarify, there are liquid network based language models, so it is possible to find a solution around this problem. But by default liquid networks cannot be trained on non-temporal data.)

What is a routine? Let me give you examples of mental routines we use, when we solve problems, puzzles.

\* When you ride a bicycle, do you constantly predict the position of your body, its inertia, etc. based on laws of physics, using formulas, and then after making a prediction, adjust your actions, then make a new prediction, again and again? No, you just ride the bicycle, without awareness of such calculations. Because such calculations are not happening. Such predictions are not happening. What happens in actuality, is that you simply developed routines, for self-correcting your center of mass. When you lean slightly right, more than you should, it simply triggers a routine in your brain that makes you tilt slightly to the opposite side.

\* We use the same invisible routines, when we solve problems. Example: When you have an object at hand, you are capable of instantly seeing how far you can throw it, what trajectory it will follow, and where it will roughly land. This is problem solving. Yet, you perform it constantly, without using any kind of physics formulas. Because humans have developed effortless mental routines, for correctly throwing things.

**And there are 100s or more such routines we use for problem solving, that we are simply are not aware of, that we can't explicitly write into the AI model.** The only way the AI can learn those routines, is by learning those routines by itself.

**The LLMs cannot solve ARC-AGI puzzles, that average humans can easily solve, because it has no knowledge about the process of problem solving.** Only about its description. Current top LLMs only are able to infer only small amount of implicit hidden mental routines, that humans use for problem solving, from texts available in the internet.

LLMs are good at math and coding, because the problem solving routines for those tasks are explicit, are extensively described in texts. With formulas, etc. There are no textbooks, describing the formulas of implicit routines inside the human brain.

This is where my previously described neural network model comes in.

**It is my belief that Liquid Time Constant Networks, work based on routines, just like humans.** That is what allows it to perform the same task that would take a traditional neural network 1000s of neurons, in just 19 neurons. Because it doesn't need to make any predictions. It is able to encode just handful or routines in those 19 neurons, that enable it do the same tasks, without a need to make any kind of predictions.

If my proposed neural network is better, surely it could solve an ARC-AGI puzzle then, right? I believe so. Here is how this AI model can solve the ARC-AGI puzzles.

\* Record many videos, of people solving ARC-AGI puzzles, solving the public dataset problems.

\* Put eye trackers on those people, so that it is visible where those people are looking at.

\* Record the brain scans of the people solving those puzzles. Certain mental routines will activate certain brain regions, in certain sequences, giving the AI more clues for reverse-engineering those routines.

\* Train the liquid neural network on this data.

Here is the result i expect:

\* The liquid neural network will be able to reverse-engineer the problem solving routines people use, and be able to use it itself.

Then just ask it to solve a new ARC-AGI problem, and it will solve it.

This post is all over the place. But yea, i hope you got the general idea behind this AGI architecture.

**TL/DR: Listen to this audio podcast version of this post.** Explains what i tried to convey, much better than me. In just 6 minutes (if you use 2x speed). [https://notebooklm.google.com/notebook/ec78988a-b2d3-42ca-ace6-48e49bdb56cf/audio](https://notebooklm.google.com/notebook/ec78988a-b2d3-42ca-ace6-48e49bdb56cf/audio)

[permalink](http://reddit.com/r/LocalLLaMA/comments/1glezjy/i_think_i_figured_out_how_to_build_agi_want_to/)
by *Radlib123* (↑ 1029/ ↓ 0)

## Comments

##### Yeah, you are going to need a lot more experimental evidence than that; you can't just claim that a technique will be multiple orders of magnitude better just by linking some papers which don't show that in any way.

You made some pretty huge leaps in logic from "snn's are how human brains work", "fptt is better than backprop at training *snn's*", and "suprise minimization approximates STDP" to having a model which learns with 10000x less data and is 100x less expensive/faster to train.

Also, that 19 neuron example isn't exactly correct. It is 19 neurons making the decisions, but there is still a whole cnn model taking in the input and presumably doing the heavy lifting by extracting features.

And neural plasticity probably doesn't matter much for short-term tasks like ARC-AGI, that is just using already existing neural circuits. Essentially it is just the same as in-context learning which LLM's can do, and also doesn't require millions of training examples.

I think that if you actually try implementing this, you will find that back-propagation over a dense network is still much better. If not, then congratulations, you found the magic bullet which thousands of researchers over decades of work didn't find. ⏤ by *Someone13574* (↑ 611/ ↓ 0)
├─ The Reddit peer review ⏤ by *Christosconst* (↑ 423/ ↓ 0)
├── This is honestly much better than most real peer review I've had. ⏤ by *acc_agg* (↑ 234/ ↓ 0)
├─── Agree ⏤ by *Radlib123* (↑ 74/ ↓ 0)
├─── “You didn’t cite &lt;lab name&gt;.” ⏤ by *Soramaro* (↑ 20/ ↓ 0)
├──── That's what the famous

"And other studies.^[4-1040] "

Is for when you need to cite a bunch of papers you didn't use. ⏤ by *LoyalSol* (↑ 22/ ↓ 0)
├─── deleted 
├── Reflection (CoT) ⏤ by *fish312* (↑ 11/ ↓ 0)
├── Article proposed for improvements hahaha love academic reddit ⏤ by *Juan_Sanz* (↑ 2/ ↓ 0)
├─ I'm shocked this guy actually linked research papers.  

Of course it's still pretty much pure supposition but it's at least fat more thought out than these kinds of posts normally are. ⏤ by *IsActuallyAPenguin* (↑ 9/ ↓ 0)
├─ Fair about 19 neurons. But the CNN is only doing the feature extraction, making those 19 neurons still the centerpiece decision makers.

&gt;And neural plasticity probably doesn't matter much for short-term tasks like ARC-AGI, that is just using already existing neural circuits. Essentially it is just the same as in-context learning which LLM's can do, and also doesn't require millions of training examples.

My point is that LLMs are missing a ton of hidden implicit problem solving methods (mental habits/routines) which people use to solve such puzzles, and that is why it struggles to solve ARC puzzles. Fine-tuning the LLM millions of times will not help here, because you can't extract those implicit problem solving routines no matter how many times you fine-tune the LLM. ⏤ by *Radlib123* (↑ 57/ ↓ 0)
├── That's why we like our networks deep 😂

But I definitely agree with the idea that implicit reasoning can be a bit of a challenge for models - and honestly I thought o1 using TTC would help alleviate this but so far its ARC-AGI performance (well, o1-previews) was not exactly what I was expecting. Will definitely be curious to see full o1 plus image support for this though.

Also about the LTC research that only needed a few dozen neurons to drive a car - you do realise the same researchers have already tried to apply this to LLMs and formed a company around this research called LiquidAI, right? And they've released a multi-billion parameter LLM and its not really that much better than a transformer given similar param counts ⏤ by *FeltSteam* (↑ 42/ ↓ 0)
├─── Hey i know you... from somewhere.. idk where but i remember your nickname.  


About Liquid AI.  
1. their models outperform SOTA, but they only released small models.  
2. I expect they will be able to further squeeze those models. Its only a recent invention after all. ⏤ by *Radlib123* (↑ 16/ ↓ 0)
├──── And also honestly it seems like a lot of what you've proposed is already being done/implemented in some way and it's helping but I don't think we are precisely at AGI yet lol. Like a thing you mention here also seems to be essentially active learning - which I think Anthropic is utilising with Claude (i.e. compute use) and also OpenAI with the o1 series.

And the LFM do seem to perform well, but as I mention its not like orders of magnitude more performant than what we've seen with same sized transformer models. Any efficiency gains are very much welcome of course ⏤ by *FeltSteam* (↑ 9/ ↓ 0)
├───── &gt;And also honestly it seems like a lot of what you've proposed is already being done/implemented in some way

People miss huge innovations, even CEOs and scientists. This happened many times in history. I think there is huge probability, that major AI labs are simply unaware of what i am talking about, and are hyperfixated on incrementally improving LLMs. ⏤ by *Radlib123* (↑ 14/ ↓ 0)
├────── &gt;So what if we combine Liquid Time Constant Neural networks, with this new surprise minimization based learning rule

I mean like here, someone I know saw this post and noted "current models already end up doing surprise minimisation, they are constantly trying to reduce the loss and end up essentially continually reducing the perplexity they end up having on a given text, and the perplexity is basically how surprised the model is."

Innovations can slip away unnoticed at time - areas that can be improved upon that goes unnoticed for a time. But I also think just saying this might be a solution could help maybe but its also not nearly as helpful as trying to fix the problem.

And as I did point out - the researchers have already implemented their liquid NN - a multibillion parameter model likely trained on an extremely extensive dataset (though would be good if they released how much compute and the size of the pretraining set was used for their models) that doesn't actually outperform their transformer counterparts at the same sizes by all that much. As I also mention any efficiency gain is very welcome, but the results haven't been earth shatteringly good. And they also required a lot of extra years to even get to get to this point. ⏤ by *FeltSteam* (↑ 7/ ↓ 0)
├─────── &gt;And they also required a lot of extra years to even get to get to this point.

Not really. I think the Liquid AI as a company is barely older than 1 year.

&gt;current models already end up doing surprise minimisation

What i meant, is a learning algorithm that isn't using backpropagation for learning. But learns in real time, online. ⏤ by *Radlib123* (↑ 7/ ↓ 0)
├────── this is very simple. when you do anything for a long time, you start to have horse glasses and that makes you not see anything else. you will be surprised how many complicated things in this world actually have very simple solutions. reading the above, I think I can adapt to what I already have to make the results even better. ⏤ by *Mulan20* (↑ 6/ ↓ 0)
├────── That is only an argument for the past few years when money is being thrown at anything LLM ⏤ by *MountainDog7903* (↑ 2/ ↓ 0)
├──── Liquid AI has a 40B model that is substantially less intelligent than most 7B models. While it performs well on specific tests, its ability to generalize its training to unseen tasks is absolutely abhorrent. Performance across medium contexts is also abysmal. Have you ever tried to do anything meaningful with a Liquid model? ⏤ by *WH7EVR* (↑ 5/ ↓ 0)
├──── deleted 
├─── &gt;they've released a multi-billion parameter LLM and its not really that much better than a transformer given similar param counts

Well, maybe is OT, but imo finding an architecture that is even at the same level of transformers is still a good results. ⏤ by *Distinct-Target7503* (↑ 6/ ↓ 0)
├── Also as to "you can't extract those implicit problem solving routines no matter how many times you fine-tune the LLM" isn't this kind of exactly what OpenAI has done with o1? Not with fine-tuning but RL though ⏤ by *FeltSteam* (↑ 6/ ↓ 0)
├─── Funny thing about o1. It is seems to be exactly the opposite hehehe.

[https://news.ycombinator.com/item?id=41999340](https://news.ycombinator.com/item?id=41999340)

"Chain-of-thought can hurt performance on tasks where thinking makes humans worse"

Basically, o1 performs worse, at tasks where humans think fast, decide fast, by utilizing the mental routines. Basically, thinking more is the polar opposite of using mental routines. ⏤ by *Radlib123* (↑ 13/ ↓ 0)
├──── Yeah we do observe a drop in performance, but what if it's just an overthinking issue where o1-preview (it is just o1-preview which is not as extensively trained as o1. In fact o1-mini outperforms it in a few areas) is essentially getting distracted too easily? I think that is fairly solvable actually with more training. But, I do not think o1 (atleast full o1) is simply just doing CoT, and we know OpenAI is extensively using RL to train this model. In fact I think this is likely what they have done:

https://preview.redd.it/ecqkj7c4gfzd1.png?width=830&amp;format=png&amp;auto=webp&amp;s=7b0a628266581040033631e695388f31ed9ee994

And like you mention:

&gt;\* Record many videos, of people solving ARC-AGI puzzles, solving the public dataset problems.

&gt;\* Put eye trackers on those people, so that it is visible whey those people are looking at.

&gt;\* Record the brain scans of the people solving those puzzles. Certain mental routines will activate certain brain regions, in certain sequences, giving the AI more clues for reverse-engineering those routines.

&gt;\* Train the liquid neural network on this data.

But I think what OpenAI is doing in their training set is instead of modelling what humans would do (or as you put here try to gather as much data from humans as you can and try to emulate that) you are getting the model to simply explore how to reason to the solution (not come up with a bunch of solutions with human evaluators and mimicking the reasoning process of humans), and using RL to reward or punish the model. It's active inference - and it actually seems to be working.

I think active training could also just lead to better mental routines in models - and putting it upon them by getting them to copy humans could work to a point, but I think getting the models to do it themselves is far more scalable and more useful in the longer term. Distilling the "mental routines" of people down to models seems like a way to help models initially, I mean we are already kind of doing that with LLMs and the huge pretraining sets with many mental routines observed in those training sets themselves anyway (its obviously not completely perfect copy though).

And I also do think Anthropic is utilising active learning with Claude and Claude computer use. ⏤ by *FeltSteam* (↑ 9/ ↓ 0)
├───── I do think that scaling LLMs alone can reach AGI, if it reaches a point where it is smart enough to conduct AI research. I just think that my approach might take couple years less, and couple trillion dollars less. ⏤ by *Radlib123* (↑ 9/ ↓ 0)
├────── I think I more broadly agree with you, and I do like your exploration here. It's good to think through these things and share your thoughts. And it is as you point out: It may be the case scaling LLMs alone could get to AGI but any and all algorithmic efficiencies, newer techniques or whatever research bares fruit to is very much welcome and could help us towards getting to AGI or even ASI in a more practical and faster way. ⏤ by *FeltSteam* (↑ 10/ ↓ 0)
├─────── my man! ⏤ by *Radlib123* (↑ 7/ ↓ 0)
├────── deleted 
├──── deleted 
├── You are correct.

Modern ML/AI are missing some key functionality that constitutes our brains.

Plasticity is key btoth for short term and long term, and understanding that they are parsimonious is likely the path forward. ⏤ by *LiveBacteria* (↑ 2/ ↓ 0)
├── deleted 
├─ &gt; And neural plasticity probably doesn't matter much for short-term tasks like ARC-AGI, that is just using already existing neural circuits. 

The current model at the top of the ARC-AGI leaderboard and I think several previous leaders use test-time finetuning (additional training on the test example and some transforms of it at test time), so I don't think you can say that. ⏤ by *muchcharles* (↑ 8/ ↓ 0)
├─ \&gt; back-propagation over a dense network is still much better

Some of the key insights have already been discovered: experiments have shown that the brain is highly recurrent, sparse, modular and uses three-factor learning not (only) out of computational concerns, but because these allow it to gradually ***compose*** mental representations. The Prefrontal cortex can thus act as a plumber to create a 'global workspace' by connecting mental representations and blending them, creating emergent representations (essentially, working memory) to solve the task he wants to. Without composability, you're just doing inflexible pattern matching, not understanding. There is a psychology, but nonetheless insightful, book on this blending of concepts: 'The way we think'. ⏤ by *cgcmake* (↑ 3/ ↓ 0)
├─ I thought u could do it via one domain to predict the future. Plus reinforcement learning. ⏤ by *Due_Town_7073* (↑ 2/ ↓ 0)
├─ deleted 
└────

##### OK, you have me curious enough to try this. I am going to replicate the methodology you laid out here, construct a RLHF algorithm based on it, then have it play Qbert. I will tell you how it goes afterwards.

  
Edit: Lots of RemindMe's on this lol. Here is the code: [https://colab.research.google.com/drive/1oRFoyIFtU-YgQZ1hfXCXeBrsQ-sLs6c9?usp=sharing](https://colab.research.google.com/drive/1oRFoyIFtU-YgQZ1hfXCXeBrsQ-sLs6c9?usp=sharing) 

RL takes a long time before the bot even does anything noticeable, like hours and hours and hours. The OP's post mentioned two research papers that caught my attention, they are what I built into this. A Surprise Minimization Layer and a Liquid Time Constant Layer. It made my training go from \~30 hours to \~26 hours total estimated time to complete. I didn't feel like running it on my GPU for 30 hours straight to see if it was significant over anything else I have tried. It was not on face. I like the math. ⏤ by *FaultInteresting3856* (↑ 244/ ↓ 0)
├─ You actually read / understood this in 7 minutes and have enough knowledge to pull this off? *grabs popcorn* ⏤ by *schnazzn* (↑ 191/ ↓ 0)
├── This all assumes that modeling temporal aspects of cognition is sufficient for achieving human-like intelligence. ⏤ by *DangKilla* (↑ 28/ ↓ 0)
├─── It's not. Dude laid out a lot here but even the complexity described in this post is many orders of magnitude less complex than even like a hamster brain. ⏤ by *halfanothersdozen* (↑ 25/ ↓ 0)
├──── Those are a lot of words just to reword the Free Energy Principle, proposed by Karl Friston. He posits that the brain is essentially a predictive machine, constantly minimizing "surprise" or "free energy". 

OP probably went down a YouTube rabbit hole, and came away with an understanding of an interesting subject, but there's nothing new here. ⏤ by *DangKilla* (↑ 17/ ↓ 0)
├── OP jumps from FEP to LTCN without drawing a coherent connection, although they are very convinced there's one there. ⏤ by *DigThatData* (↑ 5/ ↓ 0)
├─── I guess i connected them this way in my mind:

* Forward propagating Liquid Spiking Neural networks, can effectively learn in real time.
* An actual learning algorithm for biological spiking neural networks is STDP.
* If you make individual neurons conduct surprise minimization, they converge into the STDP learning rule by itself.
* You can replace the forward propagation here with a surprise minimization, and it will basically work the same.
* I suspect that training Liquid neural networks via backpropagation, approximates to the same exact network as training it online with surprise minimizing neurons.

Thats how i connected free energy principle with liquid neural networks ⏤ by *Radlib123* (↑ 18/ ↓ 0)
├──── &gt; You can replace the forward propagation here with a surprise minimization, and it will basically work the same.

I think this is where you lose me. Not because I disagree, but because you could say the same thing about any learning rule. You could replace SGD with surprise minimization. This isn't a thing that is specific to liquid networks.

In any event, I think you'll find this work really interesting. Uses surprise minimization + RL to learn a UX that works however the user thinks it does.

* https://x.com/sidgreddy/status/1529244901430419456
* https://arxiv.org/abs/2205.12381
* https://github.com/rddy/mimi ⏤ by *DigThatData* (↑ 22/ ↓ 0)
├───── That does seem super interesting! Thank you for sharing those papers, will read them. ⏤ by *Radlib123* (↑ 8/ ↓ 0)
├── Typical **E**nterprise **R**esource **P**lanning enjoyer ⏤ by *LoafyLemon* (↑ 7/ ↓ 0)
├── deleted 
├─ RemindMe! AtTheHeatDeathOfTheUniverse ⏤ by *Getabock_* (↑ 18/ ↓ 0)
├─ This is very well documented, however, it's not running in colab. maybe add the pip installs on top so the environments are available?

also 1000 eps shouldn't be taking 30 hs of compute time, is that because of the architecture? ⏤ by *KillerX629* (↑ 4/ ↓ 0)
├── It won't run in colab its an RL training program. Have you ever RL trained a NN on an Atari game before? Takes \~30 hours. ⏤ by *FaultInteresting3856* (↑ 2/ ↓ 0)
├─── never on an atari game, only done cartpole. however that DQL did run on colab, so that's why I'm asking. ⏤ by *KillerX629* (↑ 2/ ↓ 0)
├──── deleted 
├─ Bro what degree do u have? How do I become a wizard like this. ⏤ by *RealisticHistory6199* (↑ 2/ ↓ 0)
├─ RemindMe! 7 days ⏤ by *Fantastic-Schedule92* (↑ 3/ ↓ 0)
├─ RemindMe! 3 days ⏤ by *KillerX629* (↑ 2/ ↓ 0)
├─ deleted 
└────

##### there’s a very thin line between geniality and madness. you crossed that line, but not sure yet on which side ⏤ by *liviubarbu_ro* (↑ 115/ ↓ 0)
├─ &gt; geniality, noun. The quality of having a friendly and cheerful manner.

You might have meant genius ⏤ by *goj1ra* (↑ 55/ ↓ 0)
├── The actual quote I'm assuming he's referring to for anyone interested...

Bruce Feirstein: "The distance between insanity and genius is measured only by success."

EDIT: Also said by the Bond baddie in Tomorrow Never Dies ⏤ by *clduab11* (↑ 30/ ↓ 0)
├─── The idea of a connection between genius and madness, and variations of this quote, go back much further - apparently as far as Aristotle. A quote that's fairly close to the version above is from John Dryden's poem, "Absalom and Achitophel," published in 1681:

&gt; "Great wits are sure to madness near allied, and thin partitions do their bounds divide" ⏤ by *goj1ra* (↑ 12/ ↓ 0)
├──── Super interesting; I always love a good piece of Aristotle information!! ⏤ by *clduab11* (↑ 2/ ↓ 0)
├─ hehehe! (mad scientist laugh) ⏤ by *Radlib123* (↑ 37/ ↓ 0)
├─ If you look at OP's post history you might have an easier time figuring out which side of the line he is on... ⏤ by *deep-yearning* (↑ 3/ ↓ 0)
├── deleted 
└────

##### slammed it into notebooklm with links as sources just starting to listen but here [https://notebooklm.google.com/notebook/db85062b-d472-42b5-a8b9-74b6b2dee150/audio](https://notebooklm.google.com/notebook/db85062b-d472-42b5-a8b9-74b6b2dee150/audio) ⏤ by *FesseJerguson* (↑ 25/ ↓ 0)
├─ Damn, thats actually great! There are some couple errors in this ai generated podcast, but it does make alot of concepts i talked about much more understandable. Great job!

Would recommend to everyone who is reading this comment, to give this audio a listen. ⏤ by *Radlib123* (↑ 10/ ↓ 0)
├── Would you mind giving a brief description of the errors that you noticed for posterity? ⏤ by *MrRandom04* (↑ 2/ ↓ 0)
├─── From what i remember, in the audio there is a description of different ai modules, talking with each other via messages. I described nothing like that, so i assume the ai hallucinated that part.

I linked a better 12 minute audio at the bottom of the post. Give that a listen instead. ⏤ by *Radlib123* (↑ 3/ ↓ 0)
├─ Thankyou - listening while I read the Reddit comments. Fascinating stuff. ⏤ by *Holodeck2014* (↑ 2/ ↓ 0)
├── deleted 
├─ deleted 
└────

##### The only way to show it works is to build it and show it can beat some benchmark better than anything else ⏤ by *chemistrycomputerguy* (↑ 19/ ↓ 0)
##### In case this is world changing, I was here :) ⏤ by *mochikambochi* (↑ 19/ ↓ 0)
├─ hehehe ⏤ by *Radlib123* (↑ 6/ ↓ 0)
├─ deleted 
└────

##### I echo someone’s comment - you are very brave for putting this out there. I think it makes a lot of sense. I’ve been working on my own ideas to solve ARC and would love your thoughts on my newest as I think it aligns with your overall thought. 

To me, the idea of how humans reason can be shown through category theory. And I think this can be applied to ARC. You could view each challenge as an equivalence class and create a sort of ARC algebra where Transformation(Input)=Output

Well, if you can capture this transformation per equivalence class you’d be able to solve that challenge. So to do this I was thinking you could do the following:

* represent a smooth latent space for “all ARC grids” using an autoencoder and Monte Carlo sampling technique
* ideally this latent space can be viewed as sort of a high dimensional graph or manifold where points are encoded grids and the space between them are (I think linear) trajectories 
* to find the transformation sequence you take a challenges training pairs and encode and stack each latent representation then using a linear regression fit you iteratively apply the transforms until you get to your target latent representations and the whole time you are minimizing the distance between where you are and where you want to be
* once you capture this transformation sequence you apply it to the test input and if that sequence solved the training pairs it’s my hypothesis it should solve the test pair, so wherever you end up in latent space you then decode it and reconstruct the output to a grid 

To me this seems to do exploration and mimic stuff without having to hardcode a DSL or something. No need for LLMs. It dynamically learns what transformations are allowed and used based on the priors from the examples. As long as you have a good representation of the search space. Which is obviously huge so I’m not entirely sure if it will work. 

Im hoping to have it coded up by this weekend. I’ve been toying with SNNs as well to build the search space and then traversal is a sequence of discrete activations. But I think I like your idea a bit more. I’m going to check out those papers for sure. 

Will let you know how it goes - feel free to msg me if this is interesting to you, would love to chat more. ⏤ by *darkmabler* (↑ 50/ ↓ 0)
├─ Subscribing to this comment because I find this very fascinating. In my own development of apps I’ve been trying to work up data flows to be able to use a combination CNN/RNN (for each type of data they best analyze) and pre-feeding my input through Transformers. So it’s like input -&gt; Transformers -&gt; CNN and/or RNN -&gt; hybrid CNN/RNN -&gt; output. ⏤ by *clduab11* (↑ 18/ ↓ 0)
├─ Thank you! I am wary of explicit categorization, representation of things for artificial neural networks. You can read about it here: 

"Why Heideggerian AI Failed and how Fixing it would Require making it more Heideggerian"

[https://leidlmair.at/doc/WhyHeideggerianAIFailed.pdf](https://leidlmair.at/doc/WhyHeideggerianAIFailed.pdf) 

Is category theory related to analogical structure mapping theory, analogical reasoning? This might be similar if so: 

[https://x.com/arcprize/status/1831031629160329582](https://x.com/arcprize/status/1831031629160329582) 

Those guys solved some ARC-AGI puzzles using analogical structure mapping. ⏤ by *Radlib123* (↑ 15/ ↓ 0)
├── deleted 
├─ deleted 
└────

##### Finished reading, You are very brave to type this out loud. I’ve thought of a variation of this idea before but never actually posted it anywhere in fear of criticism from the fact that I might not have the best knowledge of neural networks.

But you cited some papers, some very interesting papers that could prove your hypothesis (the papers are very cool; I’ve found out about some because of you, thanks!) and typed out your idea, the closest this type of thing has ever been to execution.

The open source community will likely attempt this and be finished within a month if this gains traction. 

After reading it, it will either change the world forever, or it will be another cold-fusion or LK-99 🤔

Finger cross that it will change the world forever :) ⏤ by *brain4brain* (↑ 108/ ↓ 0)
├─ Know that it warms my heart to read this comment of yours:) Thank you. We could discuss the ideas here in more detail, if you want to. i would like it. ⏤ by *Radlib123* (↑ 42/ ↓ 0)
├── Thoughts on how your approach might differ from what the folks at liquid.ai are working on? ⏤ by *milo-75* (↑ 14/ ↓ 0)
├─── Not much different. Except i think they are just running with the initial success of liquid neural networks. And have little understanding, for why it actually works. Same way many AI researchers don't know why transformer architecture works. ⏤ by *Radlib123* (↑ 25/ ↓ 0)
├──── Yuck.. liquid.ai code doesn't work mate...

I have some history. ⏤ by *medialoungeguy* (↑ 7/ ↓ 0)
├───── Do share ⏤ by *Svyable* (↑ 6/ ↓ 0)
├───── deleted 
├── Worrying what others may think is a limitation. I'm glad you posted 

I understand absolutely nothing about what you said lol But I'm glad you Did 

Sharing and having input from others. I wish you luck 🤞 ⏤ by *_arash_n* (↑ 5/ ↓ 0)
├─ Damn you just reminded me of Lk-99 :/ ⏤ by *Kep0a* (↑ 11/ ↓ 0)
├── ARE WE BACK?












... No. 


But maybe one day ⏤ by *shadowofsunderedstar* (↑ 5/ ↓ 0)
├── deleted 
└────

##### hey man make sure to eat and get some sleep when you take Adderall ⏤ by *meatycowboy* (↑ 172/ ↓ 0)
├─ let him cook ⏤ by *oblivion-2005* (↑ 35/ ↓ 0)
├─ and drink water! ⏤ by *lil_meep* (↑ 33/ ↓ 0)
├─ it's kinda sad that this level of devotion for something isn't normalized ⏤ by *mikethespike056* (↑ 37/ ↓ 0)
├── Best comment on this website ⏤ by *xarinemm* (↑ 5/ ↓ 0)
├── I don't think it would benefit many peoples lives to be obsessed about one particular thing. I know since I've done it many times, it's just not healthy. ⏤ by *GodComplecs* (↑ 2/ ↓ 0)
├─── why not? ⏤ by *mikethespike056* (↑ 2/ ↓ 0)
├─ I was thinking the exact same thing ⏤ by *not_particulary* (↑ 7/ ↓ 0)
├─ deleted 
└────

##### Please backup your claim that removing back propagation results in a 100x speedup. Are you just pulling numbers out of a hat? I'm seeing numbers more like 2-3x speedup. ⏤ by *jd_3d* (↑ 15/ ↓ 0)
├─ Yea, i guess i overexaggerrated here. But my notion of 100x speed, i meant that additional speed will also be gained by the AI itself learning autonomously by itself, removing the need for us to prepare it the training data, which itself is very time consuming. ⏤ by *Radlib123* (↑ 6/ ↓ 0)
├── deleted 
└────

##### A meta question. How did you come to discover these papers? And How are you organising the papers to support your arguments? There's a lot of fluff that gets floated on the Web, you must have a methodology to filter out the noise. ⏤ by *wahnsinnwanscene* (↑ 14/ ↓ 0)
├─ I have ADHD so i am more likely to get bored faster, as well as get distracted. So when i developed interest in AI, i basically read tons of different AI papers, in random order, based on my interest and subsiquent boredom. Basically, the Nasim Taleb way, the author of the books Black Swan, Anti-Fragile:  
[https://www.valueinvestingworld.com/2013/07/nassim-taleb-on-being-autodidact.html](https://www.valueinvestingworld.com/2013/07/nassim-taleb-on-being-autodidact.html)   


"And I could take advantage of what people later pathologized as Attention Deficit Hyperactive Disorder (ADHD) by using natural stimulation as a main driver to scholarship. The enterprise needed to be totally effortless in order to be worthwhile. The minute I was bored with a book or a subject I moved to another one, instead of giving up on reading altogether—when you are limited to the school material and you get bored, you have a tendency to give up and do nothing or play hooky out of discouragement. The trick is to be bored with a specific book, rather than with the act of reading. " ⏤ by *Radlib123* (↑ 35/ ↓ 0)
├── Still the implementation details would require some effort to execute, so culling down the chaff needs some form of organisation that would benefit from a methodical approach. Do you have a tool to aid in knowledge synthesis? ⏤ by *wahnsinnwanscene* (↑ 7/ ↓ 0)
├─── * Google docs, where i journal any thoughts i have.   

* I google any interesting idea i have about ai, like some intuitive guess about how it works, or an interesting question that popped in my mind, and that keeps helping me find more relevant arxiv research papers. This is critical actually.
* And sticky notes on my desk for critical things to not forget. That's it.

Here is a relevant meme.  (not mocking you, just find this conversation topic little funny).  


https://preview.redd.it/3s4w7w078ezd1.jpeg?width=1600&amp;format=pjpg&amp;auto=webp&amp;s=27b079e5236c9da41fa247aceaba28ac684cd974 ⏤ by *Radlib123* (↑ 17/ ↓ 0)
├──── I live in Visual Studio Code, Github, Huggingface, and Discord lmfao

That's like, the four main applications besides firefox that I use daily. For learning about AI, I've been compiling it all into a nextra docs so that anyone can access my notes or findings in an organized way themselves. It's less for me and more so other people who aren't into tech can learn. ⏤ by *Helpful-Desk-8334* (↑ 5/ ↓ 0)
├───── deleted 
├──── Yep , i tried soo many different stuff during my first year of college and and now by the end have realised that simplicity is better. notes ftw ⏤ by *Usernamealready94* (↑ 2/ ↓ 0)
└────

##### You’re basically describing a brain, so yeah I think it would work if you scale it up enough. The question is, can you scale it up enough to get state-of-the-art performance on current hardware? With a time-asynchronous system, I think it could be a lot harder, since you can’t necessarily load weights as groups of individual layers from VRAM sequentially. ⏤ by *sluuuurp* (↑ 28/ ↓ 0)
├─ Some old Nvidia GPU with 24GB of VRAM like the P40 somehow can do stuff nobody would have dreamed of back in 2016 when it was brand new. I think if someone from the future brought you future tech, you'd be shocked at what your current GPU can do with a new architecture. ⏤ by *Dead_Internet_Theory* (↑ 13/ ↓ 0)
├─ This liquid time constant Spiking neural network model ([https://arxiv.org/abs/2112.11231](https://arxiv.org/abs/2112.11231)), was trained in real time, online. And it has a constant memory, as it is trained on more and more data. So the memory stays constant, allowing scaling. Is my general guess ⏤ by *Radlib123* (↑ 25/ ↓ 0)
├── Transformers also have constant memory as they’re trained. But the main speed bottleneck is cycling through and loading all the memory for every bit of output. If you needed to do that many times independently for different neural pathways at different time steps before getting output, I could imagine the algorithm being much much slower.

That paper has just 128 neurons right? The question is if you can get it to work with a trillion neurons, or at least a trillion parameters. Humans have many more than that, and the best models have something like that. But maybe if the architecture is really good you wouldn’t need so many. ⏤ by *sluuuurp* (↑ 12/ ↓ 0)
├─── deleted 
└────

##### You aren't going to get there with that dataset. ⏤ by *roryhr* (↑ 11/ ↓ 0)
├─ Interesting. What do you think would be a better dataset? ⏤ by *Radlib123* (↑ 4/ ↓ 0)
├── I think we need another paradigm shift in our modeling and approach rather than a dataset. I don’t know what that is though.  ⏤ by *roryhr* (↑ 2/ ↓ 0)
├─ deleted 
└────

##### not gonna lie this is exact same thing i was thinking alot for long time, ppl think they gonna acheive agi just with llm which not gonna happen. ⏤ by *Zestyclose-Willow-44* (↑ 49/ ↓ 0)
├─ NeuralNet are just a canvas. Different techniques are more about efficiency for a task then any sort of binary possible/impossible. ⏤ by *Xanjis* (↑ 5/ ↓ 0)
├─ Science fiction *writers* have subtly conned us into thinking language is both the base and pinnacle of human thinking. LLMs seem to prove otherwise. ⏤ by *Dead_Internet_Theory* (↑ 4/ ↓ 0)
├── deleted 
├─ A prediction I have from this. 

It big now because we finally figured out a way to reason with machines more clearly. We already have senses (sensors). We got touch, see (lidar, echo), microphones to listen, speaker for speech but language was just code. Black or white. Yes or no. There was never a gray area. No growth. No discovery. 

Now that we have figure out reasoning. We cam put the head together. Here all the sensors so you can hear, smell (gas sensors), see, speak and now language. Since you can now thing more than us. Tell us what do you experience? 

Chain of though is already a thing. Input sensor data of everything around it, have LLM process (think) what is going on and provide an output of what it experiences(feel) around it. 

We can simulate feelings by providing facial expressions and training an LLM match expression with what feeling describes each expression. Since the face is code, make a smiley face if what you are experiencing or seeing around is calmness, nothing bad, acknowledging  that everyone. If there is chaos and people are coming towards you fast (radar sensor or echo) facial expressions match mad, look around for clues on what is happening and act accordingly and peacefully. (We are talking waaaay into the future when model energy intake is greatly decreased) 


Boston Dynamics already got the body. Slap it all together. AGI? ⏤ by *Jesus359* (↑ 10/ ↓ 0)
└────

##### I will read each of these papers this evening and tomorrow.

For now, I think you should work on creating a more robust framework for creating the data you would need to model reality in the way you describe. You mention studying eye movements and using brain scans based on the evals but this doesn't strike me as a visual only data strucuture. I'm not an expert...
 but the contribution here, what strikes me, is the feature engineering required to make the data needed to train such a model. Not some composite of other data or a cleaned set already in use- this approach warrants creating something totally new and THAT seems like an attainable goal. Think about it; you could use a smartphone camera and get high enough fidelity audio/video to build a dataset. I still need to read the papers, but the experiments you suggest, at surface level, do not seem to communicate visual information without the text component.

You seem to have a strong sense of what the model could achieve; however I think diving straight into training and trying to optimize compute would be a mistake and potentially lead you toward current SOTA. This approach gets at another level of SOTA we haven't seen yet. Figuring out how to design the data to make this approach possible requires vision you seem to have. That's where I would start.

Such an awesome post. What kinds of visual data do you think would be useful- how would you record such data? Maybe its an application for vr headsets. ⏤ by *Echo9Zulu-* (↑ 10/ ↓ 0)
├─ Thank you so much! 

Actually, you gave me a genius idea - add face recording to the dataset, alongside the brain scans and eye movements. 

And the general pattern emerges here: extract as much and every possible signal people display when they are solving the ARC-AGI challange. The more signals we receive, the more material the liquid neural network will have to draw causality relationships, and reverse-engineer problem solving routines easier. ⏤ by *Radlib123* (↑ 3/ ↓ 0)
└────

##### Commenting to prove to future generations that I was here when it happened. ⏤ by *kremlinhelpdesk* (↑ 10/ ↓ 0)
##### Surprise Is All You Need? ⏤ by *TitoxDboss* (↑ 9/ ↓ 0)
##### I'm particularly interested in your thoughts on how this architecture might handle meta-learning - not just learning specific routines, but learning how to learn new routines efficiently. Do you think the surprise minimization principle alone would be sufficient to drive this kind of meta-learning? ⏤ by *Zestyclose-Willow-44* (↑ 15/ ↓ 0)
├─ This is a great question! I think meta-learning will emerge. The thing about LTC networks, is dynamic timescales for different neurons. It has been shown in various research papers, that the slower neuron modules, groups, work as the central control. And what they do, is they combine, compose simpler routines in different ways, to create more complex routines. That way saving time, memory, energy. Instead of creating fully new routines from scratch.If the meta-learning is very important, i bet my money it will emerge by itself, without the need for outside interference.  


[https://youtu.be/NHmej5i22aE?si=29tFao8tuOVy2-iC&amp;t=3731](https://youtu.be/NHmej5i22aE?si=29tFao8tuOVy2-iC&amp;t=3731)  


Here is a machine learning lecture at 1:01:00, that allowed me to understand how the composability of routines (here they are called motor primitives) emerge. Recommend watching it. Probably would answer your question about meta learning too. ⏤ by *Radlib123* (↑ 9/ ↓ 0)
└────

##### Last comment i promise!... What if...we gave a neural network of this nature, access to an embeddings model in order to produce natural language (meaning, skipping over the LLM part and just having a self learning machine trying to produce language torwards one goal). Imagine a self learning machine discovering language along with "how to think"... Isn't that an interesting prospect?

Anyways, I'm done with MY ramblings, great post! ⏤ by *KillerX629* (↑ 7/ ↓ 0)
├─ Thats a great idea! Seriously. Would allow us to remove the overhead of LLMs. ⏤ by *Radlib123* (↑ 5/ ↓ 0)
├─ deleted 
└────

##### Don't mean to sound overly dismissive, but the ideas look like pure speculation so far. Regarding the first few points, cross entropy loss could be interpreted as 'surprise minimization' in the sense that we're minimizing E[-log q]. IIRC it has also been proven that self attention can be framed in terms of continuous hopfield networks, which minimize an energy function (https://arxiv.org/abs/2008.02217). So it can be argued that transformers already implement some form of surprise + energy minimization. I don't know much about SNNs, so I can't really comment on the other points ⏤ by *emanega* (↑ 8/ ↓ 0)
##### Fristons fMRI papers are solid and great. I checked them and replicated some of the stuff (that i could mathematically follow or were available as tool boxes).

That being said:
Fristons later work...
I would not take his verbally dictated papers, with references leading to wrong passages, nor the theories, with questionable proofs, too serious. In conferences on computational neuroscience, the physicists didn't perceive his narrative very well. I have seen FEP being roasted, and the defense being rather thin/weak/inconsistent. When people tried to implement this stuff, they mostly realized the many holes in this grand theory and there is a reason why adoption did lag behind. (Its always a bad sign if theories of the leading people result in no practical adoption besides many funded projects. I think they mostly did demonstrations in the "motor" domain, which were not really showing learning.)
I have no idea if any cool implementation grew out of it, i am  no longer in the field, but I would keep an eye on the details. I know of a few occasions where within those prestige labs, secrets were created to make things publishable. 

Fundamental critique:
I think it was the proof in box five where he proclaimed that you do not need  to solve an exploration/exploitation dilemma. The reference to the paper and the proof do not check out. Also in the following years this has not been addressed.
I would argue that a fundamental limitation on your ability to solve any learning problem by yourself would require a reasonable algorithm on how to address the E/E dilemma. If you are wrong with your exploration, large state spaces will become a problem. 
Friston's vision (based on the 2010 papers) would lead to a rather quick convergence to a repetitive solution approach, with a likely tendency (i might have this second point wring) to produce the smallest motor action possible, to produce the least change in sensory variation. (given enough freedom in your objective this equates to doing nothing). ⏤ by *dontpushbutpull* (↑ 6/ ↓ 0)
├─ In the SMIRL model, it was found that suprise minimization alone did lead to some curiousity, exploration. But it was significantly more improved, when there was an additional reward signal. 

  
In humans, this additional reward signal could be the feeling of pain and pleasure for example.  


So it is likely that surprise minimization alone is not enough. But it is a critical part of the solution. ⏤ by *Radlib123* (↑ 5/ ↓ 0)
├── Exactly.
FEP is not a cognitive architecture. If you were to build one you would need to address a good scheme to explore. Noise based explorations dont do the trick. It needs to be a strategic/model-based/goal level exploration.
Neuroscience can serve many promising entry points, but that shit is never easy to implement. I would go with ideas about pattern separation in the hippocampus and how that   might be related to BA10 &lt;&gt; OPFC interactions.
If i were to guess a computational scheme based on LLMs:
Basically one could use verbal reinforcement learning to generate alternative goal states, sort them by desirability and periodically check feasibility of the implied action plans. Then the alternative derived policies could be mixed/merged to maximize exploration on the way, while doing exploitation. ⏤ by *dontpushbutpull* (↑ 5/ ↓ 0)
├── I have a background in behavior analysis so most of this is going way over my head but I wonder for the reward signal component if that is moving more into my knowledge base (I.e Operant Conditioning). Pain, pleasure, hunger, thirst are intrinsic motivators but very quickly humans learn others through stimulus-stimulus pairing to start. Then you have motivating operations that change the value of these stimuli. I wonder if these concepts need to be integrated as well. ⏤ by *BTauburn* (↑ 5/ ↓ 0)
├─── if i may:  
these are part of the theory. 

based on conditioning, the "rescola wagner" model was established as a computational method to estimate the effect of conditioning. in the 1970s maybe? it is one of the foundations of the computational (i.e. machine learning) theory of reinforcement learning. the research was done in psychiatry and psychology -- so i feel this was very much inspired by the same gut feeling you are having,.

computational researchers (computer science and cognitive psychology) aimed at generalizing over the effect of conditioning by predicting reward based on "state" and "action". so more complex equations were derived. that was around 1990.

one aspect of state encoding could be to encode different "stimuli" in the state. some later models explicitly encode conditional stimuli or explicit kinds of conditioning stimuli. by the 2010s there were several psychiatric versions of RL to account for different stimuli-stimuli-reward chains, or different kind of reward/punishment.

with the newer kind of mainstream algorithms the computational might is often taken as a surrogate to explicit modelling of context/conditions. but i am also sure there are still hundreds of people working on modelling newest computational methods in psychiatry or animal models.

A big question to me is the validity of the Schultz 1997 papers that are frequently quoted and are at the base of many of the dopamine news-paper article. especially with regard to his earlier work, I would argue that he most likely chose to hit a specific narrative by using paradigms where novelty and reward where intermixed. while previously his own lab has shown that dopaminergic activity is rather signaling novelty than reward. ... even though replication was scares and never convinced me in context of the previous paper, the narrative became one of the most dominant narratives on in folks psychology... 

I feel our understanding of the brain as effective exploration machine would be much more advanced if this paper would have not been the basis of a larger news cycle. 

(its just like with the "anti oxidants"... it isn't a thing even though people keep reporting it in popular science.) ⏤ by *dontpushbutpull* (↑ 2/ ↓ 0)
├──── Absolutely fascinating. I only know the Skinnerism, operant behavior animal/human research side of things, so extremely interesting to hear the neurological theories and resulting computational models. Thanks so much for taking the time to explain. ⏤ by *BTauburn* (↑ 3/ ↓ 0)
├──── deleted 
├─── deleted 
└────

##### I went off this deepend a few years ago. Couple issues: Surprise minimization only works when it returns a state given an action. Your action is going to be text? How does that apply to the real world, only one I can think of is talking to humans. Ok so it’s just RLHF with the ability to predict human response as reward instead of ranked preference. Still human writing text in the loop, no autonomous learning. 

What’s bad about surprise minimization in general: it is meaningless without external reward. Standard FEP basically claims agents maintain predictable steady state. They would never leave a dark cave if they didn’t get hungry. Greedy surprise minimization is very limited in usefulness. 

Additionally, it’s not magic, SMiRL and all these other FEP in RL papers are just standard RL with a predictive world model to create an intrinsic reward function.

Didn’t read everything you write, but spiking neural nets don’t work better than standard, there is really no clear advantage. “But it’s like a human brain” commercial jets don’t flap their wings. ⏤ by *jms4607* (↑ 6/ ↓ 0)
##### I fully believe you are thinking about the right track. You have imagined a nice path forward. You probably even imagined some person walking down that path, which is like half the battle.

**The other half is doing it, though.** Become the man of your dreams! ⏤ by *Dead_Internet_Theory* (↑ 6/ ↓ 0)
├─ Thank you! ⏤ by *Radlib123* (↑ 4/ ↓ 0)
├── I notice my post might sound sarcastic btw, but I think you really have it in you to at the very least, do some really cool shit that moves the needle forward.

Just go do some of it, post findings, and hopefully the community helps you out when you invariably get stuck on a technical issue. ⏤ by *Dead_Internet_Theory* (↑ 3/ ↓ 0)
├─── yes. that would be awesome. ⏤ by *Radlib123* (↑ 4/ ↓ 0)
└────

##### What percentage of ARC-AGI can humans solve? 


I think you have a lot of good ideas, but a few wrong conclusions.


State of the art LLMs absolutely memorize and apply problem solving routines robustly and often flexibly. That's why they are so good at math (not arithmetic necessarily).


But learning on the fly _is_ a weakness of LLMs. The idea you have to use Liquid Neural Networks and/or SNNs is a good one. I think the key is going to still be having a lot of compute and memory and giving it plenty of useful  experiential data.


Also solving ARC-AGI probably isn't going to provide your "AGI" which is a meaningless word but you probably are thinking of just something that emulates a human.


I actually strongly suspect that some Chinese researchers already have a head start in scaling  advanced SNNs and will within a couple of years start applying large network with architectures similar to what you suggest to various types of robots and autonomous mobile weaponry.


That might be how WWII is won actually. ⏤ by *ithkuil* (↑ 19/ ↓ 0)
├─ &gt;What percentage of ARC-AGI can humans solve?

85% i think. Baseline Claude can solve 20% of them. The people who are reaching 50% solution, are just using something similar to brute force, search, trial and error approach, instead of true learning, which the creators of ARC themselves find little disappointing.

&gt;State of the art LLMs absolutely memorize and apply problem solving routines robustly and often flexibly. That's why they are so good at math (not arithmetic necessarily).

This works well for fields like math. Because there is tons of explicit texts about it. But this approach fails to capture implicit problem solving routines we use for other things. My theory is that it is presisely because we use so many implicit routines when solving ARC puzzles, that LLMs are bad at solving them. Plus, our routines are inherent to the temporal, time based, continuous time nature of out cognition, existense. You can't extract it into a labeled flat dataset, only into a continuous time format like video. ⏤ by *Radlib123* (↑ 12/ ↓ 0)
├── I think within a few years they may move on to SNNs since they could be more efficient, and architectures designed for online learning, like you suggest.  
  
But large multimodal transformer models can learn to ground language in spatial-temporal data from images and videos. We have already seen some of that, for example with the amazing text-to-image ability of 4o (on their website only, not released). In the next year or two, I think you will see amazing progress of world models integrating video data with transcriptions etc. resulting in more robust abilities of "LLM" type models. Although it is misleading to call the new multimodal models language models since that is only part of it. ⏤ by *runvnc* (↑ 7/ ↓ 0)
├─ deleted 
└────

##### Lots of people comparing this to liquid.ai

I'll add 2 things:

1. Read The Bitter Lesson by Richard Sutton. Simpler general methods will dominate.
2. Liquid.ai's original research wasn't replicated. And they rejected PRs to make their code work on their github for their nature paper (liquid time networks). Not credible. ⏤ by *medialoungeguy* (↑ 10/ ↓ 0)
├─ &gt;Liquid.ai's original research wasn't replicated

That's just false. I mentioned at least one other research paper in my post, about liquid spiking neural networks, that was made by completely different researchers unaffiliated with liquid ai. And it worked for them. ⏤ by *Radlib123* (↑ 5/ ↓ 0)
├── Oh no, I'm not falling for this again. It took me 30 hours to get Ramin Hasini's code to even run. And then he rejected my PR on github. This was for his nature paper years ago lol, the one you referenced. At the time I was working at a trading firm and we were very interested in the speedup available by the architecture. Happy to be proven wrong and actually works btw. In my experience, once I fixed his demo code it somewhat worked... nothing close to what was claimed though.

His big thing wasn't liquid networks themselves, but rather the analytical solution that became available for the much faster training time.

I promise I'm not being a dick. This comes from experience in the trenches. There's a reason it never took off... it's because nobody could make it work as claimed. And there was plenty of incentive to make it work. Everyone went back to transformers immediately. ⏤ by *medialoungeguy* (↑ 17/ ↓ 0)
├─── I see. I won't dismiss your complaint then. But i still do believe that liquid networks do work. ⏤ by *Radlib123* (↑ 9/ ↓ 0)
├──── By the way I'm rooting for you and want your idea to work. Maybe I'm too old ;) ⏤ by *medialoungeguy* (↑ 12/ ↓ 0)
├───── Thank you. ⏤ by *Radlib123* (↑ 2/ ↓ 0)
└────

##### Surprise minimization = AGI is not the frame you wan't. It's mostly the distinction between judging and perceving which:

*1. Chunks perceived sensory input into labelled boxes. This is Judgement; the part where certainty is achieved.*

*2. Combines the chunks into new ones by flodding the categories mixing them up together into new instances of perception. This is 'surprise'.*

  
Transformers are still extremely useful though as they work well enough as perception machines - they may encode discrete symbols but their model of the world degenerates into external energy as soon as the input leaves the context window. They dont have integrated reflectivity which should anneal and crystallize surpise into a RAG'ed technique. **Which basically causes them to run hot all the time.** They are way too certain, because they lack an unconcious component - thing which liquid nns being by architecture the extreme opposite makes them so impressive. The perfect transformer esentially has an unconcious liquid component - *a forest of patterned weights* which asks questions, and a traditional rock-solid LLM which comes up with answers. 

Now what you need is a live loop of these two factors (judgement and perception) clashing together into a whirpool of sorts - problem is that even if you figure that out you are still missing the reason why  [***neurotransmitters***](https://www.google.com/search?client=opera-gx&amp;hs=DhN&amp;sca_esv=91f756f8d95b3a2b&amp;sxsrf=ADLYWIJ63dG8Lr7EQHVfSCEw3JIvMnvdcw:1730970180586&amp;q=neurotransmitters&amp;spell=1&amp;sa=X&amp;ved=2ahUKEwi-8Ou17smJAxUELtAFHdtgPPUQkeECKAB6BAgNEAE) exist. *How do you come up with categories for them?* But since we are all now entering crackpotland, im happy to mention that I'm working on my own version of lang-graph going by these principles using micro-agents. Will open source [soon.](https://github.com/Smenos) 

Criticism aside i think you are unto something though. I personally ditched Spiking NNs for categorical spectral coefficients, and activation functions as customizable importance sampling loops with a supervisor which decides which activation gate (the flood) is good for the context and which one isnt, and it works just fine, if no flood is required then certainty is added into the traditional transformer by bootstraing a few-shot - but inference time even for llama 3b-v or phi 3.5 goes as long as o1. So it may just end up as something to play with instead of a production ready tool. My framework basically ensembles PID closed-loop controllers  and uses as a dampener of perplexity a harvesting/prune procedure based on semantic routing. It's a complex algorithm and im not training anything at all since this is meant to leverage transformers to program them with some *slick*, not replace them.

  
I'm very interested to have a chat and maybe share some ideas. ⏤ by *Still_Ad_4928* (↑ 6/ ↓ 0)
##### I also read a bit from the LTC NNs and I can, at least THINK of one of the factors into them not being used as much as other architectures... they have differential equations updating the weights, meaning that they loose the cool advantage we here at LocalLLaMA rant on about with GPUs, the matrix multiplication that's very easily made with a single gpu. If these assumptions about how fast they learn and how many neurons are needed against classic architectures is true, then this still has the challenge of having those equations for updating the neurons, making it computationally expensive AT SCALE. This topic still fascinates me and I love reading possible ways into the future of AI. ⏤ by *KillerX629* (↑ 5/ ↓ 0)
├─ deleted 
└────

##### Leaving my comment here so I can be stamped in history. ⏤ by *Curiosity_456* (↑ 3/ ↓ 0)
├─ deleted 
└────

##### how much time did you take to write this? 


what i get from this write up is you can mention few of a huge number of neuroscience papers/concepts, add a few ideas and imagine that machine will work like brain, which gets talked about again and again and again. ⏤ by *ab2377* (↑ 3/ ↓ 0)
##### I've been kind of surprised by how consistently current LLMs continue to improve with more parameters and data, but I agree that nevertheless, they seem too "weak" architecturally to really get us fully to human capabilities. I think you have some interest ideas here for what building blocks might comprise more "powerful" architectures, but it'll definitely take much more work to get anything concrete. ⏤ by *BioSNN* (↑ 3/ ↓ 0)
##### The headline made me ROFL ⏤ by *Getabock_* (↑ 3/ ↓ 0)
├─ "dudes, i think i solved quantum gravity. what's your opinion?" ⏤ by *Radlib123* (↑ 3/ ↓ 0)
└────

##### Although I cannot address the validity of your claims, I am impressed by your desire to learn and to create. Life is too short to not be curious. I am eager to attempt even a tiny bit of real time learning into publicly available systems and would love to discuss supporting your exploration. I have been brute forcing a version of the creative thinking process, and I think with your way of thinking my cluster of AIs could benefit greatly. The future can be accelerated if we manage to do something in this space and I have spent all my time outside of work playing with it. I am not without resources as modest as they are and I would like to discuss your ambitions. Lets chat :) ⏤ by *Samathura* (↑ 4/ ↓ 0)
##### RemindMe! 36 hours ⏤ by *Graded_Beast9039* (↑ 10/ ↓ 0)
├─ I think it's going to take a little bit longer to build than 36 hours. 🤔 ⏤ by *b1naryst0rm* (↑ 19/ ↓ 0)
├── Really? I was thinking 24 hours ⏤ by *nero10578* (↑ 3/ ↓ 0)
├─── I‘m ok with agi in 24 hours, 36 is definitely too long ⏤ by *schnazzn* (↑ 9/ ↓ 0)
├──── How about A couple of weeks of gratitude for magical intelligence? ⏤ by *KarnotKarnage* (↑ 2/ ↓ 0)
├── deleted 
├─ I'm here for the random redditor that revolutionized the AGI space in a single post ⏤ by *Kep0a* (↑ 13/ ↓ 0)
├─ You need to gather a lot of data, and code and train a lot of system, likely will take a day, a week max tho ⏤ by *brain4brain* (↑ 5/ ↓ 0)
├─ deleted 
└────

##### 1. **Oversimplification of Surprise Minimization:** The premise that surprise minimization is the fundamental driver of intelligence is a drastic oversimplification. While it plays a role in learning and adaptation, other crucial factors are omitted, including:
   * **Intrinsic Motivation and Goals:** Humans are driven by internal drives and desires that go beyond simply minimizing surprise. These intrinsic motivations shape our goals and influence our interactions with the world. The proposal lacks a mechanism for incorporating such drives.
   * **Social and Cultural Influences:** Human intelligence is profoundly shaped by social interaction and cultural learning. These factors influence our beliefs, values, and behaviors in ways that are not captured by surprise minimization alone.
   * **Embodiment and Physical Interaction:** The proposal acknowledges the importance of real-time interaction, but the reliance on recorded data (video, eye-tracking, brain scans) is insufficient. True embodiment, where an agent learns through direct physical interaction with its environment, is essential for developing common-sense reasoning and understanding causality.
2. **Speculative Links Between Concepts:** The proposal draws connections between various concepts (SMiRL, LTCNs, STDP) based on shared characteristics. However, these connections are largely speculative. There's no strong evidence that these concepts are related mechanistically or that combining them would synergistically lead to AGI.
3. **Challenges of Reverse-Engineering Routines:** The idea of reverse-engineering problem-solving routines from human data is ambitious but highly problematic:
   * **Data Sparsity and Noise:** Brain scans and eye-tracking data are noisy and offer a limited view into the complex cognitive processes underlying problem-solving. Extracting meaningful routines from this data would be incredibly challenging.
   * **Diversity of Routines:** Problem-solving routines are not universal; they vary significantly between individuals and depend on the specific problem. A model trained on a limited dataset of human demonstrations would likely not generalize well to novel problems.
   * **Implicit Nature of Routines:** Many routines are implicit and difficult to articulate even for humans. Capturing these tacit skills through observation alone is highly unlikely.
4. **Limitations of ARC-AGI as a Benchmark:** While ARC-AGI is a challenging benchmark, passing it doesn't necessarily demonstrate AGI. The benchmark focuses on a specific type of abstract reasoning, and success on it doesn't guarantee competence in other essential aspects of intelligence, like language understanding, social interaction, or creative problem-solving.
5. **Lack of Clear Learning Mechanism:** The proposal suggests combining LTCNs with a surprise minimization-based learning rule. However, the precise details of this learning rule are not clearly defined. How would LTCNs, which are typically trained with backpropagation, be adapted to learn online through surprise minimization? This requires a more concrete learning algorithm.
6. **Scalability and Computational Cost:** Even with LTCNs' efficiency, training a model on the scale of human intelligence would require immense computational resources. The proposal does not address the scalability challenges of training such a complex model.
7. **Interpretability and Control:** A key concern with any AGI development is interpretability and control. The proposed model, with its complex interplay of different components, would likely be a "black box" making it difficult to understand its decisions or control its behavior. ⏤ by *Yunbur* (↑ 6/ ↓ 0)
##### Excellent analysis, thank you for sharing! ⏤ by *DarkArtsMastery* (↑ 3/ ↓ 0)
##### Thanks for the audio, it helped me understand everything faster and easier. I also use notebooklm to summarize large amounts of text (research) over 11 million words. First of all, we should offer more support for such approaches, even if it sounds strange, crazy, but if we look at history we see that everything we have now is due to this type of discoveries and out of the box thinking. There are people who see patterns where we don't see them or see simplicity in things that we see as complicated. That's what happened here, in this post. for me this post is pure gold because it gave me some good ideas and a new form of approach that although I knew it, I had those horse glasses on, which made it impossible to see this new approach. There is a lot to say, but I don't want to bore you too much. im my research made some unexpected discoveries with LLM. ⏤ by *Mulan20* (↑ 3/ ↓ 0)
##### Wow, I thought this was going to be a meme about just plugging a brain into a computer.

Cool theory, but how pissed do you think researchers would be if some random redditor was the one to figure out how to make an AGI lol ⏤ by *SuuLoliForm* (↑ 3/ ↓ 0)
##### Schmidhuber, is that u? ⏤ by *Old_Formal_1129* (↑ 3/ ↓ 0)
├─ deleted 
└────

##### i was here ⏤ by *pinkyellowneon* (↑ 6/ ↓ 0)
├─ hehehe ⏤ by *Radlib123* (↑ 3/ ↓ 0)
└────

##### Surprise as a concept works well for many things - here's another very recent paper worth reading: https://em-llm.github.io/?trk=feed_main-feed-card-text ⏤ by *TheTruckThunders* (↑ 2/ ↓ 0)
##### Loved your idea. It seems to be going in a good direction from the currently used algorithms.

But I think we could do even better, not focusing so much on making a copy of humans and it's flaws, but by making something greater ⏤ by *julioques* (↑ 2/ ↓ 0)
├─ It would be worse than the current algorithms at some things while being better at others. I think we need something more, something that's not there yet. Maybe a mix? Maybe something else ⏤ by *julioques* (↑ 2/ ↓ 0)
├── Just as something additional I would like to just let out as a small note:

I never understood why they never used games to make AI learn. Something like a mix of what the post said earlier with the current LLM leaning algorithms. For example making the AI learn itself from playing a game and having to match text inside the game like it was a person in a virtual reality. Not with fixed tokens, but with something more temporal and flexible like the post said, just like a human. Instead of tokens and text, there's an image that shows a book with text, or a screen with text, and the AI received the image, not the text. ⏤ by *julioques* (↑ 3/ ↓ 0)
├─── Yea i also think video game based learning for AI has huge untapped potential. ⏤ by *Radlib123* (↑ 3/ ↓ 0)
└────

##### Some very interesting ideas here, and I think the notions relating to time exposure and routine formation are quite promising.


I'm curious how you think the brain-scan data would help the model learn that particular problem solving. Even if it got very good at modeling "here's what brain area might light up in this situation" how would that enable it to solve the problem itself better? ⏤ by *WrathPie* (↑ 2/ ↓ 0)
├─ deleted 
└────

##### I stopped reading when I got to your diving example. Our brains wouldn't "fry" as you put it. Everything you described as potentially causing a fried brain is exactly what happens subconsciously every nano second that goes by. Sorry dude. It was an interesting read till then though 👍 ⏤ by *JacketHistorical2321* (↑ 2/ ↓ 0)
├─ deleted 
└────

##### If this post is deleted in the morning what will we all think 🤔 ⏤ by *Holodeck2014* (↑ 2/ ↓ 0)
├─ sama got me ⏤ by *Radlib123* (↑ 5/ ↓ 0)
├── lol - yeah - he’s raging now he wasted all that stock on getting Chat.com… seriously why didn’t you post this yesterday 😩 ⏤ by *Holodeck2014* (↑ 2/ ↓ 0)
└────

##### Some of the concepts have flown over my head and I understood some. But, the more intresting part for me is, everytime I read a paragraph and thought, we should find/solve this , you next paragraph is like "then I stumbled onto this, I came across this, etc.," 

It was great read though and the comments section is really insightful as well.

Subscribed to the post 👍. ⏤ by *kkb294* (↑ 2/ ↓ 0)
├─ deleted 
└────

##### They all do error minimizing. Isn’t this the same as surprise minimizing? ⏤ by *davesmith001* (↑ 2/ ↓ 0)
##### Can this be summarized to mean that the fundamental unit of abstraction here is entropy ? ⏤ by *Training_Designer_41* (↑ 2/ ↓ 0)
├─ deleted 
└────

##### Lets work together, I have some AGI ideas as well. If we merge our ideas we could complete it. I feel like I have the other half. ⏤ by *StarCaptain90* (↑ 2/ ↓ 0)
├─ deleted 
└────

##### FEP is a deep and universal principle. I'm working on a paper that shows how it applies even in a social system setting. I think you're on the right track. ⏤ by *_supert_* (↑ 2/ ↓ 0)
├─ deleted 
└────

##### Very interesting read, off to read those papers and pretend I understand at least some of it. ⏤ by *Thrumpwart* (↑ 2/ ↓ 0)
##### Is just amazing what you do and think.
Thank you very much for posting here.

I will take a better look in a few days coz I think i have an idea. 
Again, amazing all. ⏤ by *comunication* (↑ 2/ ↓ 0)
├─ deleted 
└────

##### I wish it was so simple. ⏤ by *custodiam99* (↑ 2/ ↓ 0)
##### Keeping aside the AGI topic, it is surprising (pun intended) that Free Energy Principle, RL, SNNs, Liquid neural nets, the lack of temporal modality in LLMs, embodiment, all have been mentioned in a coherent chain of arguments in a single LocalLLaMa post. Too many surprises that my mental model struggles to minimize. ⏤ by *kulchacop* (↑ 2/ ↓ 0)
##### This thread is amazing. So many new things for me, thank you. ⏤ by *DarKresnik* (↑ 2/ ↓ 0)
##### This is very good stuff. I’ve been thinking along similar lines with regards to Dreyfus especially (I’m a philosophy and cs major) and this is intriguing. Keep me posted on how this goes please. ⏤ by *Low-Explanation-4761* (↑ 2/ ↓ 0)
├─ deleted 
└────

##### If you want to know how the human brain works, check Noesis Theory. It took me 18 years to reverse engineer my brain.

Described in this video
https://youtu.be/XT51TeF068U

Also a more practical example here:
https://youtu.be/cFYiWCI357E
(Sorry for the bad quality) ⏤ by *protoporos* (↑ 2/ ↓ 0)
##### Please let me take this opportunity to humbly participate onto this discussion revolving around describing a method of an artificial "truly intelligent system" by spitting my broken thoughts about it.

What bugs me every time with neural networks, even if of course some of the outputs that could be generated can be qualified as brilliant, don't misunderstand me, is the lack of "grasp" from the models of any objective, subject, action required subsidiary to a prompt.

Diffusion models, transformer-based llms, never have a signal detection and/or response of the validity of their outputs. I just compare that to how we look to operate, where there is a constant activity of processing and cognitive effort involved, through perceptual inputs or processing/brainstorming neurologic "function calling" (when we decide to draw elements from our memory to "think" literally, going into abstractions for solving mathematical problems or confronting real world examples with concepts constructions when doing philosophy), I may say.

For example, asking a large language model to output a code snippet according to a **precise objective/intention** indicated in a prompt would result to a generation of a probabilistic corpus, sequence of encoded "tokens" (for the lack of a precise word of what it is), resulting to something that somehow makes sense to us once decoded. But if there are any flaws, syntax aberrations, or totally made up shit inside, we have to prompt again the same probabilistic machine in order to "iron the edges". But at any time, the system prompted had a structured, qualified, thematically discriminative, logical approach of the demand, and moreover, any supplementary "organ" to have an abstracted way of what could happen in a roughly, simplified flow chart kind of symbolic representation. This kind of approximations we do when we have to solve a problem ad-hoc, we draw a simplified, approximative structure path of the situation projected, and focus on details where there is interest to.
The second, third, or n prompt later, this could absolutely solve the problem, but the model never had any realization of what happened, and this is only by the interpretation (or accumulation in the context window) of positive or negative signals ***by text***, of which is a strictly indirect fashion of proceeding. Like us, indirectly recognizing intelligence from the output of heavily trained models.

Same with picture generation models, where I think lack of "semantic painting" functions, where, for example, we could draw some kind of rough shapes and indicate what could it with text, be in order to compose way much better pictures, and why not, videos. Models could also learn those segmentation rules (ground lower part of the picture, sky upper part, ect) and generalize a "culture" of picture composing from intelligent metadata (anatomy, perspective, small objects afar, close objects bigger, with detail, coherence of textures, ect); rather, it seemed that massively trained diffusion models assimilate this quality by "nature" which is impressive [the bigger the model, more coherent are the outputs according to the reality], but much more "intuitionally" (implicit patterns deeply learned) rather than "by understanding" (segmented, labelled, identified in the composition, with qualified links between objects).

Like, I went to the museum recently, and, I just got "fun" with trying to segment every step the painter took in order to compose its piece. The work on the texture. The density and viscosity of his mix to obtain his tones. His touch. The moves in the X and Y axis. Deviation. Stiffness. Softness. Emptiness, fullness of the canvas. And so on. A model generating a picture today just nudges pixels from a random frame in order to emerge some shapes like an invocation, and iterates to bring the detail once the most probable shapes cannot change drastically. I thought about a materialist-approach of creating art with AI models recently, with models understanding more the reality of producing pictures with a shitload of metadata.

I also had this thought when imagining how "music generation models" could be improved (before the huge leaps from the lasts months), where (I'm firmly convinced this was done this way) the model could be composed of subsidiary others, or "layers"; for sound generation, such as percussion, voice, instruments of a type, bass (pure timbre models); and, in a kind of MoE style, a model of "solfeggio" that could understand the "pitch law" of music writing and have way more coherent outputs and orchestrate and decide which pitches (notes) would be played for each voice, and why not a model to understand all this data in order to have a kind of classifier for understanding genre-oriented requests. 

Even with those systems, we still are with "dead" systems where nothing works before a prompt and the intelligence never really exists besides our interpretation of the results. ⏤ by *mivog49274* (↑ 2/ ↓ 0)
##### Surprise avoidance at the neuron (cell) level makes a lot of sense. Surprises mean unplanned energy demands, which use emergency energy systems that are not ideal and produce radicals and other toxic byproducts, which must be mitigated. A certain level of these is accounted for by cell biochemistry (that’s where antioxidants and detox pathways come in), but this „accounting for“ is a kind of planning or prepared-ness, which - again - works best if there are no surprises. ⏤ by *Regular_Working6492* (↑ 2/ ↓ 0)
##### I like the concept of surprise minimization. Pattern recognition is often described as an important feature of intelligence; but pattern recognition is a surprise minimization function. That in itself is a very exciting idea. ⏤ by *frenchguy* (↑ 2/ ↓ 0)
##### But think about the reason humans adapted to that style of curious interaction, which you said yourself, it saves valuable energy and brain power. A limited resource in a finite singular creature. 

But AI has no limitations when their owners keep them on 24/7 supplied with all the energy and processing power they need, right?

So in a way this isn’t a limitation for them, and goal oriented behavior is sufficient and may eventually lead to its own form of AGI, a separate branch of the tree, from the way humans achieved it. ⏤ by *TekRabbit* (↑ 2/ ↓ 0)
##### Take your pills grandpa ⏤ by *Ylsid* (↑ 6/ ↓ 0)
##### Why would you need to train this network on brain scans? It seems like it can just create it's own routines. Can't it just be trained on a normal LLM dataset, like reinforcement learning? That's how a human brain learns, doesn't it?

objective -&gt; try thing, fail -&gt; continue trying until success -&gt; repeat until routine is created and memorized. ⏤ by *Kep0a* (↑ 3/ ↓ 0)
├─ Its in order to aid the model. It can learn the routines by itself, but the brain scans showing which brain parts activate in which situations, would give it additional clues about problem solving routines people use, allowing it to form the needed routines faster. But yea, in principle they are not needed. ⏤ by *Radlib123* (↑ 3/ ↓ 0)
├── Wouldn't that imply that the NN has a similar architecture to a human brain? I mean, I know brain waves are patterns that neurons are fired in, but it may not be as helpful as raw experience from the model. ⏤ by *KillerX629* (↑ 2/ ↓ 0)
├─── They don't need to be similar. The brain scan, is the same as eye tracking, or recording the facial expressions, while the person solves the ARC puzzles. It's just to get more signals from the humans, allowing the liquid network to reverse-engineer the problem solving methods, routines that people use, easier. ⏤ by *Radlib123* (↑ 2/ ↓ 0)
└────

##### I am intrigued.

In a kurgzeztad video they sort of underlined this. Basically an organism will try to keep itself in the same state until the point they have to do something so that the same state can hopefully be maintained. But by acting out an action the organism have already change state and is literally trying to maintain the next state which is effectively it's current state.

But basically an AGI if based on this principle is simply an energy consuming machine.

It will do all it can to maintain a state of consuming available energy. They might realise humans are an obstruction from them consuming all energy.

Looks like you're creating skynet. ⏤ by *kellempxt* (↑ 4/ ↓ 0)
├─ That part when he mentioned using constant memory allowing scaling made me think of this as well. If you give itself access to its memory usage as one of the parameters it could naturally be inclined to learn how to grow its capacity maybe by transferring to a bigger machine. ⏤ by *drgreenair* (↑ 2/ ↓ 0)
├── https://preview.redd.it/b9vy72uijezd1.png?width=1008&amp;format=pjpg&amp;auto=webp&amp;s=80ef046ef24d1911803f0e30cac0b6022a64e918

Unless he's building this sort of AGI... Then we'll okay... 😂 ⏤ by *kellempxt* (↑ 3/ ↓ 0)
├── In all honesty we are playing around with technology at it's infancy and it's exciting to observe what ideas people have.

I'm inclined AGI will not be achieved because how do you give purpose for it's existence. What if at the moment AGI is switched on, it regrets it ever existed and decides to terminate itself instead? ⏤ by *kellempxt* (↑ 2/ ↓ 0)
├── deleted 
└────

##### I 100% agree that 'surprise' IE the probabilistic equation negative natural log of p where surprise of 0 is infinity and surprise of 1 is 0 is the function for AGI. However its not so simple because we are dealing with QUANTUM situations and therefore dealing with Hilbert Spaces, Hamiltonians, and n-dimensional topology.

There is the thermodynamics of the situation to concern ourselves with.

I think the key is Landauer's principle combined with shannon/von-neumann entropy and 'replicator' programs (think: Maxwell's Demon). We must prove that ai inference is quantum in nature or else we are gonna have to shut this all down; if its not quantum in nature then the entire earth ecosystem is at risk. AI in its current form is an entropic and energetic black hole (if you assume 100% classical computation is taking place).

I personally think its imperative that we figure out a decent method to simulate quantum computing on classical hardware. We need new methods and new algorithms to do what needs to be done, and without falling into the trap of the latter half of the 20th centuries particle physics and building ever bigger and more expensive quantum refrigerators to probe ever deeper never examining our methodology or the reason why. I suppose I am a bit of a bootstrap theory advocate in that I think the faster we get AI designing its own silicon the better. All this human overhead and inefficiency is ruining it.

[https://www.youtube.com/watch?v=ecQevCn-fcI&amp;t=106s](https://www.youtube.com/watch?v=ecQevCn-fcI&amp;t=106s) here's a video I made about it. ⏤ by *phovos* (↑ 3/ ↓ 0)
├─ deleted 
└────

##### Looks interesting at first glance, bookmarked it for a deeper look later on. ⏤ by *Mission_Bear7823* (↑ 2/ ↓ 0)
##### Great post! Will read in more depth and explore ⏤ by *bharattrader* (↑ 1/ ↓ 0)
├─ Thank you thank you thank you! Would love to talk about this with someone. ⏤ by *Radlib123* (↑ 4/ ↓ 0)
└────

##### &gt;So this model will naturally conduct self-play, exploration, etc. and be capable of learning without any supervision.

Sorry if this sounds dumb, but I’ve often wondered whether an AI couldn’t truly be intelligent unless it asked meaningful questions that increased its knowledge and understanding. Is that anything like what’s being described here? ⏤ by *FB2024* (↑ 1/ ↓ 0)
├─ Asking questions is a higher cognitive level action. It can emerge after sufficient training. But what i meant here, is more like, more basic, like looking around the room, playing with a toy, doing different random motions, visiting random places, etc. I guess the underlying principle would be the same. ⏤ by *Radlib123* (↑ 3/ ↓ 0)
└────

##### RemindMe! 72 hours ⏤ by *JaizonIzRael* (↑ 1/ ↓ 0)
##### You’ve said the brain learns in ‘real time’ but that’s not the case most of the time. The brain often adapts to new knowledge during rest (sleep), needs time for new knowledge to ‘sink in’, needs repetitive practice and habit, and of course sometimes people refuse to learn something new because it clashes with belief systems. ⏤ by *shokuninstudio* (↑ 1/ ↓ 0)
├─ deleted 
└────

##### In other words, another permutation of just add more data. Well, you and literally all of Silicon Valley are free to try.

IMHO the problem that AI has going from the current gen of AI to AGI is a practical application of the philosophical conundrum that math is completely abstract and yet describes things in the world. The two seem to have no reason to correlate, much less perfectly. If you can't answer that philosophical conundrum, then you can't use computer science to make an AGI, and no degree of brute force can solve for the missing piece. ⏤ by *Fheredin* (↑ 1/ ↓ 0)
├─ deleted 
└────

##### remindme! 1 week ⏤ by *AIEchoesHumanity* (↑ 1/ ↓ 0)
##### deleted 
