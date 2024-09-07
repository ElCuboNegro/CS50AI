# CS50AI - L0 - Search
Search is the way an agent reaches a expected state from a initial state.
oh, well, did you expected more than that as a definition? then let's go for that.

First we should know what the heck is an agent, then what is a state... 
and finally, what is a problem. yep, we will go deep into the rabbit hole

## What the fuck is an Agent?
Well, an agent is a piece of software that is aware of it's context, so it's capable
of taking decisions about how to interact with it's environment and has a desired state (which it tries to reach).

![image](https://github.com/user-attachments/assets/a59997d0-0352-4eb8-969a-486737fa8d43)

### What the fuck an agent can do?
It's a brief list.
- Analyze data: AI agents can collect data and use it to perform tasks.
- Make decisions: AI agents can use data to make decisions and choose actions to achieve goals. 
- Learn: AI agents can learn from their experiences and interactions, improving their performance over time. 
- Perform tasks: AI agents can perform a wide range of tasks, including answering questions, resolving issues, and automating processes. 
- Interact with the environment: AI agents can interact with their environment.
  
Then, more or less, an Intelligent agent is something that behave in this particular way:

![image](https://github.com/user-attachments/assets/119b7525-dbf7-4348-90d0-74f931833e34)

---

## What the fuck is a state?
A state is a configuration of an agent in (or and?) its environment. For example, in a 15 puzzle, a state is any one way that all the numbers are arranged on the board. 

It is essentially the set of conditions or values that define the system’s or agent's current configuration and status.


### And what is a configuration? 
well, let's say it's the way the things are (the number of things, the positions of all the things inside the group and all the properties of the objects inside the group) in a particular moment. 

A configurtion can include:

- Internal attributes: The agent's memory, data, or variables that define its current situation.
- External environment conditions: Information about the environment in which the agent operates (e.g., sensor readings, external events).
- Agent's position or situation: Where the agent is in relation to its task or goal (e.g., location in a map, current progress in a process).


### Initial State
The **initial state** is the starting point of the search process. For example, in a navigator app, it’s the current location, and in a maze, it’s the starting position. You begin from this state and execute an action, which modifies the system's configuration, transitioning you to a new state.

---

## Actions
An **action** is a choice that can be made in a particular state. Formally, an action can be described as a function:

`Actions(s) -> {a1, a2, ..., an}`

Where:
- **s** is the current state.
- **Actions(s)** is a function that returns the set of all possible actions `{a1, a2, ..., an}` that can be performed in state **s**.
- Each **a(i)** represents a valid action in that state.

#### Example:
In a 15-puzzle, given a state `s`, the **Actions(s)** function will return all possible moves (e.g., sliding a tile up, down, left, or right) based on the position of the empty square.

```
  Actions(s) = {
    s = empty square position.
    if the empty square is in the middle: {<4 actions>: a1, a2, a3, a4},
    if the empty square is on the side: {<3 actions>: a1, a2, a3},
    if the empty square is in the corner: {<2 actions>: a1, a2}, 
}
```

### Transition Model

A **transition model** describes what state results from performing any applicable action in a given state. More precisely, the transition model can be defined as a function:

`Results(s, a) -> s'`

Where:
- **s** is the current state.
- **a** is the action performed in state **s**.
- **Results(s, a)** is a function that returns the new state **s'** after performing action **a** in state **s**.

#### Example:
In a 15-puzzle, given a certain configuration of the puzzle (state `s`), moving a square in any direction (action `a`) will result in a new configuration of the puzzle (the new state `s'`).

---


