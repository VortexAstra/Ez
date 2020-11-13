# Snake

[![][badge-travis]][build-travis] [![][badge-appveyor]][build-appveyor] ![][badge-python]

The project focuses on the artificial intelligence of the [Snake][wiki-snake] game. The snake's goal is to eat the food continuously and fill the map with its bodies as soon as possible.

Standard approaches to completing the snake game involve a Hamiltonian loop, which is not spectacular because the snake essentially moves along the same path. The ML approach allows you to randomize the snake's behavior, making it closer to the human one. This approach allows you to save data for further analysis and identify the best path for various algorithms.

**Performed by Artem Ustinov, Kazantsev Lev, Mashenko Bogdan, Petrov Artyom.**

## Issue
Finding the optimal solution - using machine learning on the example of a classic game (Snake).

## Requirement

### Functional
1. The system must be able to change the machine learning algorithm (Hamilton, Greedy and DQN);
2. The system should be able to change the speed of the game demonstration - snake;
3. The system must be able to stop the game to check the step statistics;
4. The system must be able to restart the game with new algorithm;
5. The system must be able to switch to manual control;
6. The system must select logs with full statistics for each system start.

### Non-functional
1. The system must be written in Python;
2. The user interface should be able to adapt to any screen;
3. Screen processing speed should be 60 fps;
4. Compliance with the geometric standards of the snake and its food, respectively.
5. Calm colors.

## Architecture development
### Level Context/Container diagram
![System Context/Container diagram](https://github.com/VortexAstra/software-engineering/blob/master/lvl.png)


## Coding and Debugging
A python program was implemented and tested in the Pycharm development environment using some libraries:
1. pytest
2. numpy
3. matplotlib
4. tensorflow

## Experiments

We use two metrics to evaluate the performance of an AI:

1. **Average Length:** Average length the snake has grown to (*max:* 64).
2. **Average Steps:** Average steps the snake has moved.

Test results (averaged over 1000 episodes):

| Solver | Demo (optimal) | Average Length | Average Steps |
| :----: | :------------: | :------------: | :-----------: |
|[Hamilton][doc-hamilton]|![][demo-hamilton]|63.93|717.83|
|[Greedy][doc-greedy]|![][demo-greedy]|60.15|904.56|
|[DQN][doc-dqn]<br>(experimental)|![][demo-dqn]|24.44|131.69|

## Installation

Requirements: Python 3.5+ (64-bit) with [Tkinter][doc-tkinter] installed.

```
$ pip3 install -r requirements.txt

# Use -h for more details
$ python3 run.py [-h]
```

Run unit tests:

```
$ python3 -m pytest -v
```



## Utils

***[Algorithms >][doc-algorithms]***






[snake-proj-old]: https://github.com/chuyangliu/Snake/tree/7227f5e0f3185b07e9e3de1ac5c19a17b9de3e3c

[build-travis]: https://travis-ci.org/chuyangliu/snake
[build-appveyor]: https://ci.appveyor.com/project/chuyangliu/snake/branch/master

[badge-travis]: https://travis-ci.org/chuyangliu/snake.svg?branch=master
[badge-appveyor]: https://ci.appveyor.com/api/projects/status/ew63pr1vb7ee1yyi/branch/master?svg=true
[badge-python]: https://img.shields.io/badge/python-3.5+-blue.svg

[wiki-snake]: https://en.wikipedia.org/wiki/Snake_(video_game)
[doc-tkinter]: https://docs.python.org/3.6/library/tkinter.html
[doc-algorithms]: ./docs/algorithms.md
[doc-greedy]: ./docs/algorithms.md#greedy-solver
[doc-hamilton]: ./docs/algorithms.md#hamilton-solver
[doc-dqn]: ./docs/algorithms.md#dqn-solver

[demo-hamilton]: ./docs/images/solver_hamilton.gif
[demo-greedy]: ./docs/images/solver_greedy.gif
[demo-dqn]: ./docs/images/solver_dqn.gif
