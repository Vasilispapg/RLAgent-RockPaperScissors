# Rock-Paper-Scissors Reinforcement Learning Project

Google Colab Code: [Google Colab Viewer Link](https://colab.research.google.com/drive/1Gf3AMGoCA3JIn-UlToRl9--7PE7ZzQAy?usp=sharing)

## Overview
This project presents a Reinforcement Learning (RL) agent trained to play Rock-Paper-Scissors. Utilizing Convolutional Neural Networks (CNN) within a Deep Q-Learning framework, the agent interacts with a custom gym environment, processes image data for state representation, and learns strategies to maximize rewards. The project also features a Random Agent responsible for image preprocessing and noise addition, adding complexity to the agent's training environment.

## Features
- **Image Processing**: Loading and preprocessing of Rock, Paper, and Scissors images, including resizing and normalization.
- **Data Splitting**: Stratified splitting of the dataset into training and testing sets with balanced class representation.
- **Custom Environment**: A gym-based environment specifically designed for the Rock-Paper-Scissors game, facilitating diverse game state interactions.
- **Random Agent for Image Preprocessing**: A separate agent applies noise and transformations to images, increasing the training model's robustness.
- **Agent Design**: The RL agent employs a CNN for state evaluation and decision-making, with a replay buffer for experience storage and learning. The agent manages a budget and calculates scores based on game outcomes.
- **Training and Evaluation**: Scripts for training the agent using reinforcement learning and evaluating its performance, including budget management and game outcome tracking.

## Dependencies
- OpenCV
- NumPy
- TensorFlow and Keras
- Gymnasium (a fork of OpenAI Gym)

## Usage
1. **Image Loading and Preprocessing**: Images for each state (rock, paper, scissors) are loaded and preprocessed.
2. **Random Agent Image Processing**: The Random Agent applies noise and transformations to the images for a more robust training environment.
3. **Environment Setup**: Initialization of the custom Rock-Paper-Scissors environment with these images.
4. **Agent Initialization**: Creation of an RL agent with CNN, budget tracking, and scoring mechanics.
5. **Training**: The agent learns over many game episodes, improving its policy and managing its budget.
6. **Evaluation**: Post-training, the agent's performance is evaluated in terms of wins, losses, draws, and budget management.

## Custom Game Environment
The `RockPaperScissorsEnv` class extends the `gym.Env` class, providing the necessary functionality for the Rock-Paper-Scissors game. This includes defining game rules and managing game outcomes.

## RL Agent
The `Agent` class encapsulates the RL logic, including the CNN model, action selection, memory for experience replay, budget management, and a learning mechanism. It interacts with the environment and improves decision-making over time, considering both game outcomes and budget constraints.

## Learning and Game Scripts
- The learning script (`learn`) allows the agent to experience multiple episodes, storing experiences and adapting its strategy.
- The game script (`game`) evaluates the trained agent's performance, tracking wins, losses, draws, and budget changes.

## Image Test
The project includes a script for testing the agent's decision-making using user-provided images, allowing for real-world scenario evaluations.

## Budget and Scoring
The agent is designed to manage a budget and calculate its score based on game outcomes, adding a layer of complexity and realism to the training and evaluation process.

## Process

The process of this project is divided into several key stages, each playing a crucial role in the development and functioning of the RL agent:

### 1. Image Loading and Preprocessing
- **Function**: `load_images_from_folder`
- **Purpose**: Loads and preprocesses images from specified directories. Images are converted to grayscale, resized to 28x28 pixels, and normalized.
- **Output**: Arrays of processed images and corresponding labels for rock, paper, and scissors.

### 2. Data Stratification and Splitting
- **Function**: `split_data`
- **Purpose**: Splits the data into training and testing sets for each class (rock, paper, scissors) separately. This ensures equal representation of each class in both sets.
- **Output**: Training and test sets with a default split of 70% training and 30% testing.

### 3. Random Agent Image Processing
- **Class**: `RandomAgent`
- **Purpose**: Applies noise and transformations to the preprocessed images, enhancing the robustness of the training data for the RL agent.
- **Process**: The Random Agent randomly selects images, applies vertical and horizontal flips, and adds random noise to create a more varied and challenging dataset for training.

### 4. Environment Setup
- **Class**: `RockPaperScissorsEnv`
- **Purpose**: Creates a custom game environment compatible with gym. The environment uses the preprocessed and transformed images to simulate game states.
- **Features**: Methods for image selection, preprocessing, and defining the game rules.

### 5. Agent Initialization
- **Class**: `Agent`
- **Purpose**: Initializes the RL agent with a specified state size, action size, and neural network architecture.
- **Features**: The agent uses a CNN for decision-making, supported by methods for action selection, memory updating, and learning from experiences.

### 6. Training the Agent
- **Script Section**: `Learn`
- **Purpose**: Runs the agent through multiple game episodes, allowing it to learn from its actions' outcomes.
- **Process**: In each episode, the agent selects actions based on its policy, stores the experience, and updates its knowledge after each game round.

### 7. Agent Evaluation
- **Script Section**: `Game`
- **Purpose**: Tests the trained agent's performance in the game environment, providing insights into its learning and decision-making capabilities.
- **Process**: The agent plays a set number of games, making decisions based on its trained model, and the outcomes (win/lose/draw) are tracked.

### 8. Testing with Custom Images
- **Script Section**: `Image from me`
- **Purpose**: Allows testing the agent's decision-making with custom, user-provided images.
- **Process**: The user's image is preprocessed and fed into the trained model to evaluate the agent's response in a real-world scenario.
