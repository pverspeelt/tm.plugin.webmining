# tm.plugin.webmining
[![Build Status](https://travis-ci.org/mannau/tm.plugin.webmining.svg?branch=master)](https://travis-ci.org/mannau/tm.plugin.webmining) [![codecov.io](http://codecov.io/github/mannau/tm.plugin.webmining/coverage.svg?branch=master)](http://codecov.io/github/mannau/tm.plugin.webmining?branch=master) [![License](http://img.shields.io/badge/license-GPL%20%28%3E=%203%29-blue.svg?style=flat)](http://www.gnu.org/licenses/gpl-3.0.html)

**tm.plugin.webmining** is an R-package which facilitates text retrieval from feed formats like XML (RSS, ATOM) and JSON. Also direct retrieval from HTML is supported. As most (news) feeds only incorporate small fractions of the original text **tm.plugin.webmining** even extracts the text from the original text source.

## Install
To install the [latest version from CRAN](http://cran.r-project.org/web/packages/tm.plugin.webmining/index.html) simply 
```python
install.packages("tm.plugin.webmining")
```

Using the **devtools** package you can easily install the latest development version of **tm.plugin.webmining** from github with

```python
library(devtools)
install_github("mannau/tm.plugin.webmining")
```

Windows users need to use the following command to install from github:

```python
library(devtools)
install_github("mannau/boilerpipeR", args = "--no-multiarch")
```

## Usage
The next snippet shows how to download and extract the main text from all supported sources as WebCorpus objects including a rich set of metadata like *Author*, *DateTimeStamp* or *Source*:

```python
library(tm.plugin.webmining)
googlefinance <- WebCorpus(GoogleFinanceSource("NASDAQ:MSFT"))
googlenews <- WebCorpus(GoogleNewsSource("Microsoft"))
nytimes <- WebCorpus(NYTimesSource("Microsoft", appid = "<nytimes_appid>"))
reutersnews <- WebCorpus(ReutersNewsSource("businessNews"))
#twitter <- WebCorpus(TwitterSource("Microsoft")) -> not supported yet
yahoofinance <- WebCorpus(YahooFinanceSource("MSFT"))
yahooinplay <- WebCorpus(YahooInplaySource())
yahoonews <- WebCorpus(YahooNewsSource("Microsoft"))
liberation <- WebCorpus(LiberationSource("latest"))
```

## License
**tm.plugin.webmining** is released under the [GNU General Public License Version 3](http://www.gnu.org/copyleft/gpl.html)
