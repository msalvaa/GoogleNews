# GoogleNews

[![Build Status](https://travis-ci.com/Iceloof/GoogleNews.svg)](https://travis-ci.com/Iceloof/GoogleNews)
[![Coverage Status](https://coveralls.io/repos/github/Iceloof/GoogleNews/badge.svg)](https://coveralls.io/github/Iceloof/GoogleNews)
[![PyPI](https://img.shields.io/pypi/v/GoogleNews)](https://pypi.org/project/GoogleNews/)
[![PyPI - Downloads](https://img.shields.io/pypi/dm/GoogleNews)](https://pypistats.org/packages/googlenews)
![PyPI - Python Version](https://img.shields.io/pypi/pyversions/GoogleNews)
![PyPI - Wheel](https://img.shields.io/pypi/wheel/GoogleNews)
![GitHub contributors](https://img.shields.io/github/contributors/Iceloof/GoogleNews)
![GitHub issues](https://img.shields.io/github/issues-raw/Iceloof/GoogleNews)
![GitHub Action](https://github.com/Iceloof/GoogleNews/workflows/GitHub%20Action/badge.svg)
![GitHub](https://img.shields.io/github/license/Iceloof/GoogleNews)

## Install
```
pip install GoogleNews
```
or
```
pip install --upgrade GoogleNews
```
## Usage
- Initializing
```
from GoogleNews import GoogleNews
googlenews = GoogleNews()
```
- Optional choose language
```
googlenews = GoogleNews(lang='en')
```
- Optional choose period (period and custom day range should not set together)
```
googlenews = GoogleNews(period='7d')
```
- Optional choose custom day range (mm/dd/yyyy)
```
googlenews = GoogleNews(start='02/01/2020',end='02/28/2020')
```
- Optional set encode
```
googlenews = GoogleNews(encode='utf-8')
```
or
```
googlenews.set_lang('en')
googlenews.set_period('7d')
googlenews.set_time_range('02/01/2020','02/28/2020')
googlenews.set_encode('utf-8')
```
- **news.google.com** search sample
```
googlenews.get_news('APPLE')
```
- **google.com** section news search sample
```
googlenews.search('APPLE')
```

Default return first page result. To get other page of search results:

```
googlenews.getpage(2)
```
- Get results will return the list, `[{'title': '...', 'media': '...', 'date': '...', 'datetime': '...', 'desc': '...', 'link': '...', 'img': '...'}]`
```
googlenews.results()
```
if `googlenews.result(sort=True)` the tool will try to order the results in cronologically reversed order
- Get texts will return the list of news titles
```
googlenews.get_texts()
```
- Get links returns the list of news links
```
googlenews.get_links()
```
- Clear result list before doing another search with the same object
```
googlenews.clear()
```
## Issue
Image is not working in the latest version, it can only return default google loading gif
