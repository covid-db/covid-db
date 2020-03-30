# covid-db

## Relationally Normalized COVID-19 Data in CSV Format

This project scrapes data from the [Johns Hopkins COVID-19
dataset](https://github.com/CSSEGISandData/COVID-19) and transforms it into
normalized tables that are more suitable for SQL querying.

This is a good start but we can do a lot better.  The Johns Hopkins dataset
[uses the CDC for its U.S.
data](https://github.com/CSSEGISandData/COVID-19/blame/master/README.md#L30)
and does not include state level data.  The CDC gets its data from individual
state websites.  These sources are listed
[here](https://www.cdc.gov/coronavirus/2019-ncov/index.html) in the collapsible
States table just below the Reported Cases map.  We would like to start a
community effort to compile this data from the most granular sources possible
to make it easier to do higher fidelity analysis of the data.

You don't have to write an automated scraper to help.  Simply searching for
the lowest level sources and listing them here would be a great first step.
Manually copying that data from those sources into this database on a daily
basis would be an even better next step.  Once this information has been
tracked down, it will be easier for people with coding skills to automate the
process.  Let's crowd-source a really high quality clean dataset to help
analyze and fight the COVID-19 virus!

This doesn't have to be limited to the United States.  The same strategy can
work for anywhere in the world where low-level data is available.

## Data Currently Available

### Johns Hopkins Data

* [places.csv](tables/places.csv)
* [reports.csv](tables/reports.csv)

### US State Data

Data is currently being scraped for the following states:

* [New York](tables/us-states/newyork.csv)
* [Utah](tables/us-states/utah.csv)

## Scrapers

Scrapers for this data are available here:

https://github.com/covid-db/covid-scrapers

## Future Work

The exiting categories of `confirmed`, `deaths`, and `recovered` have
significant uncertainties associated with them.  A better next step would be
to get more granular data something like the following numbers of cases:

* Tests administered
* Positive tests (confirmed cases)
* Cases admitted to hospitals
* Cases admitted to ICU
* Deaths
* Recoveries

Getting this data would give us a much more accurate picture of what is
happening, but this will take a lot of effort.  The first step is to establish
a clearly defined format that is maximally usable and make it easy to add data
in this format.

Of course the ideal situation would be to have individual case data
(anonymized) with things like gender, age, and more accurate timestamps of
disease progression. We have the tools to enable this.  It's mostly a matter
of being organized and coordinated.
