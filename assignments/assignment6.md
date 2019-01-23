# Your task

## Write a Web Crawler

With the help of BeautifulSoup, write a web crawler that collects links from websites recursively.

That is, when pointed to a URL with an HTML page your crawler collects all URLs starting with an `http` and , which are contained in a link tag. For example, when pointing your crawler to http://www.pyregex.com/, it will scrape the following ten URLs:

  * http://www.pythex.org
  * http://docs.python.org/library/re.html
  * http://www.github.com/rscarvalho
  * http://www.github.com/rscarvalho
  * http://rubular.com
  * http://www.gnu.org/licenses/gpl-2.0.html#SEC1
  * https://www.heroku.com
  * https://travis-ci.org/rscarvalho/pyregex
  * http://www.python.org
  * https://github.com/rscarvalho/pyregex

All those links are considered to be of depth one, i.e., on step from the URL of origin.

Since your web crawler is recursive, it is crawling the linked websites again and finds:

  * https://github.com/tartley/python-regex-cheatsheet/
  * http://rubular.comhttps://docs.python.org/2/library/re.html
  * http://gabi.is
  * http://flask.pocoo.org/

as outgoing links from http://www.pythex.org, 

  * https://www.python.org/
  * https://www.python.org/psf/donations/
  * http://sphinx.pocoo.org/

as outgoing links from http://docs.python.org/library/re.html, etc.


Write you web crawler so that it scrapes all outgoing links from a website in a certain depth. That is, depth 10 means that you scrape until you are ten links deep away from the original website. Make sure that you handle circular appropriately.

Save your scraped links in a dictionary, which you serialize into a Python module for later reuse.


## Visualize the Scraped Links

Make use of the `networkx` package, see https://networkx.github.io and https://networkx.github.io/documentation/stable/ to visualize the graph of links. You want to create a `DiGraph` (a directed graph), see https://networkx.github.io/documentation/stable/tutorial.html#directed-graphs where edges go from website of origin to the linked website. Create a visalization of the link structure with a circular layout, see https://networkx.github.io/documentation/stable/tutorial.html#drawing-graphs
