# emoji-progress-bar

Animated clock-emoji busy spinner for Slack messages.

`SlackBusySpinner` is an iterator that yields Slack clock-emoji names
(`clock1`, `clock130`, `clock2`, ... `clock1230`) in a loop. Update a Slack
message's emoji with each value to render a spinning clock while a long task
runs.

## Install

```bash
pip install emoji-progress-bar
```

## Usage

```python
from emoji_progress_bar import SlackBusySpinner

# Endless spinner: yields clock1, clock130, clock2, ... and loops.
for emoji in SlackBusySpinner():
    # e.g. update your Slack message with f":{emoji}:"
    ...

# Bounded spinner: StopIteration once the internal index passes `timeout`.
spinner = SlackBusySpinner(timeout=48)
emojis = list(spinner)
```
