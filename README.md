# 1D Multi-Agent Littering Dynamics Simulator

[**Live Demo on GitHub Pages**](https://zackakil.github.io/Broken-window-litter-sim)

This project is a single-file HTML/JavaScript simulation designed to model the social and environmental dynamics of littering and cleanup on a simplified, one-dimensional street. It allows users to explore how agent flow, cleanup efficiency, and the **Broken Window Phenomenon** affect the overall state of cleanliness.

## 🚀 How to Run

There are two ways to interact with the simulator:

1. **Recommended (Live Demo):** Visit the deployed version directly at the GitHub Pages URL: **`https://zackakil.github.io/Broken-window-litter-sim`**.

2. **Local Copy:**

   * Copy the content of the `litter_simulator.html` file.

   * Save the code as an HTML file (e.g., `litter_sim.html`).

   * Open the file directly in any modern web browser.

3. **Start Simulation:** Adjust the parameters using the sliders and press the **Start Simulation** button.

## 🏙️ Simulation Overview

The simulation consists of a single **50-block street** with four lanes of traffic. The state of each block is tracked (clean or littered).

| **Component** | **Visual Representation** | **Description** | 
 | ----- | ----- | ----- | 
| **Street Blocks** | Green horizontal surface | The 50 discrete locations where litter can exist. | 
| **Litter** | 🥤 (Cup/Can Emoji) | Indicates a block is currently littered (state=1). | 
| **Regular Person** | Blue Square (👤) | Travels along a lane. They are **completely neutral** (do not intentionally drop or pick up litter). | 
| **Litter Picker** | Green Square (✨) | Travels along a lane. They are the **only agents** that pick up litter. | 
| **Litter Chart** | Line Graph | Tracks the total number of litter items on the street over time. | 

## ⚙️ Key Controls and Dynamics

The simulation's behavior is governed by four main control sections:

### 1. Agent Flow Rates

These sliders control the **probability** (flow rate) that a new agent of that type spawns at either end of the street on any simulation tick, influencing the agent population density.

* **Regular Person Spawn Rate (Blue):** Controls the flow of neutral agents.

* **Litter Picker Spawn Rate (Green):** Controls the flow of cleanup agents.

* **Litter Picker Efficiency (Cleanup Probability):** Controls the percentage chance a Litter Picker will successfully clean a littered block when passing over it (modeling capacity or focus).

### 2. Litter Generation

* **Global Litter Drop Base Chance:** This is the baseline probability (%) that *any* passing agent (Regular or Picker) will drop a piece of litter on the block they are on. This represents random, impulse littering.

### 3. Broken Window Effect

This toggleable feature introduces social dynamics where the environment's current state influences behavior, exponentially increasing or decreasing the chance of littering.

| **Parameter** | **Effect when Enabled** | 
 | ----- | ----- | 
| **Toggle Checkbox** | Enables/Disables the dynamic multiplier logic. | 
| **Low Litter Multiplier (0 items)** | Multiplies the Base Drop Chance when the street is perfectly clean (litter count = 0), making littering much harder (e.g., 0.1x). | 
| **High Litter Threshold** | Defines the litter count (e.g., 20) at which the street is considered "broken." | 
| **High Litter Multiplier (Dirty Street)** | Multiplies the Base Drop Chance when the litter count exceeds the threshold, making littering much easier (e.g., 3.0x). | 

### 4. Simulation Speed

Controls the delay (in milliseconds) between simulation steps, affecting the visualization speed and the overall "real-time" flow.
