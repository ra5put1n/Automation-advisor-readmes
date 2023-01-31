### What is Rebot in Robot Framework?

XML output files generated during the execution of tests can be post-processed using Rebot, a tool that is an integral part of Robot Framework. It is automatically used when test reports and logs are generated during the test execution, and using it separately allows creating custom reports and logs as well as combining and merging results.

### How to run rebot?

You can use the command line to execute Rebot. Alternatively, you can use the Python interpreter to run the robot/rebot.py file or the installed robot module.

```python
rebot [options] outputs
python -m robot.rebot [options] outputs
python path/to/robot/rebot.py [options] outputs
```