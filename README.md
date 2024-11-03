# -SWE_CAP2_Game_Automation-

# Programming the Farming Drone (Report)

## Introduction
"The Farmer Was Replaced" is a Python coding game that challenges us to automate 
farm management tasks.In this game, we write Python code to replace a fictional 
farmer who has been automated out of his job. Our task is to develop scripts 
to handle typical farming activities such as planting, watering, harvesting, and trading 
crops, all while maximizing profits and managing resources. Each level introduces new 
complexities, requiring us to use programming concepts like loops, conditionals, 
functions, and data handling to solve problems efficiently. The game is designed to be
educational and entertaining, blending programming skills with strategic thinking.

# Table of Contents
- [Code Snippets and Explanation](#code-snippets-and-explanation)
- [Challenges and Learnings](#challenges-and-learnings)
- [References](#references)


## Step 1: Farming on 1 tile
  **Demo:**
    Video Demo:
    ![](first_tile.mp4)
  **Code:**
   ```python
    while True:
        harvest()
   ```
  **Explanation:**
   - Initially, we need to harvest around five hays manually to activate the infinite loop. This loop will continuously harvest grass using the harvest() function, allowing the drone to gather resources automatically.
  **Notes**
   - This code enables collecting enough hay to unlock the "speed" feature and allows the drone to progress to the next tile.
   - Features unlocked : loop

## Step 2: Farming on 1x3 tile
  **Demo:**
    Video Demo:
    ![](second_tile.mp4)
  **Code:**
   ```python
    while True:
        plant(Entities.Bush)
        move(North)
        do_a_flip()
        harvest()
   ```
  **Explanation:**
   - With the speed upgrade, we can unlock the plant function and expand the tile to 1x3. Using this code, the bot plants a bush (to produce wood) and then moves in different directions to harvest. The move() function is used to navigate each tile, making the drone to manage the expanded farm space.
  **Notes**
   - This code allows collecting sufficient hay and wood to unlock the "senses" and "operator" functions.
   - Features unlocked : operator

## Step 3: Farming on 3x3 tile
  **Demo:**
    Video Demo:
    ![](third_tile.mp4)
  **Code:**
   ```python
   #Till
    while True:
        for i in range(get_world_size()):
            for j in range(get_world_size()):
                move(South)
                till()
            move(East)
    #Planting Carrots
    while True:
        for i in range(get_world_size()):
            for j in range(get_world_size()):
                move(South)
                plant(Entities.Carrots)
                do_a_flip() 
            move(East)
        for i in range(get_world_size()):
            for j in range(get_world_size()):
                move(South)
                harvest()
            move(East)
            do_a_flip()
   ```
  **Explanation:**
    - After unlocking senses, the drone can plant and harvest carrots on a 3x3 grid. This code handles tilling, planting, and harvesting in each tile. So the 'get_world_size()' ensures adaptability to the grid size.
  **Notes**
   - The drone can efficiently manage a larger farm and continuously produce carrots.
   - Features unlocked : loop

## Step 4: Farming on 4x4 tile
  **Demo:**
    Video Demo:
    ![](fourth.mp4)
  **Code:**
   ```python
    while True:
        for i in range(get_world_size()):
            for j in range(get_world_size()):
                move(South)
                plant(Entities.Tree)
            move(East)
        for i in range(get_world_size()):
            for j in range(get_world_size()):
                move(South)
                use_item(Items.Water_Tank)
            move(East)
        for i in range(get_world_size()):
            for j in range(get_world_size()):
                move(South)
                harvest()
            move(East)
            do_a_flip()
   ```
  **Explanation:**
    - At this stage, trees are introduced. The code plants trees, waters them, and harvests resources once they grow. This setup takes advantage of a 4x4 grid, utilizing each tile for optimal farming.
    - Trees are hard to plant as it cannot grow next it one another so we can also use other methods to do so
  **Notes**
   - Watering and managing a larger grid add complexity to farming operations.

## Step 5: Farming on 6x6 tile
  **Demo:**
    Video Demo:
    ![](fifth.mp4)
  **Code:**
   ```python
    while True:
        for i in range(get_world_size()):
            for j in range(get_world_size()):
                move(South)
                till()
            move(East)
        for i in range(get_world_size()):
            for j in range(get_world_size()):
                move(South)
                plant(Entities.Carrots)
            move(East)
        for i in range(get_world_size()):
            for j in range(get_world_size()):
                move(South)
                use_item(Items.Water_Tank)
            move(East)
        for i in range(get_world_size()):
            for j in range(get_world_size()):
                move(South)
                harvest()
            move(East)
   ```
  **Explanation:**
    - With the full 6x6 tile setup, this code manages tilling, planting, watering, and harvesting in a large grid. The functions are applied in sequence to maximize yield across the entire farm space. We use the same codes from above
  **Notes**
   - This advanced setup showcases the d's full farming capabilities and tile management on the largest grid.

## Step 6: Farming Pumpkin
  **Demo:**
    Video Demo:
    ![](sixth.mp4)
  **Code:**
   ```python
    while True:
        for i in range(get_world_size()):
            for j in range(get_world_size()):
                move(South)
                till()
            move(East)
        for i in range(get_world_size()):
            for j in range(get_world_size()):
                move(South)
                plant(Entities.Carrots)
            move(East)
        for i in range(get_world_size()):
            for j in range(get_world_size()):
                move(South)
                use_item(Items.Water_Tank)
            move(East)
        for i in range(get_world_size()):
            for j in range(get_world_size()):
                move(South)
                harvest()
            move(East)
   ```
  **Explanation:**
    - With the full 6x6 tile setup, this code manages tilling, planting, watering, and harvesting in a large grid. The functions are applied in sequence to maximize yield across the entire farm space. We use the same codes from above. Its hard as some pumpkin tends to blast before fully grown
  **Notes**
   - This advanced setup showcases the d's full farming capabilities and tile management on the largest grid.


# Challenges and Learnings
   ## Challenges
    - Identifying and fixing logical errors to ensure the farmer completes tasks as expected.
    - Working within limitations (e.g., finite water or seeds), requiring efficient use of resources.
    - Creating solutions for complex tasks, such as growing tree and pumpkin or finding treasure in maze.

   ## Learnings
    - Optimization: Learn to conserve resources and improve code efficiency.
    - Debugging and Problem Solving: Build resilience and troubleshooting skills.
    - Algorithmic Thinking: Develop strategies for pathfinding and task optimization.

## References
List any resources, articles, or libraries you used or referenced while working on this project.
1. [Youtube](https://www.youtube.com/playlist?list=PLateWiNrGEtoIy8aeWse6dQOCToetjXJg)
2. [ChatGpt](https://chatgpt.com/c/67277fb1-f1f8-8003-b6d5-b7bfdeeeb9fc)
3. [Blackbox](https://www.blackbox.ai/)