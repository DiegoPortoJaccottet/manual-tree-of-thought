# Manual way of using Tree-of-Thought for better prompt performance with AIs/LLMs. 

## Idea

Tree-of-Thought (ToT) is said to enhance AI/LLM results by up to about 10x (According to: https://arxiv.org/abs/2305.10601). 

A similar repository to this one with comparison to the previous best method (Chain-of-Thought): https://github.com/dave1010/tree-of-thought-prompting 

Chain-of-Thought can also be achieved by providing Q/A examples to show the manner/kind of steps by which the LLM should find the result, as in: https://arxiv.org/pdf/2201.11903.pdf

This repository explores Tree-of-Thought prompting without using code to keep track of the nodes (asking the LLM to do this by itself).

In my experiments, sometimes I've achieved better results with Anthropic (Claude) rather than OpenAI. 

## Usage

### Step 1: Breadth

The first step is to prompt the LLM to do a task n amount of times:

    Try to do [task] n times.

An example:

    Try to explain the meaning of life 3 times.
    
The number n depends on the size of the search space. As in, searching for a new way to extract energy from the sun will require a greater n than asking for the meaning of life, because exploring any chosen way to extract energy from the sun is more likely to lead to a dead end that can't be improved further. 

https://github.com/dave1010/tree-of-thought-prompting attempts to enhance this method by asking the AI to take the role of multiple experts. One could also ask the LLM to list which experts would be most relevant to answer such question, and answering as each one of them.

### Step 2: Depth

The second step is to choose a branch(es) and explore it. This can be repeated for all previous attempts, or just for the best ones. Such as:

    Choose the best try and improve it 3 times. 
    
Or:

    Choose the best 2 tries and improve each 3 times. 

Like this, one is creating the tree. Repeat this prompt an arbitrary number of times. 

### Step 3: Evaluation/Backtracking

The third step is to backtrack, using the LLM to compare all results. 

    From all your first and improved tries, pick the best one. 
    
One can copy this result and paste it into a new chat to create a new tree, perhaps asking to check for flaws and to solve these flaws. 

[//]: # (If this work has benefited you or you wish to contribute to its advance, please consider donating.)
[//]: # (Add describe steps.)
[//]: # (Add reflection and self-criticism.)
[//]: # (Add divide and unite.)
[//]: # (Add stunts.)
