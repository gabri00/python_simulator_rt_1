# Research Track 1 - Assignment 1

## Description

In this simulation, we are given a mobile robot that is able to detect informations of the tokens in front of him with a certain angle. The robot is also able to grab/release a token and to move while holding a token. In this configuration we have 6 silver tokens and 6 gold tokens.
The aim of the assignment is to develop a Python script to make the robot grab a silver token and bring it next to a gold token, then repeat this process for every silver box.
The code for the assignment can be found in the file [assignment.py](robot-sim/assignment.py).

**Report of the assignment:** [report](report.pdf)

## Installing and running

The simulator requires a _Python 2.7_ installation, the [pygame](http://pygame.org/) library, [PyPyBox2D](https://pypi.python.org/pypi/pypybox2d/2.1-r331), and [PyYAML](https://pypi.python.org/pypi/PyYAML/).
All the libraries should be easy to install using `pip`.

Once the dependencies are installed, you can run:
`python2 run.py assignment.py`

To run the statistical analysis open the [statistics notebook](robot-sim/statistics.ipynb) in *Jupyter Notebook* or in *Jupyter Lab* and run all cells.
The data used for the analysis are in a *csv* table: [results](robot-sim/results.csv).

## Robot API

The API for controlling a simulated robot is designed to be as similar as possible to the [SR API](https://studentrobotics.org/docs/programming/sr/).
Further instructions on the robot API ca be found in the [README](robot-sim/README.md) inside the [robot-sim](robot-sim/) folder.

## Code description

![Flowchart](robot-sim/images/flowchart.png "flowchart of the code")

#### Functions description

- Find token:
  ```python
  def find_token(token_type, visited_tokens)
  ```
  Scans all tokens of type _token_type_ in view and gathers informations on the closest token. Ignores all tokens in the _visited_tokens_ list. It return the distance, the rotation angle and the code of the token with respect to the robot.
  <br>

- Update position:
  ```python
  def update_pos(target_code)
  ```
  Returns the distance and the angle relative to the token of code _target_code_.
  <br>

- Bring a (silver) token to a checkpoint (gold token):
  ```python
  def bring_to_checkpoint(token_code)
  ```
  Delivers the silver token with code _token_code_ the the closest gold token in view.
  <br>

- Collect silver tokens:
  ```python
  def collect_silver_tokens(n_tokens)
  ```
  Search and deliver all _n_tokens_ silver tokens.

## Possible improvements
- Make the robot's actions smoother and faster;
- Optimize the robot's search path of the tokens;
- Show robot's view cone and detections lines.
