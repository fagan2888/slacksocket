# SlackSocket Client

To instantiate a `SlackSocket` class that will setup an RTM websocket:

```python
from slacksocket import SlackSocket
s = SlackSocket('<slack-token>')
```

**Params**:

* slacktoken (str): token to authenticate with slack
* translate (bool): yield events with human-readable user/channel names rather than id. default true

****

## get_event

Return event object in the order received or block until an event is received and return it.

**Params**:

* type (str): A slack event type to filter by. Default 'all' returns all slack events. See https://api.slack.com/events for a listing of valid event types.

**Returns** (obj): SlackEvent object

# SlackEvent

Event object received from SlackSocket

**Attributes**:

* type (str): The Slack API event type
* time (int): The UTC epoch time that the event was received by the client
* json (str): The full JSON of the event received. If slacksocket was instantiated with translate=True(default), user and channel IDs will be replaced with their human-readable versions rather than ID. 