```python
pip install beautifulsoup4

```

    Requirement already satisfied: beautifulsoup4 in c:\users\user\anaconda3\lib\site-packages (4.11.1)
    Requirement already satisfied: soupsieve>1.2 in c:\users\user\anaconda3\lib\site-packages (from beautifulsoup4) (2.3.1)
    Note: you may need to restart the kernel to use updated packages.
    


```python
pip install lxml
```

    Requirement already satisfied: lxml in c:\users\user\anaconda3\lib\site-packages (4.8.0)
    Note: you may need to restart the kernel to use updated packages.
    


```python
pip install requests
```

    Requirement already satisfied: requests in c:\users\user\anaconda3\lib\site-packages (2.27.1)
    Requirement already satisfied: charset-normalizer~=2.0.0 in c:\users\user\anaconda3\lib\site-packages (from requests) (2.0.4)
    Requirement already satisfied: urllib3<1.27,>=1.21.1 in c:\users\user\anaconda3\lib\site-packages (from requests) (1.26.9)
    Requirement already satisfied: idna<4,>=2.5 in c:\users\user\anaconda3\lib\site-packages (from requests) (3.3)
    Requirement already satisfied: certifi>=2017.4.17 in c:\users\user\anaconda3\lib\site-packages (from requests) (2021.10.8)
    Note: you may need to restart the kernel to use updated packages.
    


```python
from bs4 import BeautifulSoup
import requests

html_text= requests.get('https://www.timesjobs.com/candidate/job-search.html?searchType=personalizedSearch&from=submit&txtKeywords=Python&txtLocation=').text

Soup = BeautifulSoup(html_text,'lxml')

Job = Soup.find('li', class_='clearfix job-bx wht-shd-bx')

#print(Job)

# dot replace('','') used in the line of code below is used to removed the white space that should have come up with out output

Company_name = Job.find('h3', class_ = 'joblist-comp-name').text.replace(' ',' ')
print(Company_name)


 
```

    
        Surya Informatics Solutions Pvt. Ltd.
        
        
    


```python
Soup = BeautifulSoup(html_text,'lxml')

Job = Soup.find('li', class_='clearfix job-bx wht-shd-bx').text

print(Job) 
```

    
    
    
    
    
    
    Python 
    
        Surya Informatics Solutions Pvt. Ltd.
        
        
    
    
    card_travel0 - 3 yrs
    
    location_on
    Chennai
    
    
    
    
    Job Description:
    POSITION: Python Developer ELIGIBILITY: FRESHERS Your RoleUnderstand requirements and participate in project road map discussions in order to design ,  estimate ,  and deliver... More Details
    
    
    KeySkills:
    
    python  ,  web technologies  ,  linux  ,  mobile  ,  mysql  ,  angularjs  ,  javascript
            
           
    
    
    
    
    
    Apply
    
    
    
    
    Posted few days ago
    
    
    
    
    
    


```python
from bs4 import BeautifulSoup
import requests

html_text= requests.get('https://www.timesjobs.com/candidate/job-search.html?searchType=personalizedSearch&from=submit&txtKeywords=Python&txtLocation=').text

Soup = BeautifulSoup(html_text,'lxml')

Jobs = Soup.find_all('li', class_='clearfix job-bx wht-shd-bx')

#print(Job)

# dot replace('','') used in the line of code below is used to removed the white space that should have come up with out output
for Job in Jobs:
    Company_name = Job.find('h3', class_ = 'joblist-comp-name').text.replace(' ',' ')

    Skills_needed = Job.find('span',class_ = 'srp-skills').text.replace(' ', '')

#print(Skills_needed)

#To get the needed information from this particular job at a go, we will use the print statement below

    Published_Date = Job.find('span', class_ = 'sim-posted').text
    print(f'''Company Name: {Company_name} Requirred Skills: {Skills_needed} Published Time: {Published_Date}''')
    
    print('')
#print(Published_Date)

```

    Company Name: 
        Surya Informatics Solutions Pvt. Ltd.
        
         Requirred Skills: 
    python,webtechnologies,linux,mobile,mysql,angularjs,javascript
    
     Published Time: 
    Posted few days ago
    
    
    Company Name: 
        Ivan Infotech Pvt. Ltd.
        
         Requirred Skills: 
    
    rest,python,security,debugging
    
     Published Time: 
    Posted few days ago
    
    
    Company Name: 
        east india securities ltd.
        
         Requirred Skills: 
    python,hadoop,machinelearning
    
     Published Time: 
    Posted few days ago
    
    
    Company Name: 
        art technology and software india pvt ltd
        
         Requirred Skills: 
    
    rest,python,database,django,api
    
     Published Time: 
    Posted 6 days ago
    
    
    Company Name: 
        TandA HR Solutions
        
         Requirred Skills: 
    python,git,django,GITHub
    
     Published Time: 
    Posted 6 days ago
    
    
    Company Name: 
        TandA HR Solutions
        
         Requirred Skills: 
    Python,Django,Flask,GITHub
    
     Published Time: 
    Posted 6 days ago
    
    
    Company Name: 
        sjain ventures
        
         Requirred Skills: 
    python,webdeveloper,webservices
    
     Published Time: 
    Posted 6 days ago
    
    
    Company Name: 
        TandA HR Solutions
        
         Requirred Skills: 
    Python,Django,Flask,unittesting
    
     Published Time: 
    Posted few days ago
    
    
    Company Name: 
        INFINITY GROUP
        
         Requirred Skills: 
    python,css,django,html,bootstrap
    
     Published Time: 
    Posted few days ago
    
    
    Company Name: 
        DREAMAJAX TECHNOLOGIES
        
         Requirred Skills: 
    python,django,api,sql,nosql
    
     Published Time: 
    Posted few days ago
    
    
    Company Name: 
        pofi technologies pvt ltd.
        
         Requirred Skills: 
    python,django,html5,oops,javascript
    
     Published Time: 
    Posted 3 days ago
    
    
    Company Name: 
        day1 technologies
        
         Requirred Skills: 
    
    rest,python,django,git,postgresql,sql,docker
    
     Published Time: 
    Posted 3 days ago
    
    
    Company Name: 
        3RI Technologies Pvt Ltd
        
         Requirred Skills: 
    python,django,html5,javascript
    
     Published Time: 
    Posted few days ago
    
    
    Company Name: 
        TECHNOPARK TRIVANDRUM
        
         Requirred Skills: 
    python,softwaredesign,debugging,softwareengineering
    
     Published Time: 
    Posted 4 days ago
    
    
    Company Name: 
        xonier technologies pvt ltd
        
         Requirred Skills: 
    python,django,testingtools,debugging,storage
    
     Published Time: 
    Posted 6 days ago
    
    
    Company Name: 
        CONNECTING 2 WORK
        
         Requirred Skills: 
    python,storage,django,testingtools,debugging
    
     Published Time: 
    Posted 6 days ago
    
    
    Company Name: 
        TandA HR Solutions
        
         Requirred Skills: 
    
    rest,python,github,nosql,sql,django,api,mongodb,soap
    
     Published Time: 
    Posted 2 days ago
    
    
    Company Name: 
        InnOvator Web Solutions Pvt.Ltd.
        
         Requirred Skills: 
    
    rest,python,django,webdeveloper,mysql,api
    
     Published Time: 
    Posted few days ago
    
    
    Company Name: 
        pearl global solutions
        
         Requirred Skills: 
    python,database,django,teamplayer,sql
    
     Published Time: 
    Posted few days ago
    
    
    Company Name: 
        creative thoughts informatics indore
        
         Requirred Skills: 
    python,django,restapi,html5,javascript
    
     Published Time: 
    Posted few days ago
    
    
    Company Name: 
        DealsCorner
        
         Requirred Skills: 
    python,css,oops,linux,debugging,html,javascript
    
     Published Time: 
    Posted few days ago
    
    
    Company Name: 
        AxisTechnolabs
        
         Requirred Skills: 
    python,django,itskills,html5,api,jquery
    
     Published Time: 
    Posted few days ago
    
    
    Company Name: 
        CIGNEX Datamatics Technologies Pvt Ltd
        
         Requirred Skills: 
    python,sql,django,postgresql,writtencommunication,api,angularjs
    
     Published Time: 
    Posted 3 days ago
    
    
    Company Name: 
        Xpetize Technology Solutions Private Limited
        
         Requirred Skills: 
    
    rest,python,rdbms,nosql,postgresql,devops,socialservices,shellscripting,mysql,mongodb
    
     Published Time: 
    Posted 2 days ago
    
    
    Company Name: 
        Sourcedesk Global Private Limited
        
         Requirred Skills: 
    
    html5,storage,python,javascript,django,infrastructure
    
     Published Time: 
    Posted few days ago
    
    
    


```python
#To find all jobs published a 'few days ago' on the website I used the code below

from bs4 import BeautifulSoup
import requests

html_text= requests.get('https://www.timesjobs.com/candidate/job-search.html?searchType=personalizedSearch&from=submit&txtKeywords=Python&txtLocation=').text

Soup = BeautifulSoup(html_text,'lxml')

Jobs = Soup.find_all('li', class_='clearfix job-bx wht-shd-bx')

#print(Job)

# dot replace('','') used in the line of code below is used to removed the white space that should have come up with out output
for Job in Jobs:
    
    Published_Date = Job.find('span', class_ = 'sim-posted').text
    
    if 'few' in Published_Date:
    
        Company_name = Job.find('h3', class_ = 'joblist-comp-name').text.replace(' ',' ')

        Skills_needed = Job.find('span',class_ = 'srp-skills').text.replace(' ', '')

        print(f'''Company Name: {Company_name} Requirred Skills: {Skills_needed} Published Time: {Published_Date}''')

        print('')

#print(Skills_needed)

#To get the needed information from this particular job at a go, we will use the print statement below

    
#print(Published_Date)
```

    Company Name: 
        Surya Informatics Solutions Pvt. Ltd.
        
         Requirred Skills: 
    python,webtechnologies,linux,mobile,mysql,angularjs,javascript
    
     Published Time: 
    Posted few days ago
    
    
    Company Name: 
        east india securities ltd.
        
         Requirred Skills: 
    python,hadoop,machinelearning
    
     Published Time: 
    Posted few days ago
    
    
    Company Name: 
        TandA HR Solutions
        
         Requirred Skills: 
    python,git,django,GITHub
    
     Published Time: 
    Posted few days ago
    
    
    Company Name: 
        sjain ventures
        
         Requirred Skills: 
    python,webdeveloper,webservices
    
     Published Time: 
    Posted few days ago
    
    
    Company Name: 
        art technology and software india pvt ltd
        
         Requirred Skills: 
    
    rest,python,database,django,api
    
     Published Time: 
    Posted few days ago
    
    
    Company Name: 
        TandA HR Solutions
        
         Requirred Skills: 
    Python,Django,Flask,GITHub
    
     Published Time: 
    Posted few days ago
    
    
    Company Name: 
        3RI Technologies Pvt Ltd
        
         Requirred Skills: 
    python,django,html5,javascript
    
     Published Time: 
    Posted few days ago
    
    
    Company Name: 
        DREAMAJAX TECHNOLOGIES
        
         Requirred Skills: 
    python,django,api,sql,nosql
    
     Published Time: 
    Posted few days ago
    
    
    Company Name: 
        INFINITY GROUP
        
         Requirred Skills: 
    python,css,django,html,bootstrap
    
     Published Time: 
    Posted few days ago
    
    
    Company Name: 
        xonier technologies pvt ltd
        
         Requirred Skills: 
    python,django,testingtools,debugging,storage
    
     Published Time: 
    Posted few days ago
    
    
    Company Name: 
        CONNECTING 2 WORK
        
         Requirred Skills: 
    python,storage,django,testingtools,debugging
    
     Published Time: 
    Posted few days ago
    
    
    Company Name: 
        Sourcedesk Global Private Limited
        
         Requirred Skills: 
    
    html5,storage,python,javascript,django,infrastructure
    
     Published Time: 
    Posted few days ago
    
    
    Company Name: 
        TandA HR Solutions
        
         Requirred Skills: 
    python,cloudservices,postgresql,mysql,machinelearning
    
     Published Time: 
    Posted few days ago
    
    
    Company Name: 
        InnOvator Web Solutions Pvt.Ltd.
        
         Requirred Skills: 
    
    rest,python,django,webdeveloper,mysql,api
    
     Published Time: 
    Posted few days ago
    
    
    Company Name: 
        pearl global solutions
        
         Requirred Skills: 
    python,database,django,teamplayer,sql
    
     Published Time: 
    Posted few days ago
    
    
    Company Name: 
        creative thoughts informatics indore
        
         Requirred Skills: 
    python,django,restapi,html5,javascript
    
     Published Time: 
    Posted few days ago
    
    
    Company Name: 
        DealsCorner
        
         Requirred Skills: 
    python,css,oops,linux,debugging,html,javascript
    
     Published Time: 
    Posted few days ago
    
    
    Company Name: 
        AxisTechnolabs
        
         Requirred Skills: 
    python,django,itskills,html5,api,jquery
    
     Published Time: 
    Posted few days ago
    
    
    


```python
#To get rid of the spcaes in our output, I uses the line of code below(Stripe)

from bs4 import BeautifulSoup
import requests

html_text= requests.get('https://www.timesjobs.com/candidate/job-search.html?searchType=personalizedSearch&from=submit&txtKeywords=Python&txtLocation=').text

Soup = BeautifulSoup(html_text,'lxml')

Jobs = Soup.find_all('li', class_='clearfix job-bx wht-shd-bx')

#print(Job)

# dot replace('','') used in the line of code below is used to removed the white space that should have come up with out output
for Job in Jobs:
    
    Published_Date = Job.find('span', class_ = 'sim-posted').text
    
    if 'few' in Published_Date:
    
        Company_name = Job.find('h3', class_ = 'joblist-comp-name').text.replace(' ',' ')

        Skills_needed = Job.find('span',class_ = 'srp-skills').text.replace(' ', '')

        print(f'''Company Name: {Company_name}''') 
        
        print(f'''Requirred Skills: {Skills_needed}''') 
        

        print('')

```

    Company Name: 
        Surya Informatics Solutions Pvt. Ltd.
        
        
    Requirred Skills: 
    python,webtechnologies,linux,mobile,mysql,angularjs,javascript
    
    
    
    Company Name: 
        east india securities ltd.
        
        
    Requirred Skills: 
    python,hadoop,machinelearning
    
    
    
    Company Name: 
        sjain ventures
        
        
    Requirred Skills: 
    python,webdeveloper,webservices
    
    
    
    Company Name: 
        art technology and software india pvt ltd
        
        
    Requirred Skills: 
    
    rest,python,database,django,api
    
    
    
    Company Name: 
        TandA HR Solutions
        
        
    Requirred Skills: 
    python,git,django,GITHub
    
    
    
    Company Name: 
        TandA HR Solutions
        
        
    Requirred Skills: 
    Python,Django,Flask,GITHub
    
    
    
    Company Name: 
        3RI Technologies Pvt Ltd
        
        
    Requirred Skills: 
    python,django,html5,javascript
    
    
    
    Company Name: 
        DREAMAJAX TECHNOLOGIES
        
        
    Requirred Skills: 
    python,django,api,sql,nosql
    
    
    
    Company Name: 
        INFINITY GROUP
        
        
    Requirred Skills: 
    python,css,django,html,bootstrap
    
    
    
    Company Name: 
        xonier technologies pvt ltd
        
        
    Requirred Skills: 
    python,django,testingtools,debugging,storage
    
    
    
    Company Name: 
        CONNECTING 2 WORK
        
        
    Requirred Skills: 
    python,storage,django,testingtools,debugging
    
    
    
    Company Name: 
        Sourcedesk Global Private Limited
        
        
    Requirred Skills: 
    
    html5,storage,python,javascript,django,infrastructure
    
    
    
    Company Name: 
        TandA HR Solutions
        
        
    Requirred Skills: 
    python,cloudservices,postgresql,mysql,machinelearning
    
    
    
    Company Name: 
        InnOvator Web Solutions Pvt.Ltd.
        
        
    Requirred Skills: 
    
    rest,python,django,webdeveloper,mysql,api
    
    
    
    Company Name: 
        creative thoughts informatics indore
        
        
    Requirred Skills: 
    python,django,restapi,html5,javascript
    
    
    
    Company Name: 
        DealsCorner
        
        
    Requirred Skills: 
    python,css,oops,linux,debugging,html,javascript
    
    
    
    Company Name: 
        pearl global solutions
        
        
    Requirred Skills: 
    python,database,django,teamplayer,sql
    
    
    
    Company Name: 
        AxisTechnolabs
        
        
    Requirred Skills: 
    python,django,itskills,html5,api,jquery
    
    
    
    


```python
#To scrap a direct link to all job posted on the site, I use the link below

from bs4 import BeautifulSoup
import requests

html_text= requests.get('https://www.timesjobs.com/candidate/job-search.html?searchType=personalizedSearch&from=submit&txtKeywords=Python&txtLocation=').text

Soup = BeautifulSoup(html_text,'lxml')

Jobs = Soup.find_all('li', class_='clearfix job-bx wht-shd-bx')

#print(Job)

# dot replace('','') used in the line of code below is used to removed the white space that should have come up with out output
for Job in Jobs:
    
    Published_Date = Job.find('span', class_ = 'sim-posted').text
    
    if 'few' in Published_Date:
    
        Company_name = Job.find('h3', class_ = 'joblist-comp-name').text.replace(' ',' ')

        Skills_needed = Job.find('span',class_ = 'srp-skills').text.replace(' ', '')
        
        Job_links = Job.header.h2.a['href']

        print(f'''Company Name: {Company_name}''') 
        
        print(f'''Requirred Skills: {Skills_needed}''') 
        
        print(f'Job Links: {Job_links}')
        

        print('')

```

    Company Name: 
        Surya Informatics Solutions Pvt. Ltd.
        
        
    Requirred Skills: 
    python,webtechnologies,linux,mobile,mysql,angularjs,javascript
    
    
    Job Links: https://www.timesjobs.com/job-detail/python-surya-informatics-solutions-pvt-ltd-chennai-0-to-3-yrs-jobid-UVlLes58wutzpSvf__PLUS__uAgZw==&source=srp
    
    Company Name: 
        east india securities ltd.
        
        
    Requirred Skills: 
    python,hadoop,machinelearning
    
    
    Job Links: https://www.timesjobs.com/job-detail/python-engineer-east-india-securities-ltd-kolkata-2-to-5-yrs-jobid-KEkE19WqPbFzpSvf__PLUS__uAgZw==&source=srp
    
    Company Name: 
        sjain ventures
        
        
    Requirred Skills: 
    python,webdeveloper,webservices
    
    
    Job Links: https://www.timesjobs.com/job-detail/python-intern-sjain-ventures-raipur-0-to-3-yrs-jobid-KmspiL9__SLASH__D9hzpSvf__PLUS__uAgZw==&source=srp
    
    Company Name: 
        art technology and software india pvt ltd
        
        
    Requirred Skills: 
    
    rest,python,database,django,api
    
    
    Job Links: https://www.timesjobs.com/job-detail/python-developer-art-technology-and-software-india-pvt-ltd-cochin-kochi-ernakulam-2-to-3-yrs-jobid-M26lxDEd__PLUS__qtzpSvf__PLUS__uAgZw==&source=srp
    
    Company Name: 
        TandA HR Solutions
        
        
    Requirred Skills: 
    python,git,django,GITHub
    
    
    Job Links: https://www.timesjobs.com/job-detail/python-developer-tanda-hr-solutions-gurgaon-chandigarh-4-to-6-yrs-jobid-RxlCUMDjB7dzpSvf__PLUS__uAgZw==&source=srp
    
    Company Name: 
        TandA HR Solutions
        
        
    Requirred Skills: 
    Python,Django,Flask,GITHub
    
    
    Job Links: https://www.timesjobs.com/job-detail/python-developer-tanda-hr-solutions-mohali-chandigarh-3-to-6-yrs-jobid-EAm60cv2FrxzpSvf__PLUS__uAgZw==&source=srp
    
    Company Name: 
        3RI Technologies Pvt Ltd
        
        
    Requirred Skills: 
    python,django,html5,javascript
    
    
    Job Links: https://www.timesjobs.com/job-detail/python-interns-3ri-technologies-pvt-ltd-pune-5-to-8-yrs-jobid-cfLZrmnuzxxzpSvf__PLUS__uAgZw==&source=srp
    
    Company Name: 
        DREAMAJAX TECHNOLOGIES
        
        
    Requirred Skills: 
    python,django,api,sql,nosql
    
    
    Job Links: https://www.timesjobs.com/job-detail/python-developer-dreamajax-technologies-bengaluru-bangalore-4-to-7-yrs-jobid-EWIVCDzRLKBzpSvf__PLUS__uAgZw==&source=srp
    
    Company Name: 
        INFINITY GROUP
        
        
    Requirred Skills: 
    python,css,django,html,bootstrap
    
    
    Job Links: https://www.timesjobs.com/job-detail/python-developer-infinity-group-noida-greater-noida-2-to-5-yrs-jobid-efOg3e9X__SLASH__D9zpSvf__PLUS__uAgZw==&source=srp
    
    Company Name: 
        xonier technologies pvt ltd
        
        
    Requirred Skills: 
    python,django,testingtools,debugging,storage
    
    
    Job Links: https://www.timesjobs.com/job-detail/python-developer-xonier-technologies-pvt-ltd-noida-greater-noida-2-to-5-yrs-jobid-VZ3nXzqL2FNzpSvf__PLUS__uAgZw==&source=srp
    
    Company Name: 
        CONNECTING 2 WORK
        
        
    Requirred Skills: 
    python,storage,django,testingtools,debugging
    
    
    Job Links: https://www.timesjobs.com/job-detail/python-developer-connecting-2-work-thiruvananthapuram-5-to-10-yrs-jobid-Tebue__SLASH__8iTzVzpSvf__PLUS__uAgZw==&source=srp
    
    Company Name: 
        Sourcedesk Global Private Limited
        
        
    Requirred Skills: 
    
    html5,storage,python,javascript,django,infrastructure
    
    
    Job Links: https://www.timesjobs.com/job-detail/python-developer-sourcedesk-global-private-limited-kolkata-3-to-15-yrs-jobid-A27Uf03p2IJzpSvf__PLUS__uAgZw==&source=srp
    
    Company Name: 
        TandA HR Solutions
        
        
    Requirred Skills: 
    python,cloudservices,postgresql,mysql,machinelearning
    
    
    Job Links: https://www.timesjobs.com/job-detail/python-developer-tanda-hr-solutions-mohali-5-to-8-yrs-jobid-mpGA2O7bJEVzpSvf__PLUS__uAgZw==&source=srp
    
    Company Name: 
        InnOvator Web Solutions Pvt.Ltd.
        
        
    Requirred Skills: 
    
    rest,python,django,webdeveloper,mysql,api
    
    
    Job Links: https://www.timesjobs.com/job-detail/python-developer-innovator-web-solutions-pvt-ltd-mumbai-5-to-8-yrs-jobid-OO__SLASH__Qb2Q7MfpzpSvf__PLUS__uAgZw==&source=srp
    
    Company Name: 
        creative thoughts informatics indore
        
        
    Requirred Skills: 
    python,django,restapi,html5,javascript
    
    
    Job Links: https://www.timesjobs.com/job-detail/python-developer-creative-thoughts-informatics-indore-indore-1-to-4-yrs-jobid-xtV5Tl3aEcVzpSvf__PLUS__uAgZw==&source=srp
    
    Company Name: 
        DealsCorner
        
        
    Requirred Skills: 
    python,css,oops,linux,debugging,html,javascript
    
    
    Job Links: https://www.timesjobs.com/job-detail/python-developer-dealscorner-ahmedabad-1-to-4-yrs-jobid-zwS7bOT__PLUS__nKxzpSvf__PLUS__uAgZw==&source=srp
    
    Company Name: 
        pearl global solutions
        
        
    Requirred Skills: 
    python,database,django,teamplayer,sql
    
    
    Job Links: https://www.timesjobs.com/job-detail/python-developer-pearl-global-solutions-cochin-kochi-ernakulam-4-to-7-yrs-jobid-dZD__SLASH__NDlCjpVzpSvf__PLUS__uAgZw==&source=srp
    
    Company Name: 
        AxisTechnolabs
        
        
    Requirred Skills: 
    python,django,itskills,html5,api,jquery
    
    
    Job Links: https://www.timesjobs.com/job-detail/python-odoo-axistechnolabs-ahmedabad-0-to-1-yrs-jobid-HzL8naalyxFzpSvf__PLUS__uAgZw==&source=srp
    
    


```python
#To scrap out skills that one is not familiar with in the jobs listed, the line of code below is used

from bs4 import BeautifulSoup
import requests

print('print some skill that you are not familiar with')

unfamiliar_skill = input('>')
print(f'filtering out {unfamiliar_skill}')

html_text= requests.get('https://www.timesjobs.com/candidate/job-search.html?searchType=personalizedSearch&from=submit&txtKeywords=Python&txtLocation=').text

Soup = BeautifulSoup(html_text,'lxml')

Jobs = Soup.find_all('li', class_='clearfix job-bx wht-shd-bx')

#print(Job)

# dot replace('','') used in the line of code below is used to removed the white space that should have come up with out output
for Job in Jobs:
    
    Published_Date = Job.find('span', class_ = 'sim-posted').text
    
    if 'few' in Published_Date:
    
        Company_name = Job.find('h3', class_ = 'joblist-comp-name').text.replace(' ',' ')

        Skills_needed = Job.find('span',class_ = 'srp-skills').text.replace(' ', '')
        
        
        if unfamiliar_skill not in Skills_needed:
            
        
            Job_links = Job.header.h2.a['href']

            print(f'''Company Name: {Company_name}''') 

            print(f'''Requirred Skills: {Skills_needed}''') 

            print(f'Job Links: {Job_links}')


            print('')

```

    print some skill that you are not familiar with
    >linux
    filtering out linux
    Company Name: 
        east india securities ltd.
        
        
    Requirred Skills: 
    python,hadoop,machinelearning
    
    
    Job Links: https://www.timesjobs.com/job-detail/python-engineer-east-india-securities-ltd-kolkata-2-to-5-yrs-jobid-KEkE19WqPbFzpSvf__PLUS__uAgZw==&source=srp
    
    Company Name: 
        sjain ventures
        
        
    Requirred Skills: 
    python,webdeveloper,webservices
    
    
    Job Links: https://www.timesjobs.com/job-detail/python-intern-sjain-ventures-raipur-0-to-3-yrs-jobid-KmspiL9__SLASH__D9hzpSvf__PLUS__uAgZw==&source=srp
    
    Company Name: 
        art technology and software india pvt ltd
        
        
    Requirred Skills: 
    
    rest,python,database,django,api
    
    
    Job Links: https://www.timesjobs.com/job-detail/python-developer-art-technology-and-software-india-pvt-ltd-cochin-kochi-ernakulam-2-to-3-yrs-jobid-M26lxDEd__PLUS__qtzpSvf__PLUS__uAgZw==&source=srp
    
    Company Name: 
        TandA HR Solutions
        
        
    Requirred Skills: 
    python,git,django,GITHub
    
    
    Job Links: https://www.timesjobs.com/job-detail/python-developer-tanda-hr-solutions-gurgaon-chandigarh-4-to-6-yrs-jobid-RxlCUMDjB7dzpSvf__PLUS__uAgZw==&source=srp
    
    Company Name: 
        TandA HR Solutions
        
        
    Requirred Skills: 
    Python,Django,Flask,GITHub
    
    
    Job Links: https://www.timesjobs.com/job-detail/python-developer-tanda-hr-solutions-mohali-chandigarh-3-to-6-yrs-jobid-EAm60cv2FrxzpSvf__PLUS__uAgZw==&source=srp
    
    Company Name: 
        3RI Technologies Pvt Ltd
        
        
    Requirred Skills: 
    python,django,html5,javascript
    
    
    Job Links: https://www.timesjobs.com/job-detail/python-interns-3ri-technologies-pvt-ltd-pune-5-to-8-yrs-jobid-cfLZrmnuzxxzpSvf__PLUS__uAgZw==&source=srp
    
    Company Name: 
        DREAMAJAX TECHNOLOGIES
        
        
    Requirred Skills: 
    python,django,api,sql,nosql
    
    
    Job Links: https://www.timesjobs.com/job-detail/python-developer-dreamajax-technologies-bengaluru-bangalore-4-to-7-yrs-jobid-EWIVCDzRLKBzpSvf__PLUS__uAgZw==&source=srp
    
    Company Name: 
        INFINITY GROUP
        
        
    Requirred Skills: 
    python,css,django,html,bootstrap
    
    
    Job Links: https://www.timesjobs.com/job-detail/python-developer-infinity-group-noida-greater-noida-2-to-5-yrs-jobid-efOg3e9X__SLASH__D9zpSvf__PLUS__uAgZw==&source=srp
    
    Company Name: 
        CONNECTING 2 WORK
        
        
    Requirred Skills: 
    python,storage,django,testingtools,debugging
    
    
    Job Links: https://www.timesjobs.com/job-detail/python-developer-connecting-2-work-thiruvananthapuram-5-to-10-yrs-jobid-Tebue__SLASH__8iTzVzpSvf__PLUS__uAgZw==&source=srp
    
    Company Name: 
        xonier technologies pvt ltd
        
        
    Requirred Skills: 
    python,django,testingtools,debugging,storage
    
    
    Job Links: https://www.timesjobs.com/job-detail/python-developer-xonier-technologies-pvt-ltd-noida-greater-noida-2-to-5-yrs-jobid-VZ3nXzqL2FNzpSvf__PLUS__uAgZw==&source=srp
    
    Company Name: 
        Sourcedesk Global Private Limited
        
        
    Requirred Skills: 
    
    html5,storage,python,javascript,django,infrastructure
    
    
    Job Links: https://www.timesjobs.com/job-detail/python-developer-sourcedesk-global-private-limited-kolkata-3-to-15-yrs-jobid-A27Uf03p2IJzpSvf__PLUS__uAgZw==&source=srp
    
    Company Name: 
        TandA HR Solutions
        
        
    Requirred Skills: 
    python,cloudservices,postgresql,mysql,machinelearning
    
    
    Job Links: https://www.timesjobs.com/job-detail/python-developer-tanda-hr-solutions-mohali-5-to-8-yrs-jobid-mpGA2O7bJEVzpSvf__PLUS__uAgZw==&source=srp
    
    Company Name: 
        InnOvator Web Solutions Pvt.Ltd.
        
        
    Requirred Skills: 
    
    rest,python,django,webdeveloper,mysql,api
    
    
    Job Links: https://www.timesjobs.com/job-detail/python-developer-innovator-web-solutions-pvt-ltd-mumbai-5-to-8-yrs-jobid-OO__SLASH__Qb2Q7MfpzpSvf__PLUS__uAgZw==&source=srp
    
    Company Name: 
        creative thoughts informatics indore
        
        
    Requirred Skills: 
    python,django,restapi,html5,javascript
    
    
    Job Links: https://www.timesjobs.com/job-detail/python-developer-creative-thoughts-informatics-indore-indore-1-to-4-yrs-jobid-xtV5Tl3aEcVzpSvf__PLUS__uAgZw==&source=srp
    
    Company Name: 
        pearl global solutions
        
        
    Requirred Skills: 
    python,database,django,teamplayer,sql
    
    
    Job Links: https://www.timesjobs.com/job-detail/python-developer-pearl-global-solutions-cochin-kochi-ernakulam-4-to-7-yrs-jobid-dZD__SLASH__NDlCjpVzpSvf__PLUS__uAgZw==&source=srp
    
    Company Name: 
        AxisTechnolabs
        
        
    Requirred Skills: 
    python,django,itskills,html5,api,jquery
    
    
    Job Links: https://www.timesjobs.com/job-detail/python-odoo-axistechnolabs-ahmedabad-0-to-1-yrs-jobid-HzL8naalyxFzpSvf__PLUS__uAgZw==&source=srp
    
    


```python
#in this cell, I use a code to call out differnt job function and also set a timer



from bs4 import BeautifulSoup
import requests

print('print some skill that you are not familiar with')

unfamiliar_skill = input('>')
print(f'filtering out {unfamiliar_skill}')

def find_Jobs():
    html_text= requests.get('https://www.timesjobs.com/candidate/job-search.html?searchType=personalizedSearch&from=submit&txtKeywords=Python&txtLocation=').text

    Soup = BeautifulSoup(html_text,'lxml')

    Jobs = Soup.find_all('li', class_='clearfix job-bx wht-shd-bx').text

    #print(Job)

    # dot replace('','') used in the line of code below is used to removed the white space that should have come up with out output
    for Job in Jobs:

        Published_Date = Job.find('span', class_ = 'sim-posted').text

        if 'few' in Published_Date:

            Company_name = Job.find('h3', class_ = 'joblist-comp-name').text.replace(' ',' ')

            Skills_needed = Job.find('span',class_ = 'srp-skills').text.replace(' ', '')


            if unfamiliar_skill not in Skills_needed:


                Job_links = Job.header.h2.a['href']

                print(f'''Company Name: {Company_name}''') 

                print(f'''Requirred Skills: {Skills_needed}''') 

                print(f'Job Links: {Job_links}')


                print('')

```

    print some skill that you are not familiar with
    


```python
#This line of code is use to save data scrapped from this website to a csv file
import csv

Header = ['Jobs','Company_name','Skills_needed','Job_links']

Data = [Jobs, Company_name,Skills_needed,Job_links]

with open('TimejobscrappingDataset.csv','w',newline='',encoding='UTF8') as f:
    
    writer=csv.writer(f)
    writer.writerow(Header)
    writer.writerow(Data)
```


```python
import csv

Header = ['Jobs','Company_name','Skills_needed','Job_links']

Data = [Jobs, Company_name,Skills_needed,Job_links]

with open('TimejobscrappingDataset.csv','w',newline='',encoding='UTF8') as f:
    
    writer=csv.writer(f)
    writer.writerow(Header)
    writer.writerow(Data)
```


```python

```
