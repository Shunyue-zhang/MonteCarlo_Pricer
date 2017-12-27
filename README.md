# MonteCarlo_Pricer
use variance reduction method to simulate underlying and then price the corresponding derivatives
The steps are listed below:
1. Simulate the underlying price based on lognormal distribution $dS = \mu * S * dt + \sigma * S * dB$, 
where S is underlying price (stock price), \mu is the expected return (get from the analyst report), \sigma is the historical stock price volatility, B is the Brownian motion, which is subject to normal distribution N(0, t)
2. Get the all simulated stock prices at time T (let's say 2000 simulated prices)
3. Calculate average price P_average = (P1+P2+..+P2000)/2000
4. Get final payoff of derivative ( we use European call options as an example here). Payoff_average = (P_average - Strike)^+
5. Get the price of derivative by multiply the discounted factors. Price_derivative = discounted_factor * Payoff_average.
