# How-to-python-argparse
This is a simple repo that holds an example that I came up with from working with python over time. It outlines how to take in arguments from CLI, and store them in an efficient way.

# Handling Arg/Param(s) 
### EXAMPLE CODE
#### This is an example of taking in arguments some times called parameters for a python script.   

<details>
<summary>CLICK TO SEE EXAMPLE CODE</summary>

```python
"""
This is an example of a script that outlines handeling arguments outside of a python environment.
"""

# Imports go outside the functions scope.
import argparse
import pandas as pd
import numpy as np
import ... as ... #add more


class Parameters:
    """This holds all of our parameter defaults"""

    def __init__(self):
        """Define class attributes for our anlysis function(s)"""
        self.processName_0 = "changePoint_process"
        self.sparkMaster_0 = "spark://spark-master:7077"
        self.dataFile_0 = 'hdfs://namenode:9000/data/turbofan/train_pred_lkb_edited.csv'
        self.dataFile_out_0 = "hdfs://namenode:9000/data/turbofan/changePoint_result"
        self. ... = "..." #add more


def main(parameters):
    """This is the main processing routine for the script.

    :param parameters: The parameters object
    """

    # Do stuff


if __name__ == "__main__":
    # Set up command-line argument parser
    parser = argparse.ArgumentParser()
    parser.add_argument("-a", "--a-parameter", help="Parameter 0", required= False) # required will most likely stay false if the script can be run devoid of input.
    parser.add_argument("-b", "--b-parameter", help="Parameter 1", default=None, required= False) # defaults can me set if needed
    parser.add_argument("-c", "--c-parameter", help="Parameter 2", type= int, required=False) # the parameter can require a type if needed
    args = parser.parse_args()

    parameters = Parameters()

    if args.a-parameter:
        parameters.processName_0 = args.a-parameter
    if args.b-parameter:
        parameters.sparkMaster_0 = args.b-parameter
    if args.c-parameter:
        parameters.dataFile_0 = args.c-parameter
```

</details>

---

### EXAMPLE COMMAND
#### By adding the `ArgumentParser()` & the `Parameters` class object, the scripts defaults can be used from an import or a call from a python environment, or called from a shell CLI with the option to override the defaults of the `Parameters` object. 
   
<details>
<summary>CLICK TO SEE A CLI CMD EXAMPLE</summary>

```sh
$ python script.py -a "new parameter" -b "new parameter" -c "new parameter"
```

</details>

