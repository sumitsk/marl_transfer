# Learning Transferable Cooperative Behavior in Multi-Agent Teams

This is the official repository of the 'Learning Transferable Cooperative Behavior in Multi-Agent Teams' paper available at https://arxiv.org/abs/1906.01202. 

## Dependencies
- [Pytorch >=1.0](https://pytorch.org/get-started/locally/)
- MultiAgentParticleEnv (included in this repo)
- [gym_vecenv](https://github.com/agakshat/gym_vecenv)
- [tensorboardX](https://github.com/lanpa/tensorboardX)

## Installation
- Setup MAPE environment by running `pip install -e .` command inside the `mape` subdirectory.
- Setup gym_vecenv by executing `pip install gym_vecenv`.

## Examples
See `arguments.py` file to see various command line arguments one can set while running scripts. 

### Normal Training
Training on a coverage control (`simple_spread`) environment can be started by running:

`python main.py --env-name simple_spread --num-agents 3 --entity-mp --save-dir 0`

Similarly scripts for formation control (`simple_formation`) and line control (`simple_line`) can be launched. 

### Curriculum training
To start curriculum training, specify the number of agents in `automate.py` file and execute the script:

`python automate.py --env-name simple_spread --entity-mp --save-dir 0`

## Results
The models trained via curriculum learning on the three environments can be found in `models` subdirectory.

The corresponding results obtained from the trained policies are located in `videos` subdirectory.

You can also continue training on a saved model. For example, for training a team of 5 agents in `simple_spread` task from a policy trained with 3 agents, execute:

`python main.py --env-name simple_spread --entity-mp --continue-training --load-dir models/ss/na3_uc.pt --num-agents 5`


## Contact
For any queries, feel free to raise an issue or contact the authors at sumit.sks4@gmail.com or agarwalaks30@gmail.com.

## License
This project is licensed under the MIT License.