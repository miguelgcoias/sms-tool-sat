# Single machine scheduling tool
sms-tool-sat is a Python program that generates an optimal schedule for a set of tasks and their time and dependency constraints.

## Theoretical work
The tool is a direct implementation of the MaxSAT formulation of the single machine scheduling problem by X. Liao, H. Zhang, M. Koshimura, R. Huang and W. Yu in their paper [Maximum Satisfiability Formulation for Optimal Scheduling in Overloaded Real-Time Systems](https://doi.org/10.1007/978-3-030-29908-8_49).

## Input format
The problem instance should be formulated as follows:
- one line with the number *n* of tasks to be scheduled.
- a sequence of *n* lines, where each line lists the parameters of a task, namely the release time *r*, the processing time *p*, the deadline time *d*, the number of fragments *k*, and the processing times *p<sub>1</sub>*, ..., *p<sub>k</sub>* of the fragments 1 to *k*.
- another sequence of *n* lines, where each line lists the dependencies of a task. Each line consists of the number of dependencies followed by the indices of the tasks on which *i* depends.

## Output format
The tool will output an answer in the following format:
- one line with the number *s* of scheduled tasks;
- a sequence of *s* lines, where each line lists the starting times of the fragments, ordered by fragment index in ascending order and separated by spaces.

## Execution
The tool should be executed with the command
```
/path/to/proj1 < job.sms > solution.txt
```
where job.sms is a text file formatted as specified above, and solution.txt is a file where the solution will be written to.

## Dependencies
[PySAT](https://pypi.org/project/python-sat/) must be installed.
