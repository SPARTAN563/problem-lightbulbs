# Lightbulbs Problem
Given a circuit as shown below, assume that all switches are initially open. Consequently, all lights are currently not illuminated.
Closing `sw0` will cause `light0` to become illuminated. However without both `sw0` and `sw1`, closing `sw2` will not cause `light2` to become illuminated.

```
              sw0              sw1             sw2
   ___________/ _______________/ ______________/ __________ →
  /               |               |               |
  |               |               |               |
  |               |               |               |
 /+\             / \             / \             / \
|   | battery   | x | light0    | x | light1    | x | light2
 \-/             \ /             \ /             \ /
  |               |               |               |
  |               |               |               |
  \_______________|_______________|_______________|________ →
```

Therefore, the state of each of these lights is described by the following table:

| Light  | Switches        |
|--------|-----------------|
| light0 | sw0             |
| light1 | sw0 & sw1       |
| light2 | sw0 & sw1 & sw2 |

Given a sequence of switch activations in the form of a list of switch numbers (e.g. `[0, 2, 1]` meaning first `sw0`, then `sw2` and finally `sw1`), determine the number of switch activations which result in one or more lights illuminating.

In the case of `[0, 2, 1]`, we can answer this as follows:

1. :heavy_check_mark: `sw0` results in `light0` illuminating.
2. :x: `sw2` results in no new lights illuminating (because `sw1` is still open).
3. :heavy_check_mark:`sw1` results in `light1` and `light2` illuminating (because `sw2` is already closed).

Following this logic, for `[0, 2, 1]` we have a total of two (2) switch activations which result in lights illuminating.

Develop an algorithm which, given an arbitrary array of integers representing switch activations, can determine the number of activations which result in lights illuminating.

## Solving this Problem
To run the tests, simply run `python -m pytest` from this directory. If you do not have `pytest` installed, you can install it with `pip install -U pytest`.

Implement your solution in the `solution.py` file.
