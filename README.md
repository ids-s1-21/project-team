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

Our main research topic is: How to maximize profits for Broadway
theaters?

The dataset used comes from Playbill, which is a US magazine for
theatre-goers. The information of weekly box office grosses comes from
‘The Broadway League’, an association for Broadway theatres.

There are 47,524 cases of shows that are being played in the theatres at
different times in a year. There are 14 variables. Some of the more
important ones which we will be using in our analysis include the
following:

1.  `show`
2.  `theatre`
3.  `weekly_gross`
4.  `avg_ticket_price`
5.  `seats_sold`
6.  `seat_capacity`
7.  `pct_capacity`
8.  `performances`

<!-- -->

    ## Rows: 47524 Columns: 14

    ## ── Column specification ────────────────────────────────────────────────────────
    ## Delimiter: ","
    ## chr   (2): show, theatre
    ## dbl  (11): week_number, weekly_gross_overall, weekly_gross, potential_gross,...
    ## date  (1): week_ending

    ## 
    ## ℹ Use `spec()` to retrieve the full column specification for this data.
    ## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.

In this dataset, we have variables such as “average ticket price”,
“percentage of seat capacity sold”, and “number of performances in the
week”, which may affect weekly gross revenue. Further, we think the
variables “seat capacity” and “number of weeks being run” may have an
influence on “average ticket price”. Therefore, our research questions
are:

1.What are the factors that affect weekly gross revenue?

2.What are the factors that affect average ticket price of a show, and
how average ticket price influence the weekly gross revenue earned?

Our hypotheses are:

1.Higher “average ticket price”, “percentage seats capacity sold”, and
“number of performances in the week week” lead to higher “weekly gross
revenue.”

2.More specifically, higher “seat capacity” and “number of weeks being
run” can lead to higher “average ticket price”.

We plan to create various visualizations with models and apply
inferential statistics to find out the relationship between those
variables.

Since “percentage of seat capacity sold” may be a factor affecting
weekly gross and differs depend on total seats in theater, we first draw
a density graph to see how “seat capacity” is distributed. As the graph
reveals, the seat capacity varies greatly in different theaters. The
size of a theatre might be a factor which influences the relationship
between variables. Therefore, we mutate the theatres into “large”,
“medium”, and “small” based on theatre size and do visualizations to
further explore the relationship.

First we look at factors that affect weekly gross revenue.

### Average Ticket Price and Weekly Gross Revenue:

Model, Economic analysis (reason behind that)

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

### Number of Weeks Being Run and Average Ticket Price:

…

### Seat Capacity and Average Ticket Price:

Using the function geom_smooth, all points are joint together to form
smooth curves to demonstrate how “average ticket price” is affected by
“seat capacity”. From the graph, we can see that there is no
relationship between those two variables.

### Conclusion:

…

## Presentation

#why mutate

grosses%>% ggplot(aes(x=seats_in_theatre))+ geom_density()

#mutate

grosses_2\<-grosses%>% mutate(theatre_size=(case_when(
seats_in_theatre\<750 \~“small”, seats_in_theatre\<1300 &
seats_in_theatre>750 \~“median”, seats_in_theatre>1299 \~“large”) ) )

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
