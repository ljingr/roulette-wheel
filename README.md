# Roulette Simulation

This repository contains a Python script for simulating a roulette wheel. The script allows you to spin a roulette wheel, place bets on colors and numbers, and calculate potential winnings. It demonstrates the concept of the law of large numbers and the negative expected value of roulette.

## Features

- Simulate spins of a roulette wheel with 38 slots (including 0 and 00).
- Bet on colors (red, black, green) or specific numbers.
- Generate reports on the outcomes of the spins.
- Calculate total winnings based on bets.

## Requirements

- Python 3.x
- Pandas
- Click

You can install the required packages using:

```bash
./setup.sh
```
## Usage

### Spin the Roulette Wheel

To simulate spins of the roulette wheel, use the `spin` command. This command lets you specify the number of spins, the amount to bet, and whether you want to bet on a color or a number.

#### Command Syntax

```bash
python roulette.py spin --count <number_of_spins> --bet <bet_amount> [--color <color>] [--number_bet <number>]
```

* --count (default: 1): Total number of spins.
* --bet (default: 1): Amount of money to bet on each spin.
* --color (optional): Color to bet on. Choices are "red", "black", "green".
* --number_bet (optional): Specific number to bet on (0 to 36).

### Example
Spin the wheel 10 times, betting $1 on red:

```bash
Copy code
python roulette.py spin --count 10 --color red --bet 1
```

## Code Overview
* build_wheel(): Creates a DataFrame representing the roulette wheel with slots, colors, and probabilities.
* spin_wheel(wheel): Simulates a single spin of the wheel.
* simulate_spins(wheel, spins): Simulates multiple spins and returns the results.
* generate_report(results, full_report=False): Generates a report on the simulation results.
* calculate_winnings(results, bet, count, color=None, number=None): Calculates the winnings based on bets.
* print_wheel(results): Prints the results of the simulation with color styling.
* spin_option(count, bet, number_bet, color): CLI command to spin the wheel and handle bets.

## Future Improvements
* Support for betting on multiple numbers and colors.
* Different bets on different spins.
* Interactive Jupyter notebook to show historical results.
* Web interface using Streamlit or Gradio.