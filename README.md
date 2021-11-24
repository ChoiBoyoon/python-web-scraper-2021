### Python web scraper
> we scrapes job listings on both indeed and StackOverflow, mainly using ```BeautifulSoup```

code example below
```Python
def extract_job(html):
    title = html.find("span", title=True).string
    company = html.find("span",{"class":"companyName"}).string
    location = html.select_one("pre>div").text
    job_id=html['data-jk']
    return {
        'title':title, 
        'company':company, 
        'location':location, 
        'link':f"https://www.indeed.com/viewjob?jk={job_id}"}
```
