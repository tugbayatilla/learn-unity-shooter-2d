# Unity-2DShooter

## Coursera Videos Steps

### Setup Project

- Missing

### Visual Presentation Of Player

- Create a new Scene in folder Scenes.
- Name the scene as 'Level1'.
- Open 'Level1' scene.
- Delete SampleScene from Scenes folder.
- INFO: Starting player creation.
- Expand folder structure, Assets -> Art -> Player -> Player Sprites.
- Drag&Drop 3 player sprites to Level1 scene.
- INFO: Unity will automatically create animation for us.
- Select Assets -> Art -> Animations -> Player folder.
- Set name as PlayerIdle.anim.
- Same the file.
- INFO: 2 assets has been created in Assets -> Art -> Animations -> Player folder. 'Player Sprites_0'(first sprite in sprites that we had dragged in) and PlayerIdle.
- Rename 'Player Sprites_0' to 'Player' in Assets.
- Rename also 'Player Sprites_0' to 'Player' in Level1 scene.
- INFO: when Player in Level1 Scene selected, you can see 'Sprite Renderer' component. This component shows that what and how sprite being displayed.
- Open the 'Animation' window from the top menu. Window -> Animation -> Animation.
- Dock the 'Animation' to screen, so you can see all the time.
- Run the game and zoom in 'Scene View' to check the spaceship lights are blinking, then stop the game.
- Select the 'Player' gameobject from the 'Hierarchy View'. [shortly Player]
- INFO: you can see the animation if you click the play button on the animation window that you have docked earlier.
- Open the 'Animator' window from the top menu. Window -> Animation -> Animator.
- Dock the 'Animator' to screen, so you can see all the time.
- Select (if not selected) the 'Player' gameobject from the 'Hierarchy View'. [shortly Player]
- INFO: Animator shows the 'State Diagram' of the last selected 'Animator'. In this case, 'Player' gameobject because it has 'Animator' component in it.
- INFO: 'Player Animator' component has been automatically created when we have drag&drop the sprites.
- INFO: inside the animator 'PlayerIdle State' selected, in 'Inspector', you can see 'Motion' property which shows the selected 'Animation', which is in our case 'PlayerIdle Animation'.

### Setup controls of the player

- Set (drag&drop) 'Controller script' Assets -> Scripts -> Player -> Controller.cs to the 'Player' gameobject.
- INFO: If you run the game, player does not respond to any key compination yet.
- INFO: you can see an error at toolbar in Unity. (NullReferenceException: object reference not set ...)
- INFO: you can get detail information from console. Window -> General -> Console.
- Drag&Drop 'InputManager' to the Level1 Scene. Assets -> Prefabs -> Input -> InputManager.
- INFO: now, keyboard is working and we are controlling the Player gameobject.
- INFO: 'InputManager' is collecting input information.

### Setup Player Health & Damage

- Set 'Health Script' to the 'Player'. Assets -> Scripts -> Health&Damage -> Health.
- INFO: TeamId means, which team the object belongs to, so it might NOT take damage from the same team. Do not change this, keep it as 0.
- Change 'Use Lives' property as true (checked).
- Set 'Death Effect' with 'PlayerDeathEffect' from Assets -> Prefabs -> Effects -> Player.
- Set 'Hit Effect' with 'PlayerHitEffect' from Assets -> Prefabs -> Effects -> Player.
- INFO: to be able to test this 2 effects, we need to add an enemy to the screen.
- Add an enemy 'StraightShooter' game object to the Leve1 scene (3.11,3.59,0). Assets -> Prefabs -> Enemies -> IndividualEnemies -> StationaryEnemies.
- INFO: Player location is (0,0,0).
- INFO: Run the game to test. But no hit to the player.
- INFO: Because there is no physics applied to the player.
- INFO: Unity has 2 physics engine. 2D and 3D.
- INFO: Use 2D physics components all the time in 2D games.
- Add new 'Rigidbody 2D' component to the 'Player'.
- INFO: * Now our player will be effected by physics.
- INFO: If you run the game, 'Player' gameobject will drop from the game screen becase 'Gravity Scale' property has set as 1.
- Change the 'Gravity Scale' in 'Rigidbody 2D' component in 'Player' gameobject from 1 to 0.
- INFO: if you run the game, now Player is not dropping but still not getting hit from the enemy.
- INFO: because 'Rigidbody 2D' is only a part of the physics puzzle.
- INFO: other part is the 'Collider 2D' component.
- INFO: if you go the the enemy, you can see the 'Collider 2D' component as green line on it.
- INFO: We will apply the same component to the 'Player' now.
- Change 'Collusion Detection' in 'Rigidbody 2D' component from 'Discrete' to 'Continues'. it makes collusion detection more smoothly.
- Change 'Sleeping Mode' in 'Rigidbody 2D' component from 'Start Awake' to 'Never Sleep'. It makes 'Rigidbody' always active.
- Add 'Polygon Collider 2D' component to the 'Player' gameobject.
- Select 'Edit Collider' property in 'Polygon Collider 2D' in 'Player'
- Reshape the borders of the collider in 'Scene Window' to fit it best.
- INFO: run the game and try to get it, now the player explodes.




























