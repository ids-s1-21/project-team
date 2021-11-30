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
4.  `pct_capacity`
5.  `performances`

Initially, we wanted to look at how average ticket price could be
impacted by the different variables as well, but we realised that there
was no clear relationship that could be concluded. Thus, to increase the
depth of our analysis, we decided to focus on gross revenue instead,
specifically on how average ticket price can impact gross revenue.

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

First we look at factors that affect weekly gross revenue.

### Average Ticket Price and Weekly Gross Revenue:

Model,

Though this graph surprised us when we first saw it, after analysis, it
makes sense economically. Average ticket prices increasing would
increase gross revenue logically. However, at a certain point as price
continues increasing, the demand becomes price inelastic, which means
the consumers become more reluctant to buy the tickets due to high
price, so the seats sold drops, resulting in lower gross revenue at high
prices.

### Percentage of Seats Capacity Sold and Weekly Gross Revenue:

We use geom_point for the visualization of “weekly gross revenue”
vs. “percentage of seats capacity sold” and use different colors for
different theatre size. The plot reveals the fact that higher percentage
of seats capacity sold leads to higher weekly gross revenue. Besides, we
find that under same percentage, theatres with larger size will have
higher weekly gross revenue. This is the same as we expected, since the
total number of seats is higher in larger theatres.

### Number of Performances in the Week and Weekly Gross Revenue:

We then use geom_jitter for the plot of “weekly gross revenue”
vs. “number of performances in the week”. However, the graph doesn’t
indicate any relationship between them since the data are randomly
disbributed without any pattern (that is, theatres with low number of
performances per week can have high weekly revenue, while those with
high number of performances per week may receive revenue not as high).
This is the same for the relationship between “number of performances in
the week” and “average ticket price”.

In the next part we focus on factors that affect average ticket price.

### Seat Capacity and Average Ticket Price:

Using the function geom_smooth, all points are joint together to form
smooth curves to demonstrate how “average ticket price” is affected by
“seat capacity”. From the graph, we can see that there is no
relationship between those two variables.

### Conclusion:

…

## Presentation

Our presentation can be found [here](presentation/presentation.html).

## Data

Hughes, E. & Mock, T. (2018, April 28), Broadway weekly grosses,
<https://github.com/rfordatascience/tidytuesday/blob/master/data/2020/2020-04-28>

See <http://libraryguides.vu.edu.au/c.php?g=386501&p=4347840> for
guidance on proper citation for datasets. If you got your data off the
web, make sure to note the retrieval date.

## References

List any references here. You should, at a minimum, list your data
source.
