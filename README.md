# Noir Game Engine

**Noir** is a Python game engine designed for beginners to easily create text-based adventure games. It simplifies game development by removing the need for extensive conditional logic, making it quick and straightforward to create interactive stories.

## Installation

To install **Noir**, simply use pip:

```bash
pip install noir-game-engine
```

## Getting Started

Here's how to create a simple game using **Noir**.

1. **Import** the `NoirEngine` and `Node` classes.
2. **Define** your story nodes with prompts and options.
3. **Add** each node to the engine.
4. **Set** the starting node.
5. **Run** the game!

### Example

```python
from noir import NoirEngine, Node

# Define nodes with prompts and options
node1 = Node("You are in a dark room. What do you do?", [
    {'text': "Turn on the light", 'outcome': 'node2'},
    {'text': "Walk forward", 'outcome': 'node3'}
])

node2 = Node("The light reveals a monster! What do you do?", [
    {'text': "Fight", 'outcome': None},
    {'text': "Run away", 'outcome': 'node1'}
])

node3 = Node("You stumble in the darkness. What do you do?", [
    {'text': "Stay still and listen", 'outcome': 'node1'},
    {'text': "Run", 'outcome': None}
])

# Initialize the engine, add nodes, and set the start
engine = NoirEngine()
engine.add_node('node1', node1)
engine.add_node('node2', node2)
engine.add_node('node3', node3)
engine.set_start('node1')

# Start the game
engine.run()
```

## License

This project is licensed under the MIT License.