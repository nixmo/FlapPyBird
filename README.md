FlapPyBird
===============

This fork is modified to be usable in laboratory experiments with human subjects.

Modifications:
- The game runs in fullscreen mode (centered, with black bars on all four sides)
- Ingame events will be logged to a text file (by default `flappy.log`) with time stamps
- To homogenize input, only <kbd>&uarr;</kbd> is accepted as input (<kbd>Space</kbd> was removed)
- Added command line arguments `cancelable`, `timelimit`, `timeminimum`, `log_fpath`

   If the `--cancelable` argument is passed, <kbd>Esc</kbd> can be used to quit the game. This was default behavior in the original and has been moved to an optional command line argument in this fork to prevent subjects from accidentially aborting the experiment.
   
   If a number is passed through the `--timelimit` argument, the game will automatically terminate after that amount of seconds. If `timelimit` is not set, the game will be `cancelable` by pressing <kbd>Esc</kbd> (otherwise there would be no way to quit the game)
   
   If a number is passed through the `--timeminimum` argument, the player will be able to prematurely quit the game after that amount of seconds by pressing <kbd>Esc</kbd>. A message will appear onscreen informing the player of that fact. This message is currently hardcoded in german. This functionality is implemented for experiments in which concepts such as *giving up*, *rage-quitting*, *disengagement* or similar are of interest.
   
   `--log_fpath` can be used to pass a path to a log file that should be used instead of the default `flappy.log`. Python will attempt to open this in `a+` mode.

For example, to run this fork with a timelimit of 5 minutes, use:

```bash
$ pipenv run python flappy.py --timelimit 300
```
