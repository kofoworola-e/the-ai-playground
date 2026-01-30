# The Evolution of Artificial Intelligence in Pac-Man

In 1980, Namco released *Pac-Man*, a game that captivated the world not just with its gameplay but also with its unique enemies. To the casual player, the four ghosts—Blinky, Pinky, Inky, and Clyde—seemed to possess distinct personalities, collaborating to corner the player with eerie precision. However, this perceived intelligence was a masterful illusion created by simple hardware constraints and deterministic logic.

Over the last four decades, *Pac-Man* has transformed from a commercial arcade product into a critical benchmark for computer science. This essay will explore how *Pac-Man* illustrates the evolution of artificial intelligence: moving from the rigid **Finite State Machines** of the 8-bit era to the adaptive **Reinforcement Learning** agents of the present, and finally, to the **Generative Models** that will define the future of game design.

## The Past: Geometric Rules

*Pac-Man*’s original complexity arose from simple geometric rules, not actual intelligence. The ghosts don’t “think”; they simply have different target coordinates they are trying to reach.

### The Core Mechanic: Target Tiles

The game board is a grid of tiles. At any given moment, every ghost has a specific **“Target Tile”** on the grid. The ghost’s AI is extremely simple: at every intersection, it calculates the straight-line distance (Euclidean distance) from its neighbour tiles to the Target Tile and chooses the shortest one.

### The Personality Math

**1. Blinky (The Red Ghost) – “The Chaser”**

* **The Algorithm:** Blinky is the only ghost that directly targets Pac-Man.
* **The Logic:** `Target = Pac-Man's Current Tile`
* **Resulting Behaviour:** He follows you relentlessly. As the level progresses, he speeds up (becoming “Cruise Elroy”), giving the player the feeling of being hunted by an aggressive predator.

**2. Pinky (The Pink Ghost) – “The Ambusher”**

* **The Algorithm:** Pinky targets a specific offset relative to the player.
* **The Logic:** `Target = 4 Tiles in front of Pac-Man` (based on Pac-Man’s current direction).
* **Resulting Behaviour:** This creates the illusion of an “ambush”. While Blinky chases you from behind, Pinky tries to get ahead of you to cut you off. If you are sandwiched between them, it feels like they are collaborating, but they are actually just following two different math functions.

**3. Inky (The Cyan Ghost) – “The Flanker”**

* **The Algorithm:** Inky is the most complex because his target depends on two moving objects: Pac-Man and Blinky.
* **The Logic:**
1. Find the tile 2 spaces in front of Pac-Man.
2. Draw a vector from Blinky’s current position to that tile.
3. Double the length of that vector to find the final target.


* **Resulting Behaviour:** Because his target is based on Blinky’s position, Inky is unpredictable. Sometimes he chases, sometimes he cuts you off. This unpredictability mimics “human” intuition or erratic behaviour.

**4. Clyde (The Orange Ghost) – “The Feigned Ignorance”**

* **The Algorithm:** Clyde switches behaviour based on his distance from you.
* **The Logic:**
* `If distance > 8 tiles`: Target Pac-Man (Chase behaviour)
* `If distance < 8 tiles`: Target Bottom-Left Corner (Retreat behaviour)


* **Resulting Behaviour:** Clyde looks like he is chasing you, but the moment he gets close, he “gets scared” and runs away to his corner. This prevents the game from being impossible (if all 4 chased you, you would die instantly) and adds a unique “personality” of cowardice.

## The Pac-Man FSM (Finite State Machine)

Unlike modern Reinforcement Learning agents which learn optimal policies through trial and error, the *Pac-Man* ghosts were governed by rigid **Finite State Machines**. They could not adapt or learn; they could only transition between pre-written scripts based on simple timers.

**1. State 1: Chase (The Aggressive State)**

* **Action:** The ghost calculates the path to its specific target tile (e.g., Blinky targets Pac-Man’s position).
* **Transition:** After 20 seconds, the game timer forces a switch to Scatter.

**2. State 2: Scatter (The Passive State)**

* **Action:** The ghost stops chasing you and targets a fixed corner of the maze (e.g., Blinky targets the top-right corner).
* **Transition:** After 7 seconds, the timer forces a switch back to Chase.

**3. State 3: Frightened (The Random State)**

* **Trigger:** Pac-Man eats a Power Pellet.
* **Action:** The ghost turns blue, moves at half-speed, and chooses random turns at intersections (pseudo-random number generation).
* **Transition:** Timer expires then return to the previous state.

## The Present: From Rules to Rewards (Reinforcement Learning)

While the 1980s focused on programming the enemies using strict rules, modern computer science uses *Pac-Man* to train the player using Machine Learning. Specifically, researchers use the game to test **Reinforcement Learning (RL)**, a method where AI learns by trial and error rather than being told the rules.

### The Challenge: Ms. Pac-Man vs. Pac-Man

Modern research often prefers *Ms. Pac-Man* over the original. Why? Because the original *Pac-Man* is deterministic; players can memorise a perfect path. *Ms. Pac-Man*, however, includes stochastic (random) ghost movement. Memorisation is impossible. The AI must actually “think” and react in real-time.

### Case Study: Microsoft Maluuba (Hybrid Reward Architecture)

In 2017, Microsoft’s Maluuba team achieved a superhuman score of 999,990 on *Ms. Pac-Man*. They didn’t use a single “Target Tile” script. Instead, they used a “Divide and Conquer” approach:

* **The Problem:** A single neural network gets confused trying to eat pellets and avoid ghosts at the same time.
* **The Solution:** They broke the “brain” into 150+ tiny agents.
* *Agent A* only wants to find a pellet.
* *Agent B* only wants to avoid Blinky.
* *Agent C* only wants to eat a ghost.


* **The Aggregator:** A top-level “Executive AI” takes votes from all 150 agents to decide the best move. This mirrors how modern complex ML systems work: breaking a massive problem into smaller, solvable vectors.

## The Future: AI as the Creator (Generative Models)

If the past was about scripted enemies, and the present is about learning players, the future is about AI becoming the Game Designer itself. We are entering the era of **Generative AI**, where the computer builds the game environment in real-time.

### Case Study: NVIDIA GameGAN

In 2020, NVIDIA released **GameGAN**, a neural network that recreated the entire *Pac-Man* engine without seeing a single line of code.

* **How it worked:** The AI simply “watched” 50,000 episodes of *Pac-Man* being played.
* **The Result:** It learned the physics, the rules, and the graphics purely from visual data. It can now generate a playable version of *Pac-Man* where the AI renders the next frame based on player input.
* **Why this matters:** This signals a shift toward “Procedural Generation on Steroids.” In the future, games won’t just have smarter enemies; the level layout, the difficulty, and even the graphics will be generated on the fly to match the player’s skill level (keeping them in a “Flow State”).

## Conclusion

*Pac-Man* is more than just a retro arcade token; it is a historical record of our progress in Artificial Intelligence. We started with Finite State Machines, where “intelligence” was just a distance calculation. We moved to Reinforcement Learning, where machines learned to master chaos through reward signals. Now, we are approaching Generative AI, where the machine understands the game well enough to rebuild it from scratch. While the ghosts may still look the same as they did in 1980, the mind driving them has evolved from a simple calculator into a creative neural network.

---

### References

1. Pittman, J. (2009). *[The Pac-Man Dossier](https://www.gamedeveloper.com/game-platforms/feature-the-i-pac-man-i-dossier#:~:text=seminal%20Pac%2DMan%3F-,From%20history%20through%20behavior%2C%20Gamasutra%20presents%20Jamey%20Pittman's,guide%20to%20the%20classic%20game.)*. Game Developer.
2. [Jamey Pittman’s *Pac-Man Grouping Tutorial](https://setsideb.com/jamey-pittmans-pac-man-grouping-tutorial/#:~:text=Jamey%20Pittman's%20Pac%2DMan%20Grouping,%2C%20the%20Pac%2DMan%20Dossier.)*.
3. Van Seijen, H., Fatemi, M., Romoff, J., Laroche, R., Barnes, T., & Tsang, J. (2017). *[Hybrid Reward Architecture for Reinforcement Learning](https://www.microsoft.com/en-us/research/publication/hybrid-reward-architecture-reinforcement-learning/)*. Microsoft Maluuba.
4. Kim, S. W., Zhou, Y., Philion, J., Torralba, A., & Fidler, S. (2020). *[Learning to Simulate Dynamic Environments with GameGAN](https://research.nvidia.com/labs/toronto-ai/GameGAN/#:~:text=Seung%20Wook%20Kim%2C%20Yuhao%20Zhou,%5D%20%5BBibtex%5D%20%5BVideo%5D)*. Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR).
5. Salian, I. (2020). *[40 Years on, PAC-MAN Recreated with AI by NVIDIA Researchers](https://blogs.nvidia.com/blog/gamegan-research-pacman-anniversary/#:~:text=With%20data%20from%20BANDAI%20NAMCO,AI%20agent%20playing%20the%20game.)*.
