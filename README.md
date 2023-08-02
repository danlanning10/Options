# Options
BS model, greeks, sanction screening for Capula interview
**Santions.ipynb**
Please see below for the reasons why I made certain decisions within the Sanctions.ipynb script.

I assume that sanctions are only valid if BOTH the tickers and exhange codes match between the sanctions/tickers files. The first step is therefore to reformat the data where each element in the ticker/sanctions list have the 'TCKRS+Exchange Code' format.

The sanctions file has the format '{TCKRS} + {EC} + {Security Type}' with the 3 pieces of information separated by a space. Line item 24 is the exception to this, 'OGZDDAF Equity'. This emant I couldnt use a space as a delimiter.

The solution was to remove the last 7 characters ' Equity' from each of these string elements. While this addresses the issue of no space being present between the exchange code and ticker, a different character length security type or no space between the code/security type would create an issue.

Csv file is then written where if there is a match, the tickers + exchange code is written to a csv file along with the regional sanction information from the bulk_sanctions file. If no match is fouind, each of these regional sanctions is populated with 'N'.



