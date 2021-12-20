### Flask web application
> Github doesn't support flask. Check the result & code on : https://replit.com/@BoyoonChoi/SuperScrapper#main.py

* Takes an input, and search for remote job opening on three websites: 
    * 1. Stackoverflow. f"https://stackoverflow.com/jobs?r=true&q={word}"
    * 2. WeWorkRemotely. "https://weworkremotely.com"
    * 3. RemoteOK. f"https://remoteok.io/remote-dev+{word}-jobs"

![스크린샷 2021-12-20 23 22 03](https://user-images.githubusercontent.com/22133824/146840710-02669080-9f2b-4ec9-bd87-2af59bd5eb87.png)

### Python web scraper
> we scrape Python job listings on both <b>Indeed</b> and <b>StackOverflow</b>, mainly using ```BeautifulSoup```

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

### AlbaHeaven_webscraper
> we scrape job listing from each company, and save them in individual csv files.

<img width="1253" alt="스크린샷 2021-12-13 17 19 18" src="https://user-images.githubusercontent.com/22133824/145849131-a4bff340-385a-48e5-a9bd-0acb73f86014.png">
<img width="621" alt="스크린샷 2021-12-13 17 22 49" src="https://user-images.githubusercontent.com/22133824/145849571-b686c506-2f7a-4fe9-a9ea-be6263abe997.png">

