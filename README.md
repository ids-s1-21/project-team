Maximising Profits for Broadway Theatres
================
team

## Summary

Gross revenue is important to brands and companies as it directly
reveals whether income outweighs expenses and affects sellers’ decision
on whether to continue this transaction. Therefore, finding ways to
maximize gross revenue is necessary for a long lasting company. In this
project, we focus on Broadway musicals weekly grosses (weekly box office
gross for all shows). Comparing weekly gross in various theaters, we
plan to explore factors that attribute to different amount of revenue
and how they are related to each other.

Our research topic is: How to maximize revenues for Broadway theaters?

The dataset used comes from Playbill, which is a US magazine for
theatre-goers. The information of weekly box office grosses comes from
‘The Broadway League’, an association for Broadway theatres.

There are 47,524 observations of shows included at different times of
the year. There are 14 variables. Some of the more important ones which
we will be using in our analysis include the following:

1.  `weekly_gross`
2.  `avg_ticket_price`
3.  `seats_sold`
4.  `seats_in_theatre`
5.  `pct_capacity`
6.  `performances`

Initially, we wanted to look at how average ticket price could be
impacted by the different variables as well, but we realised that there
was no clear relationship that could be concluded. Thus, to increase the
depth of our analysis, we decided to focus on gross revenue instead,
specifically on how average ticket price can impact gross revenue.

Our hypothesis is: Theatre’s weekly gross revenue is affected by average
ticket price, theatre size, percentage of seats capacity sold, number of
weeks being run, and number of performances in the week. Specifically,
larger theatre size, higher average ticket price, higher percentage of
seats capacity sold, higher number of performances in the week, and
lower number of weeks the performance was showing attribute to higher
weekly gross revenue.

We created various visualizations, generated a model, and applied
inferential statistics to aid us in our investigation. Here is a summary
of the following graphs we found useful and included in our
presentation:

### Mutation of `theatre_size`

Since “percentage of seat capacity sold” may be a factor affecting
weekly gross and differs depend on total seats in theater, we first drew
a density graph to see how “seat capacity” is distributed. As the graph
reveals, the seat capacity varies between different theaters. The size
of a theatre might be a factor which influences the relationship between
variables. Therefore, we mutated the theatres into “large”, “medium”,
and “small” using numbers based on the distribution we see in the
density graph.

### Frequency of Weekly Gross Revenue

As a preliminary visualisation to better understand the data, two
different versions of this graph were incorporated. The first was a
simple black-and-white one, where we see the distribution is
right-skewed, with most shows earning approximately $0.5 million per
week. Only a few shows manage to earn above $3 million, and that might
be considered special occasions such as finale or opening weeks, where
there is a surge in demand.

The second version was completed after a mutation to the dataset was
complete, where we divided theatres into small, medium, or large. Within
the graph, we can see that small theateres generally earn less revenue
due to less seats being sold, as opposed to large theatres. Large
theatres, as shown in the visualisation, tends to have a higher
probability of being able to earn more. The peak of the different
theatre sizes seems to earn higher and higher revenue, the larger they
are. This suggests that indeed, one of the factors that affect weekly
gross revenue is the theatre size.

### Percentage of Seats Capacity Sold and Weekly Gross Revenue:

We plotted a scatter plot for the visualization of “weekly gross
revenue” vs. “percentage of seats capacity sold” and mapped colours
according to theatre size. The plot reveals the fact that higher
percentage of seats capacity sold leads to higher weekly gross revenue.
Besides, we find that even under same percentage, theatres with larger
size will have higher weekly gross revenue. This is the same as we
expected, since the total number of seats is higher in larger theatres.
What’s interesting is that those with above 100% in seat capacity
actually had less revenue. This likely meant that standing seats tickets
were sold and lower priced, thus dragging average pricec down. This may
in turn decrease the weekly gross revenue resulting in those points.

### Week Running and Weekly Gross Revenue:

We thought that total number of weeks the show is being run might be a
factor. However, because there wasn’t such a variable in our data, we
mutated and counted different shows. We also had to separate out same
shows that were being played in different theatres. However, as we
visualised it in a scatter plot, there is no clear relationship. It
seems to be completely random, hence, the weeks running of the show is
not a factor of weekly gross revenue.

### Number of Performances in the Week and Weekly Gross Revenue:

We then made a scatter plot of “weekly gross revenue” against “number of
performances in the week”. However, the graph doesn’t indicate any
relationship between them since the data are randomly disbributed
without any pattern (that is, theatres with low number of performances
per week can have high weekly revenue, while those with high number of
performances per week may receive revenue not as high). This is the same
for the relationship between “number of performances in the week” and
“average ticket price”.

### Main Research: Average Ticket Price and Weekly Gross Revenue

In the graph to graph average ticket price with weekly gross revenue,
the initial points seem to go up linearly, but then come down,
suggesting an exponential relationship, as seen below.

![](README_files/figure-gfm/main-question-1.png)<!-- -->

Economically, the graph makes sense. Average ticket prices increasing
would increase gross revenue logically. However, at a certain point as
price continues increasing, the demand becomes price inelastic, which
means the consumers become more reluctant to buy the tickets due to high
price, so the seats sold drops, resulting in lower gross revenue at high
prices.

To see if this was indeed the case, we plotted a graph between seats
sold and average ticket price. As you can see with the graph in our
presentation, there are several red points, where price \> 400. Below
this threshold, it seems consumers do not really mind the price, they
would still be willing to buy it, suggesting that they have relatively
price inelastic demand. However, above 400, consumers seem to be more
reluctant to buy the tickets. Surprisingly, these shows are all played
in medium sized theatres, rather than small ones, where one would expect
price to be larger due to higher demand.

Going back to the initial graph, we decided a log-log model might be the
best, and hence we mutated a new value to take the logs of weekly gross
revenue and average ticket price. However, before we did that, we had to
add 0.0001 to each point since there were observations with values of 0
for both variables, then we plotted a graph to make sure we could indeed
use linear model regression.

We set the linear regression model, splitting our data into testing and
training, whilst creating a recipe and workflow, and was able to derive
the R squared and RMSE values for testing and training data, which we
found to be relatively similar. Both the R squared and RMSE value is
similar for both training and testing data, where both R squared values
were relatively high at around 0.91 and RMSE values were relatively low
at around 0.45.

Here is the mathematical equation that we derived from the model:
*y* = *e*<sup>6.81</sup>*x*<sup>1.51</sup>

### Conclusion:

Among the variables we investigated, we found that theatre size,
percentage capacity, and average ticket price influenced weekly gross
revenue of shows, whereas neither the number of weeks the performance
was showing nor the number of performances in a week had an effect. The
relationship modelled between average ticket price and weekly gross
revenue was quite successful as we found a relatively accurate model.

The result proves some of our hypothesis. It reveals that to maximize
theatre’s gross revenue, the theatre size needs to be larger, with a
high percentage of seats capacity sold each show, and a medium average
ticket price that is neither too high or too low.

Some limitations we faced with this data could likely be the geography,
because it is limited to Broadway only, which could only be applicable
to a certain set of customers. The data set size is also a limitation.

As an extension, we could hopefully find another model in the future
that would be able to consider the curvature of the graph, making a more
accurate model, since the log models do not encompass that section of
the graph. We could also investigate why there are values of 0 for
average ticket prices for some shows.

## Presentation

Our presentation can be found
[here](https://rpubs.com/Felix_Fung/842730).

Our pre-recorded video can be found
[here](https://media.ed.ac.uk/media/IDS+2021-2022+PresentationA+team/1_ac93sfh1).

## Data

Hughes, E. & Mock, T. (2018, April 28), Broadway weekly grosses,
<https://github.com/rfordatascience/tidytuesday/blob/master/data/2020/2020-04-28>

See <http://libraryguides.vu.edu.au/c.php?g=386501&p=4347840> for
guidance on proper citation for datasets. If you got your data off the
web, make sure to note the retrieval date.

## References

Hughes, E. & Mock, T. (2018, April 28), Broadway weekly grosses,
<https://github.com/rfordatascience/tidytuesday/blob/master/data/2020/2020-04-28>
