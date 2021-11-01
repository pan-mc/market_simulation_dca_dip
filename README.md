# market_simulation_dca_dip
This script does monte carlo simulations on stock market and calculate final profolio based on two stock-purchase methods

# Each simulation includes the following
1. Simulate stock market price (Monte Carlo)
2. calcalate shares bought, final asset, overall gain using two purchase method: daily cost average (dca) & buy the dip (dip) using simulated stock marekt price

Finally after the simulations are done, calculate compare average gains from the two method



## Simulation of stock market price
Stock market price = start_price * standard_deviation * crash * growth
1. standard_deviation: input historic yearly standard deviation (configurable) applied daily
    Each simulation will re-generate the stdev function
2. crash: crash intervals (and its proibability) & crash magnitude (and its probaility) are two independent set of inputs from analysis done separately
    Each simulation will re-generate the crash function
3. growth: input nominal yearly growth rate (configurable) 
    input as a list so the scripts can calulate a few at one execution
    in the implementation, use the input & crash functions to make sure the overall growth are meeting the inputs
                
## Purchase method
1. daily cost average (dca): buy stock at current price using set amount of principal (configurable) at set interval of days (configurable)
2. buy the dip (dip): 
    for fair comparison to dca method, the script calcualte how much capital has accmulated till the crash day
    then use the available capital to buy at the percentage (configurable) to previous high
        this is because typically no one can predict the lowest point and will have a number in mind to purchase relative to previous high
