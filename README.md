[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/7qg5CCgx)
# HW2
## Devlog
In my MG2 break-down plan, I designed a game process: the player (a penguin) stands on the ground, jumps up to catch gold coins, and earns one point for each coin caught. This process was transformed into specific GameObjects and scripts in my Unity project.

First of all, I plan to enable physical collisions between the player and the ground. In the code, this becomes the Player GameObject and the Ground GameObject, both of which have Collider2D and Rigidbody2D. In the OnCollisionEnter2D() method of Player.cs, I check whether the player has touched the ground to determine if they can jump.

I also plan to make the player and the gold coins have a "non-physical" collision, that is, a trigger. In the code, this part becomes a Coin GameObject, which has a Collider2D but no Rigidbody, and the IsTrigger option is checked. In the OnTriggerEnter2D() method of Player.cs, I check if the player has collided with a gold coin. If so, I increment the score and destroy the gold coin.

Gold coins are continuously generated through the CoinSpawner GameObject. In the Update() method of CoinSpawner.cs, I use Random.Range() to control the generation time, making the appearance of gold coins irregular. Each generated gold coin is instantiated from the Coin prefab.

Finally, I plan to display the score in the upper left corner of the screen. This part has been transformed into the ScoreUI.cs script in the code, which updates the ScoreText GameObject in the Canvas. Every time the player collects a gold coin, Player.cs will call scoreUI.UpdateScore(score) to update the displayed score.


## Open-Source Assets
If you added any other outside assets, list them here!
- [Sprout Lands sprite asset pack](https://cupnooble.itch.io/sprout-lands-asset-pack) - rabbit and item sprites
- [Pixel Penguin 32x32 Asset pack](https://legends-games.itch.io/pixel-penguin-32x32-asset-pack) - penguin sprites
- [Coins 2D](https://artist2d3d.itch.io/2d) - coin sprites
