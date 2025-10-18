---
{"publish":true,"created":"2025-10-18T20:56:31.298+05:45","modified":"2025-10-18T23:59:53.319+05:45","cssclasses":""}
---

This past two days, i have been listening to Dwarkesh podcast. Two phenomenal guests, Richard Sutton and Andrej Karpathy have taken over the internet as it seems. 
Richard is turing award winner and is father of RL. Andrej who has been working on LLM side before it was cool. Both the people have deep knowledge over what they are doing and i feel like their insights are supposed to be grounded as supposed to someone like [Tim Urban](https://waitbutwhy.com/2015/01/artificial-intelligence-revolution-1.html) or [Ray Kurtzweil](https://en.wikipedia.org/wiki/The_Singularity_Is_Nearer). I guess they aren't hyping as much as Sama or [Dario Amodei](https://www.darioamodei.com/post/the-urgency-of-interpretability) . Although the veil of fundraising would drape, there was genuine discussion around the internet because of these hypemen. 

### Bitter Lesson of Richard Sutton 

> We want AI agents that can discover like we can, not which contain what we have discovered. Building in discoveries only makes it harder to see how discovering process can be done. 

The point he makes on the podcast is quite unintuitive. Dwarkesh pokes around saying how a child in a learning environment starts out by imitation and then gets to understand the topic. But Sutton sees much more of a whole life itself clarifying, the zebra being able to walk and do zebra things as soon as it is born and kids not learning through imitation but through experience. 

One key idea i got from this back and forth is that, Richard is leaning more towards the Reinforcement Learning theory where a environment with a reward system for a goal is set and you tend to capitulate towards the goal with a provided reward. Goal is what makes the system work for you. But LLMs and modern tools don't even have a environment setup for them. The training portion where they ingest the entirety of internet with instant feedback. The real world doesn't work like that... The feedback system is delayed, the reward function is upto the learner and so much more. He even opposed RL on top of LLMs 

### Karpathy

The guy might be responsible for bursting the AI bubble. Because he just gave a 10 year timeline for AGI to arrive. He started by pointing out that RL is dumb. The key insight being that RL starts with multiple random initial position doing random things and then picks the choices with max intermediate reward. The reward function, for example if we are doing a flappy bird then would be the bird that survives the longest. There is no deliberation to it. Eventually it will find a nook that is optimal as a reward function but not practical or useable at all. [OpenAI plays Hide and Seek and breaks the game](https://www.youtube.com/watch?v=Lu56xVlZ40M) is one primary example. 
Another key point he made was LLMs are the ghost of the internet, similar to Sutton words. It is predicting the next best token. It doesn't have real time feedback mechanism system to update itself.  Low rank adaptors don't count because they are small subset of whole model.  

