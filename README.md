# VIVES City Game

A city game is an interactive game being played between different teams. These teams have certain objectives that need to be accomplished inside the boundaries of a certain city. So you can actually imagine a city game as a live-action game.

### _**What is it all about?**_

Imagine yourself and your team being dropped in a less familiar environment, for instance a lesser known city, having to compete in a city game against other teams. The team-members of each competing team could be or could not be familiar with the orientation, structure, topology ... of this particular city.

Each team will be equipped with a _gaming box_, including the necessary electronics to communicate with a central dispatching center, supervised by a game master. This game master can - in real-time - monitor the status of the competing teams, define new assignments, reward or sanction specific teams, according to their performance and results.

One of the main objectives of this project is offering your engineering team the opportunity to develop a framework in hardware and software, that will enable game developers to design new excitatory, attractive games.

An example of a simple game could be described as follows.

Two competing teams receive, via  the display of their gaming box, the coordinates to two different starting points in the given city. The starting points are determined by the game master and consist of the GPS coordinates of that particular location. This starting point could be defined as **location marker A**. Image that the teams are assigned with the challenge to travel a trajectory, containing several location markers, checkpoints as it were, \(location marker B, location marker C, ...\), within a dedicated short time interval.

When a team reaches a certain marker location, it is mandatory to 'proof' that they have indeed reached the correct location, and this within a defined time interval. They could for example take some photos of the environment and upload the images to a webserver, from which they can be evaluated by the game master. The teams also have the ability to save and capture crucial data \(text, images, ...\) in the gaming box. Each marker location can be accompanied with a specific task or set of tasks, defined by the game master. The updates of the game instructions could for instance be established by the communication between game master and gaming teams. Alternatively the configuration could be uploaded, as a configuration file, in the embedded system of the gaming box before the start of the game.

The winning team will be the team that is able to perform as much tasks as possible assigned at the different location markers, within the predefined time interval.

Let's take the city of Ostend as an example. The challenge for **team A** could be:

1. start at 8:45 AM at  '**Fort Napoleon** Oostende' - solve some puzzles or issues, concerning Fort Napoleon and it's history within 15 minutes
2. go to the **railway station** of Ostend - the deadline is 9:45 AM - solve some puzzles or issues, within 30 minutes

3. go to '**Cultuurcentrum De Post**' - the deadline is 10:45 AM - solve some puzzles or issues, within 20 minutes

4. go to '**Kinepolis** Ostend' - the deadline is 11:30 AM - solve some puzzels or issues, within 10 minutes

5. return to the base camp at **Hogeschool VIVES** as fast as possible, to be evaluated by the game master and indeed to claim the victory of your team!

As an example, a number of location markers \(marker B and C\) are visualized in **the image below**.

Naturally, you should be able to compose other thrilling 'compete - go - track' games or variants of the above described city game.

![VIVES City Game in Ostend](/assets/Oostende_city_game_map.PNG)

Possible extensions to this concept could be real-time alterations by the game master. For example while a team is on its way to a certain marker, the game master could introduce an intermediate challenge that rewards the team extra points upon completion. The team could then decide if they would take the extra challenge on top of the current objective of getting to the next marker in time.

Alternatively to the extension mention before, the reward could also be a disadvantage for the other teams. For example subtracting points, or lower their current dead-line for the next marker, ...

