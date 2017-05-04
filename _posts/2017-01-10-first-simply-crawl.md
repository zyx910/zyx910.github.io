---
layout: post
title: "first simply crawl"
date: 2017-01-10 22:17
categories: python


---

```python
def get_page(url):
    try:
        import urrlib
        return urllib.urlopen(url).read()
    except:
        return ""

 #获得URL和下一个URL的位置   
def next_target(page):
    start_pos = page.find('<a href = ')
    if start_pos == -1:
        return None, 0
    url_pos = page.find('"', start_pos)
    end_pos = page.find('"', start_pos+1)  
    url = page[url_pos+1 : end_pos]
    return url, end_pos

#取得一个页面中所有的Link
def get_all_links(page):
    links = []
    while True:
        url,next_pos = next_target(page)
        if url:
            links.append(url)
            page = page[next_pos :]
        else:
            break
    return links
            
#比较两个list，如果q中的元素不在p中，将这个元素添加到p中
def union(p, q):
    for i in q:
        if i not in p:
            p.append[i]

#将页面所有的Link输出
def crawl_seed(seed):
    tocrawl = [seed]
    crawled =[]
    while tocrwal:
        page = tocrawl.pop()
        if page not in crawled:
        	union(tocrawl, get_all_links(get_page(page)))
        	crawled.append(page)
     return crawled
        
```



