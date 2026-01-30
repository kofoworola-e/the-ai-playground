# Lesson 1: Introduction to Artificial Intelligence

## 1. What is AI?
Traditionally, computers follow algorithms—well-defined sequences of steps to achieve a goal (a concept dating back to Charles Babbage).
* **The Difference:** AI focuses on tasks we *cannot* explicitly program because we don't know the exact rules (e.g., determining a person's age from a photograph). We know *how* to do it subconsciously, but we can't write the code for it step-by-step.

## 2. Weak vs. Strong AI
There is a distinct separation between current technology and theoretical goals.

| Feature | Weak AI (Narrow AI) | Strong AI (AGI) |
| :--- | :--- | :--- |
| **Definition** | Systems trained for a specific, narrow task. | Systems with human-level intelligence and consciousness. |
| **Capabilities** | Excel at one thing (e.g., Chess, Recommendations) but lack understanding. | Can perform *any* intellectual task a human can do. |
| **Status** | Exists today (Siri, Netflix algorithms). | Theoretical; a long-term goal. |

## 3. Defining Intelligence & The Turing Test
"Intelligence" is hard to define. Is a cat intelligent? Is a maze-solving crow intelligent? Because we lack a universal definition, we use comparison.

**The Turing Test:**
Proposed by Alan Turing, this test posits that if a human interrogator cannot distinguish between a machine and a human in a text-based conversation, the machine is considered intelligent.


* **Critique:** Passing the test doesn't prove "thinking." The chatbot **Eugene Goostman** (2014) "passed" by pretending to be a 13-year-old boy to mask its lack of knowledge. It fooled the humans, but it didn't actually *think*.

## 4. Approaches to AI
To create intelligence, we generally use two opposing strategies:

### A. Top-Down (Symbolic Reasoning)
* **Model:** Mimics the conscious reasoning process.
* **Method:** Extracts rules and knowledge from human experts and codes them into the computer.
* **Example:** A doctor diagnosing a fever based on a checklist of symptoms.
* **Limitation:** It is brittle. It fails when rules are unknown or too complex (e.g., facial recognition).

### B. Bottom-Up (Neural Networks)
* **Model:** Mimics the physical structure of the brain (neurons).
* **Method:** Uses a network of simple units ("artificial neurons") that learn from data rather than following rules.
* **Example:** A baby learning to identify objects by seeing many examples.


## 5. A Brief History & Evolution
* **Early Era (1950s-70s):** Dominated by Symbolic AI (Top-Down). Successes included "Expert Systems."
* **The AI Winter (1970s):** Progress stalled because maintaining huge rule-based systems was too expensive and they didn't scale.
* **The Neural Boom (2010s - Present):** Compute became cheap and Data became abundant. Neural Networks (Bottom-Up) began outperforming humans.

### Evolution of Game AI
* **Past (Chess):** Used **Search Algorithms** (Alpha-Beta Pruning). The PC calculated all possible future moves.
* **Present:** Uses **Reinforcement Learning**. The AI plays against itself millions of times to learn strategies from scratch (e.g., AlphaZero).

## 6. Recent Milestones
Since the introduction of **ImageNet** (14M+ images) and **CNNs** (Convolutional Neural Networks) in 2012, AI has rapidly achieved "Human Parity" in specific tasks:

* **2015:** Image Classification (ResNet)
* **2016:** Conversational Speech Recognition
* **2018:** Automatic Translation (Chinese-to-English)
* **2020:** Image Captioning

*Current focus is on Large Language Models (LLMs) like GPT, which are trained on vast amounts of general text to "understand" structure and meaning.*
