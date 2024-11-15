# Secure Multi-Party Computation (SMPC) for Federated Learning

## Project Overview
This project explores the application of **Secure Multi-Party Computation (SMPC)** in federated learning to train agents (mice) to navigate a grid world while avoiding predators (cats). SMPC ensures that the federated learning process is **privacy-preserving**, protecting the individual data of each participant.

The project combines **Reinforcement Learning (RL)** techniques such as:
- **Tabular Q-Learning**
- **Deep Q-Learning**
- **Federated Deep Q-Learning**
- **Federated SMPC Deep Q-Learning**

## Key Features
- **Privacy-Preserving Federated Learning**: Incorporates SMPC to securely aggregate models from multiple agents without exposing their individual data.
- **Multi-Agent Reinforcement Learning**: Agents learn in parallel to navigate a dynamic environment.
- **Customizable Environment**: Configurable grid world with adjustable parameters for learning and gameplay.

---

## Project Structure
```plaintext
├── __pycache__/             # Python cache files
├── resources/
│   └── world.txt            # Definition of the grid environment
├── results/                 # Training results
│   ├── *.npz                # Saved models and performance metrics
├── CatandMouse.py           # Main script for simulation and training
├── config.py                # Configuration file for environment and learning parameters
├── qlearn.py                # Q-Learning and Deep Q-Learning implementations
├── results.py               # Analysis and visualization of training results
├── setup.py                 # Environment and agent setup
├── temp.ppm                 # Temporary files
└── README.md                # Project documentation

Setup Instructions
Prerequisites

    Python 3.8 or higher
    Required packages:
        numpy
        torch
        matplotlib
        crypten (for SMPC)

Install dependencies:

    pip install numpy torch matplotlib crypten

Run the Simulation

To start the simulation, execute:

    python CatandMouse.py

Analyze Results

Generate performance metrics and visualize results:

    python results.py

Configurations

Modify config.py to adjust the simulation and learning parameters:
Environment Settings

    graphic_file: Path to the grid world file.
    grid_width: Grid cell size in pixels.
    speed: Speed of agents.

Learning Parameters

    alpha: Learning rate.
    gamma: Discount factor for future rewards.
    epsilon: Exploration probability.
    LEARNING_MODE: Select the learning mode:
        'Tabular_QLearning'
        'Deep_QLearning'
        'Federated_Deep_QLearning'
        'Federated_SMPC_Deep_QLearning'

Rewards and Penalties

    EATEN_BY_CAT: Penalty for being caught by the cat.
    MOVE_REWARD: Reward for valid movements.
    HIT_WALL: Penalty for hitting a wall.

Federated Learning Parameters

    number_of_worlds: Number of agents participating in federated learning.
    nb_maj_required_to_update_main_model: Number of steps before updating the main model.

Learning Methods
1. Tabular Q-Learning

Uses a table to store Q-values for state-action pairs.
2. Deep Q-Learning

Employs a neural network to approximate Q-values for complex environments.
3. Federated Deep Q-Learning

Combines models trained independently by multiple agents into a single global model.
4. Federated SMPC Deep Q-Learning

Adds a layer of privacy by using SMPC to securely aggregate weights from individual models.
Results

Training results are stored in the results/ directory as .npz files:

    lifetime: Average lifetime of agents.
    var: Variance in agent performance.
    time: Total runtime of the simulation.

Visualization

Use results.py to generate plots for:

    Average Lifetime: Tracks agents' survival over time.
    Variance: Evaluates performance consistency across agents.
