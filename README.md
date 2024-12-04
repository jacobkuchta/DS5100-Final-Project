# DS5100-Final-Project
Metadata: 
  - Project Name: Monte Carlo Simulation
  - Version: 1.0
  - Author: Jacob Kuchta
  - Author Email: mjk3ku@virginia.edu
  - Program: UVA MSDS
  - License: MIT

Synopsis:

- Die Class
  from montecarlo import Die
  
  # Create a die
  faces = np.array([1, 2, 3, 4, 5, 6])
  die = Die(faces)
  
  # Roll the die 20 times
  rolls = die.roll(20)
  
  # Change the weight of face 5
  die.change_weights(5, 2.0)
  
  # Show the current state of the die
  print(die.show_die())

- Game Class
  from montecarlo import Game
  
  # Create multiple dice
  first_die = Die(faces)
  second_die = Die(faces)
  
  # Initialize a game with these dice
  game = Game([first_die, second_die])
  
  # Play the game 20 times
  game.play(20)
  
  # Show the results
  print(game.show_recent_result())


- Analyzer Class
  from montecarlo import Analyzer
  
  # Initialize an Analyzer with a completed game
  analyzer = Analyzer(game)
  
  # Calculate the number of jackpots
  jackpots = analyzer.jackpot()
  
  # Count the occurrences of each face per roll
  face_counts = analyzer.face_counts()
  
  # Compute distinct combinations
  combo_counts = analyzer.combo_count()
  
  # Compute distinct permutations
  permutation_counts = analyzer.permutation_count()

  # Show the results
  print(jackpots)
  print(face_counts)
  print(combo_counts)
  print(permutation_counts)



API:

  - Class: Die;
     Methods:
        __init__(faces), 
        change_weights(value,new_weight), 
        roll(n_rolls=1), 
        show_die()
   
        
  - Class: Game;
     Methods:
        __init__(similar_dice), 
        play(n_rolls), 
        show_recent_result(form="wide") 

  - Class: Analyzer;
     Methods:
        __init__(game), 
        jackpot(), 
        face_counts(), 
        combo_count(), 
        permutation_count()
