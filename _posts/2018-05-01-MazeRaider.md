---
title: MazeRaider
githubLink: https://github.com/Aandree5/MazeRaider
categories: ["C++", "GitHub"]
organization: "Coventry Univeristy"
---

A text base ASCII maze game, the objective is to find the way out, pick up all the chests to get more points and defeat the monsters without being killed.


{% include title.html title="Database" %}
This game connects to a MySQL database to retrieve and save the player data and score, also retrieves the information about the possible monsters to spawn. There's also items that are fetched from the database, they appear in chests spread throughout the maze.


{% include title.html title="Mechanics" %}
The objective is to reach the exit with the maximum number of points possible, the score decreases with time but can be increased with chests and by defeating monsters. The maze is generated randomly and the same for the monsters and chests, with items or not.
The player can also have several characters with different stats and visual representation.


{% include title.html title="Features" %}
The battles with the monsters is the same style as a Pokémon battle, with animations for the attacks or defences and colors.

Also the game is prepared to run on a windows or linux system.

Used a A* pathfinding algorithm to find the best path for the enemies to move towards the player.
