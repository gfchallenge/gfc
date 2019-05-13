# Example Notebooks for Working with External Data Sources

In this folder we provide some Jupyter iPython notebooks with example Python code for accessing external data sources that may be relevant to some of the Challenge IFPs.  Please note that we make no guarantee that these sources will have predictive power for any of the IFPs.  However, they may provide a launching point for Solvers to access external data relevant to the IFPs.  In some cases these sources will be the resolution criteria for the IFPs.

## Caveats

- Solvers are responsible for complying with all terms of use for the data sources they access.  All code in this document is provided using the [CC0 1.0 Universal (CC0 1.0) Public Domain Dedication](https://creativecommons.org/publicdomain/zero/1.0/).  The examples have been tested using Python 3 but have not been tested under Python 2.
- While the code in these notebooks worked on the day the notebooks were developed there is no guarantee that they are robust to changes in data provider APIs or data formats.
- We do not claim that these sources will have predictive power for any IFPs.
- We do not claim that this is an exhaustive set of data sources.  These notebooks do not cover every resolution data source.

## The Notebooks
- [Quandl](Quandl.ipynb) for financial indicators, including commodity pricing.
- [STOXX](STOXX.ipynb) for financial indicators, including the VSTOXX index.
- [eurostat](eurostat.ipynb) EU statistical data such as unemployment.
- [EIA](EIA.ipynb) US Energy Information Administration data such as energy production and consumption world-wide.
- [ACLED](ACLED.ipynb) Armed Conflict Location & Event Data Project ACLED, acleddata.com.
- [USGS Earthquakes](USGS%20Earthquakes.ipynb) USGS earthquake information world-wide.
- [Mexican Crime Data](Mexican%20Crime%20Statistics.ipynb) Data from the Goverment of Mexico on crime.
- [Google Trends](Google%20Trends.ipynb) Google Trends search frequency by keyword.

## Technical Details
The local development fork for this project looked like this:

- data
- doc
- src
-- notebooks
--- External Data Sources
- src -- resources

Each notebook begins with a preamble that directs plotting inside the notebook, loads libraries common to the notebooks, and loads file paths based on the above setup.  It also loads a JSON file called `auth.json` into a dict named `api_key_dict`.  This is one suggested method for keeping all of your API keys for the several sources in one place.  Here's an example of what `auth.json` can look like:
```
{
    "gfc_staging": <STAGING_API_KEY>,
    "gfc_production": <PRODUCTION_API_KEY>,
    "quandl": <QUANDL_KEY>,
    "eia": <EIA_KEY>,
    ...
}
```