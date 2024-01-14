# Single Server Queue Simulation for A Small Grocery Store

This Python project simulates the arrival and service of customers in a single-server queue system for a small grocery store. The simulation includes the generation of random interarrival times, the calculation of arrival times, service time generation, and the computation of various performance measures.

## Table of Contents
1. [System Initialization](#system-initialization)
   1. [Interarrival Time Generation](#interarrival-time-generation)
   2. [Arrival Time Calculation](#arrival-time-calculation)
   3. [Service Time Generation](#service-time-generation)
   4. [Service Time Begins and Ends](#service-time-begins-and-ends)
   5. [Waiting Time in Queue](#waiting-time-in-queue)
   6. [Time Customer Spends in System](#time-customer-spends-in-system)
   7. [Idle Time of the Server](#idle-time-of-the-server)
   8. [Total Time Customers Spend In The System](#total-time-customers-spend-in-the-system)
   
2. [Results Visualization In Simulation Table](#results-visualization-in-simulation-table)
   
3. [Typical Performance Measures of a Queuing System](#typical-performance-measures-of-a-queuing-system)
   
4. [Performance Histograms](#performance-histograms)
   1. [Frequency of individual customer waiting time](#frequency-of-individual-customer-waiting-time)
   2. [Average customer waiting](#average-customer-waiting)

## System Initialization

### Interarrival Time Generation
The random interarrival times are generated using the `interArrivalTime` function, ensuring the first customer's arrival time is initialized to 0.

### Arrival Time Calculation
Arrival times are calculated by accumulating the interarrival times.

### Service Time Generation
Random service times are generated based on the given service times and their probabilities using the `serviceTime` function.

### Service Time Begins and Ends
The times when service begins and ends are calculated, considering the maximum of arrival time and the previous service end time.

### Waiting Time in Queue
The waiting time in the queue is computed using the `queueTime` function.

### Time Customer Spends in System
Each customer's time in the system is calculated using the `timeInSystem` function.

### Idle Time of the Server
The idle time of the server is determined by comparing arrival times and the previous service end time.

### Total Time Customers Spend In The System
The total time customers spend in the system is calculated using the `totalTimeInSystem` function.

## Results Visualization In Simulation Table
The results are visualized in a table using Plotly, showing various parameters for each customer.

## Typical Performance Measures of a Queuing System
Key performance measures are calculated, including average waiting time, probability of waiting, probability of idle server, average service time, average time between arrivals, average waiting time of those who wait, and average time a customer spends in the system.

## Performance Histograms

### Frequency of individual customer waiting time
A histogram is plotted to visualize the frequency distribution of individual customer waiting times.

```python
# Code for plotting the histogram
plt.style.use("bmh")
fig, ax = plt.subplots()
ax.hist(queue_time, bins = 15, linewidth = 1.0, align='mid', edgecolor = "white")
x = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
default_x_ticks = range(len(x))
plt.xticks(default_x_ticks, x)
plt.ylim(0, 70)
plt.xlabel("( Queue waiting Times )")
plt.ylabel("( Frequency )")
plt.title("(Frequency of individual customer waiting time)")
plt.show()
