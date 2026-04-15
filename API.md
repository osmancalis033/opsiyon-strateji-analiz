# Python API Documentation

## Greeks Calculation

You can calculate the Greeks using the `GreeksCalculator` class. Here’s a simple example:

```python
from options_package import GreeksCalculator

greeks_calculator = GreeksCalculator()

# Example parameters
spot_price = 100.0
strike_price = 100.0
interest_rate = 0.05
volatility = 0.2
days_to_expiration = 30

# Calculate the Greeks
delta = greeks_calculator.calculate_delta(spot_price, strike_price, interest_rate, volatility, days_to_expiration)
print(f"Delta: {delta}")
```

## Strategy Creation

To create a strategy, utilize the `StrategyBuilder` class. Here’s an example:

```python
from options_package import StrategyBuilder

strategy_builder = StrategyBuilder()

# Define your strategy
strategy = strategy_builder.create_strategy(name="Bull Call Spread")
strategy.add_leg(leg_type="call", strike_price=105, quantity=1)
strategy.add_leg(leg_type="call", strike_price=110, quantity=-1)
print(strategy)
```

## P&L Computation

You can compute the profit and loss using the `ProfitLossCalculator` class as follows:

```python
from options_package import ProfitLossCalculator

pl_calculator = ProfitLossCalculator()

# Example trade details
entry_price = 1.5
exit_price = 2.0
quantity = 10

# Calculate P&L
profit_loss = pl_calculator.compute_pl(entry_price, exit_price, quantity)
print(f"P&L: {profit_loss}")
```

## Data Loading

Load data using the `DataLoader` class:

```python
from options_package import DataLoader

data_loader = DataLoader()

data = data_loader.load_data(source="path/to/data.csv")
print(data.head())
```

## Parameter Adjustment

You can adjust parameters with the `ParameterAdjuster` class. Here’s how:

```python
from options_package import ParameterAdjuster

parameter_adjuster = ParameterAdjuster()

# Adjusting parameters
new_parameters = parameter_adjuster.adjust_parameters(current_parameters={"strike_price": 110}, adjustment_factor=1.05)
print(new_parameters)
```

---

This documentation provides a basic overview of the functionalities available through the Python API for options strategy analysis. Adjust the examples according to your specific requirements.