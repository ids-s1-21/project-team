Maximising Profits for Broadway Theatres
================
team

## Summary

Write-up of your project and findings go here. Think of this as the text
of your presentation. The length should be roughly 5 minutes when read
out loud. Although pacing varies, a 5-minute speech is roughly 750
words. To use the word count addin, select the text you want to count
the words of (probably this is the Summary section of this document, go
to Addins, and select the `Word count` addin). This addin counts words
using two different algorithms, but the results should be similar and as
long as you’re in the ballpark of 750 words, you’re good! The addin will
ignore code chunks and only count the words in prose.

You can also load your data here and present any analysis results /
plots, but I strongly urge you to keep that to a minimum (maybe only the
most important graphic, if you have one you can choose). And make sure
to hide your code with `echo = FALSE` unless the point you are trying to
make is about the code itself. Your results with proper output and
graphics go in your presentation, this space is for a brief summary of
your project.

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

    ## Rows: 47,524
    ## Columns: 14
    ## $ week_ending          <date> 1985-06-09, 1985-06-09, 1985-06-09, 1985-06-09, …
    ## $ week_number          <dbl> 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1…
    ## $ weekly_gross_overall <dbl> 3915937, 3915937, 3915937, 3915937, 3915937, 3915…
    ## $ show                 <chr> "42nd Street", "A Chorus Line", "Aren't We All?",…
    ## $ theatre              <chr> "St. James Theatre", "Sam S. Shubert Theatre", "B…
    ## $ weekly_gross         <dbl> 282368, 222584, 249272, 95688, 61059, 255386, 306…
    ## $ potential_gross      <dbl> NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, N…
    ## $ avg_ticket_price     <dbl> 30.42, 27.25, 33.75, 20.87, 20.78, 31.96, 28.33, …
    ## $ top_ticket_price     <dbl> NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, N…
    ## $ seats_sold           <dbl> 9281, 8167, 7386, 4586, 2938, 7992, 10831, 5672, …
    ## $ seats_in_theatre     <dbl> 1655, 1472, 1088, 682, 684, 1018, 1336, 1368, 148…
    ## $ pct_capacity         <dbl> 0.7010, 0.6935, 0.8486, 0.8405, 0.5369, 0.9813, 1…
    ## $ performances         <dbl> 8, 8, 8, 8, 8, 8, 8, 8, 8, 8, 8, 8, 8, 9, 0, 8, 8…
    ## $ previews             <dbl> 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 8, 0, 0…

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
