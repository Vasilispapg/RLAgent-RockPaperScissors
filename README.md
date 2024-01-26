# Rock-Paper-Scissors Reinforcement Learning Project
Google Colab Viewer Link: https://colab.research.google.com/drive/1Gf3AMGoCA3JIn-UlToRl9--7PE7ZzQAy?usp=sharing
## Overview
This project features a Reinforcement Learning (RL) agent trained to play Rock-Paper-Scissors. It utilizes Convolutional Neural Networks (CNN) within a Deep Q-Learning framework. The agent interacts with a custom environment, processes image data for state representation, and learns decision-making strategies to maximize rewards.

## Features
- **Image Processing**: Implements image loading and preprocessing for Rock, Paper, and Scissors images, including resizing and normalization.
- **Data Splitting**: Stratified splitting of the dataset into training and testing sets, ensuring balanced representation across classes.
- **Custom Environment**: A gymnasium-based environment specifically designed for the Rock-Paper-Scissors game, facilitating the RL agent's interaction with varied game states.
- **Agent Design**: The RL agent is equipped with a CNN model for state evaluation and decision-making, supported by a replay buffer for experience storage and learning.
- **Training and Evaluation**: The project includes scripts for both training the agent with reinforcement learning and evaluating its performance in the game environment.

## Dependencies
- OpenCV
- NumPy
- TensorFlow and Keras
- Gymnasium (a fork of OpenAI Gym)

## Usage
1. **Image Loading**: Images for each game state (rock, paper, scissors) are loaded and preprocessed.
2. **Environment Setup**: The custom Rock-Paper-Scissors environment is initialized with these images.
3. **Agent Initialization**: An RL agent with a CNN model is created.
4. **Training**: The agent is trained over numerous game episodes, learning from the game outcomes.
5. **Evaluation**: Post-training, the agent's performance can be evaluated in the game environment.

## Custom Game Environment
The `RockPaperScissorsEnv` class extends the gym.Env class, providing a unique environment for the RL agent. It includes methods for preprocessing images, selecting game states, and determining rewards based on game outcomes.

## RL Agent
The `Agent` class encapsulates the RL logic, including the CNN model, action selection, memory for experience replay, and learning mechanism. It is designed to interact with the environment and improve its decision-making over time.

## Learning and Game Scripts
- The learning script (`learn`) runs the agent through multiple episodes, storing experiences and updating its knowledge base.
- The game script (`game`) allows for testing the trained agent's performance in the environment.

## Image Test
A separate script is provided for testing the agent's decision-making with user-provided images, offering an additional way to evaluate the model's generalization capabilities.

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

### 3. Environment Setup
- **Class**: `RockPaperScissorsEnv`
- **Purpose**: Creates a custom game environment compatible with gym. The environment uses the preprocessed images to simulate game states.
- **Features**: Methods for image selection, preprocessing, and defining the game rules.

### 4. Agent Initialization
- **Class**: `Agent`
- **Purpose**: Initializes the RL agent with a specified state size, action size, and neural network architecture.
- **Features**: The agent uses a CNN for decision-making, supported by methods for action selection, memory updating, and learning from experiences.

### 5. Training the Agent
- **Script Section**: `Learn`
- **Purpose**: Runs the agent through multiple game episodes, allowing it to learn from its actions' outcomes.
- **Process**: In each episode, the agent selects actions based on its policy, stores the experience, and updates its knowledge after each game round.

### 6. Agent Evaluation
- **Script Section**: `Game`
- **Purpose**: Tests the trained agent's performance in the game environment, providing insights into its learning and decision-making capabilities.
- **Process**: The agent plays a set number of games, making decisions based on its trained model, and the outcomes (win/lose/draw) are tracked.

### 7. Testing with Custom Images
- **Script Section**: `Image from me`
- **Purpose**: Allows testing the agent's decision-making with custom, user-provided images.
- **Process**: The user's image is preprocessed and fed into the trained model to evaluate the agent's response in a real-world scenario.
