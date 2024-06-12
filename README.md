# Privacy preserving database search

We have submitted a proposal to Catalyst to help fund this work. Please, consider to vote for [proposal](https://cardano.ideascale.com/c/idea/122016).

## Summary

This work builds on probabilistic filters such as Bloom filters([Bl70](#bl70)) which are very well studied and show interesting features. By their definition they allow to assess whether an element is part of a set of elements which can be large. This is executed by assigning elements to bins based on the hashing of their data. If this is done for all the elements in the set, then the test whether an element is part of the set becomes a condition (|bin| > 0) on the count of elements in the bin to which the query element is mapped. 

In cases of databases we think of the set as a table with lots of data rows arranged in columns, and the element as a datum in one of those columns (i.e. a key). Then, the test whether the element is part of the set becomes a query with the datum in the respective column of that database table. Usually such queries are powered by index lookups for performance reasons. 

A problem with the standard database querying approach is that the submitter of the query needs to reveal the query to the service. In situations where one wants to run such a query through a third-party API service, everyone along the pipeline learns about the query. In some situations this might not be desirable.

This is where probabilistic filters come to help. The submitter of the query encodes the query as a probabilistic filter, then submits it to the server which applies the filter in a similarity search over the database table and returns the matched results. From Bloom's paper we know that the true results to our query are part of the returned results. So the client only needs to post-filter with the original query. Of course, there is a price to pay for this. We thus evaluate in an experiment the overhead of using probabilistic filters compared to using optimised database indexing.

![Overview schema about searching a database with privacy preserved](img/overview.png)


## Methodology

> tbd

## Results

> tbd

## Discussion

> tbd

## Bibliography

#### Bl70
> Bloom, B. H. Space/time trade-offs in hash coding with allowable errors. Commun. ACM 13, 422-426 (1970). URL https://doi.org/10.1145/362686.362692

