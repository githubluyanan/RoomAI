# RoomAI

RoomAI is a toolkit for developing and comparing imperfect information game bots

# Contents

## 1. Quick Guidance


### 1.1 Installation

you can install roomai with pip

<pre>
pip install roomai
</pre>


### 1.2 Developing an AI-bot and Testing It with Enviroments

<pre>
#!/bin/python
from roomai.kuhn import *;
import random
class KuhnPokerExamplePlayer(roomai.abstract.AbstractPlayer):
    def __init__(self):
        self.available_actions  = None

    #@override
    def receiveInfo(self, info):
        if info.available_actions is not None:
            self.available_actions = info.available_actions

    #@override
    def takeAction(self):
        idx = int(random.random() * len(self.available_actions))
        return self.available_actions[idx]

    #@overide
    def reset(self):
        pass


if __name__ == "__main__":
        players = [KuhnPokerExamplePlayer() for i in xrange(2)]
        env     = KuhnPokerEnv()
        scores  = KuhnPokerEnv.round(env, players)

        print scores
</pre>

## 2  [Detailed Guidance](https://github.com/roomai/RoomAI/blob/master/docs/Basic/README.md)

## 3. Info and Action Structure

### 3.1 [Info and Action Structure for KuhnPoker ]

### 3.2 [Info and Action Structure for DouDiZhuPoker]

### 3.3 [Info and Action Structure for Texas]

# License

# Contributors

If you would like to contribute to the project, please send me (lili1987mail at gmail.com) an email. We are always happy for more help.
