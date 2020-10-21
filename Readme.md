**Summary**

We used supervised machine learning techniques and more specifically regression to predict seizures. The database from which we took our data contains EEG recordings of 22 people, in which 9-42 experiments were performed with a small number of them containing one or more episodes of epilepsy. Each experiment contains approximately 1 hour of data from 22 different channels at a frequency of 256 values ​​per second.

We did two tests, one using the epilepsy experiments of the first patient and a second one with random epilepsy experiments from the first 10 patients.

**Method**

In fig1 we see an indicative experiment from the first patient in channel 12 and the period of epilepsy occurrence.
![](/results/1.png)

Then as shown in fig2 we select a period of 10 minutes before epilepsy and give a chance of epilepsy (green line). We chose this probability to rise after 2 minutes before it started, with a probability equal to 1 at the point where the epilepsy begins.

![](/results/2.png)

Within these 10 minutes we select intervals of one minute per second until the onset of epilepsy and in each interval we use the present frequencies to draw some conclusions. More specifically, this is done in each experiment and for each channel, for example

![](/results/3.png)

selecting a specific frequency from 10-14 (fig3) for each one minute window we take, we end up with the following indicative table. The columns present the different channels and the possibility of epilepsy (y) and for rows the one minute windows that we take per second, with the corresponding values ​​that result if we calculate the average amplitude of the frequencies from 10-14.

![](/results/4.png)

**Results**

In our results we tested a wide range of frequencies and chose the most efficient ones. The selection of all these frequencies was done in two ways, one by producing many random intervals and the other by choosing the most powerful ones.(fig4,fig5)

![](/results/4,5.png)

In the first test we used the six experiments with epileptic events of the first patient, where we trained at five of them and tested at the sixth. To evaluate the results we combined R squared, Mean Absolute Error and Mean Squared Error and selected the frequencies with the best measurements. The following figures show the average values of the best results. The green values are the real values and the blue ones are the predicted ones.

![](/results/linear1.png)  
\
\
![](/results/decision1.png)  
\
\
![](/results/random1.png)  
\
\
![](/results/k1.png)

The table below shows the corresponding average values of the evaluation measures.

![](/results/table1.png)

For the second test we used random experiments from ten different patients. In contrast to the previous case, the data were randomly distributed and the training was done on 70% of the data as well as the forecast on the remaining 30%. As shown here, the results are very good except Linear regression.

![](/results/linear2.png)  
\
\
![](/results/decision2.png)  
\
\
![](/results/random2.png)  
\
\
![](/results/k2.png)  
\
\
![](/results/table2.png)

This analysis still has a lot of room for improvement but it could be a good start of a DSS for epileptic seizures prediction since we can see that there is a high success rate.
