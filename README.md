# Reinforcement Learning Model for the Chrome Dino game

A notebook that gives the process of creating a custom game environment, creating the step and reward functions, and training a DQN model for 250,000 epochs to learn how to play the chrome Dino game. The high schore achieved by the trained model is 612.

## Table of Contents
- [Overview](#overview)
- [Model Arch and Game Environment](#model-architecture-and-game-environment)
- [Training](#training)
- [Results and Demo](#results-and-demo)
- [Usage](#usage)
- [License](#license)

## Overview

This project is an exploration into using the DQN algorithm, along with Open CV, Tesseract, MSS, and OpenAI Gymnasium, to train an AI to play a game. I am new to this subject so I chose an easier game to train (the chrome dino game), but this can be extrapolated to almost any game with updated reward functions and step options. This model was trained 250,000 times for over 13 hours in order to achieve performance that is pretty good (high score of 612).

## Model Architecture and Game Environment

The game environment was created using pyautoGUI for keyboard and click inputs, the pytesseract library to turn "GAME OVER" text into machine readable text, the OpenAI Gymnasium to create the custom env within a browser (the game), and MSS for screen capturing that feeds the model. The game env essentially runs inside of the browser and takes pictures of the current game stage every frame. Then, this goes into the steps in which the AI can choose the space bar (jump), the down arrow (duck), or no key at all (no-op). The observations that are collected are transformed with Open CV and sent to the model. If the dinosaur dies, the GAME OVER text should be read by the observation using Tesseract whihc prompts the game to either start over or end (depending on what the user wants). The actual model used is the DQN model provided by stable-baselines-3 which integrated PyTorch. This model allows the model to learn based of the reward function, gradient descent back propogation, and the experience replay buffer.

## Training

This model was trained 250,000 epochs and took over 13 hours to train. Even still, there is lots of room for improvement and I believe that training the model for close to 1,000,000 epochs would provide great results. The high score of the model is 612 which is acceptable, but still easily beatable by a human. For reference, the game is [here](chrome://dino).

## Results and Demo

As stated, the high score for this AI was 612, with the average score being in the 200-300 range. This is relatively good results for the amount of training, however the model could be vastly improved by training for longer, potentially using Docker or other containers to train multiple games at once, and other options. A demo of the AI running for 5 runs is shown below. The max score for these 5 runs was 463 and you can see that the AI has definitely learned enough to be useable!

https://github.com/user-attachments/assets/9b9fb4eb-3871-4e40-b122-6930f44643ff


## Usage

To use this project, follow these steps:

1. **Clone the repository**:
   ```bash
   git clone https://github.com/nogalcy/chrome-dino-AI.git
   cd chrome-dino-AI
2. Run the 'dino-AI.ipynb' notebook in order to get full results, this notebook will install dependencies, create the game env, and you can skip the training code to simply load the model provided (best_model_250000.7z)

## License

This project is licensed under the MIT License - see the [LICENSE](https://github.com/git/git-scm.com/blob/main/MIT-LICENSE.txt) file for details.

## Contact

For any questions or inquiries, please reach out to me:

- **Email**: clogan2004@gmail.com
- **LinkedIn**: [My Profile](https://www.linkedin.com/in/cy-logan/)
- **GitHub**: [My Profile](https://github.com/nogalcy)
