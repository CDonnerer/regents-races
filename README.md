# regents-races

A fun little exercise to analyse 10k running races in Regent's park.

## Contents

There are three jupyter notebooks that deal with getting the data, cleaning the data and finally analysing the data.

* [Get the data](scrape_data.ipynb) Here we scrape the data from the website and save it into csv format for each individual race

* [Merge the data](merge_data.ipynb) For the analysis, it is easier to work with one dataframe that contains all the information, so I merged the data.

* [Race analysis](race_analysis.ipynb) This is the fun part where we look at the data!

## Some insights from the analysis

If you want to run your best 10k, two suggestions emerge from the analysis: (1) Do not start too fast and (2) do the race in September.

### 10 k finish times

The easiest analysis is to plot the distribution of finish times:

![time distribution](plots/time_distribution.png)

If we separate the data by gender, we can see a clear split of male and female runners:

![time distribution by gender](plots/time_distribution_by_gender.png)

### Lap times - everyone starts too fast

The dataset also includes the time for each of the three laps. The figure shows the time difference between laps 1 and 2, as a function of lap 1 time. Whenever the data points lie above zero, the second lap was slower than the first:

![Lap 1-2 time difference](plots/lap12_timediff.png)

We find that vast majority of runners slow down, thus we conclude that most runners start too quickly.

### Where to stand at the start of the race

Ideally, at the start of the race, runners would line up from the start line in the order that they finish the race. This would get rid of faster runners overtaking slower runners (although in this race there are three laps, so it gets more complicated). By plotting the time delay upon crossing the start line against final place, we can quantify how well this works in practice:

![delay by place](plots/delay_by_place.png)

Up to the first 100 runners, one can see a linear trend emerging, which is gradually blurred out. This shows that the fastest runners line up closest to the start line, but the subsequent standing order does not clearly reflect the finish place. This is expected, as there are no instructions on where to stand at the start of the race.

We also see that there is a line of data points at 0 min delay extending to high places, i.e. starting right in front. These runners seem to have started right at the front, but did not finish there. There is now clear signal in the data on what distinguishes these runners, it occurs for all genders, years and races. There is no evidence for runners having overestimated their abilities and slowing down strongly during the race.

### Seasonality effects: when to obtain best finish time

It is of interest to explore which races are the fastest. There are six 10k races each year in Regent's park, from April to September. The figure below shows the median finish time over years 2011 to 2017 as a function of race month:

![time seasonality](plots/time_seasonality.png)

We can clearly see the slowest races are in June/ July, whereas September is the fastest race. These seasonality effects likely emerge from different temperatures of the races as well as cumulative training effects at the end of the running season.

Hence the recommendation for running the fastest 10k is to do it in September!