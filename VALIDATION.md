# Local validation

Validated with Python 3.13.7 using the recovered final submission files and the original local course runtime.

```sh
PYTHONDONTWRITEBYTECODE=1 python3 autograder.py --no-graphics
```

The process exited with status 0. All question groups passed.

| Question | Earned | Regular maximum |
| --- | ---: | ---: |
| q1 | 5 | 5 |
| q2 | 1 | 1 |
| q3 | 6 | 6 |
| q4 (extra credit) | 1 | 0 |
| q5 | 5 | 5 |
| q6 | 2 | 2 |
| q7 | 1 | 1 |
| q8 | 1 | 1 |
| q9 | 4 | 4 |
| **Total reported** | **26** | **25** |

The q4 configuration uses `ExtraCreditPassAllTestsQuestion`, with a regular maximum of 0 and 1 extra-credit point. The result is therefore 25/25 regular points plus 1 extra-credit point.

The q8 harness ran PacmanQAgent with 2,000 training games and 100 evaluation games. Evaluation recorded 100 wins out of 100 games and an average score of 500.68 under the supplied fixed random seed.

All 28 Python files also passed syntax compilation. The original `grading.py` emitted one non-fatal `SyntaxWarning` for an invalid escape sequence in its ASCII art. No course source was changed to suppress it.

The checks ran without graphics or network submission. Bytecode writing was disabled, and no cache artifacts remained afterward. Local passing results do not establish a new official grade or behavior on unseen tests.
