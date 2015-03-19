---
layout: post
title:  "Open Data in Jersey City:  Discussion with Brian Platt"
date:   2015-03-17 10:00:00
categories: meetup opendata
author:  Anna Lukasiak
---

On March 17th, 2015, local group of civic tech activists met with Brian Platt from the Mayor Fulop’s office to discuss recent updates and the next steps for the city’s [Official Open Data Portal][officialdataportal].  The meeting was hosted by local civic tech group, [CodeForJC][cjc], a brigade of [CFA][cfa], at the [Teen Tech Center][teentechctr] at [Boys and Girls Club][bgc] in Jersey City, NJ.

* __New city website__:  The current [Official Jersey City website][officialdataportal] needs urgent upgrade to be mobile friendly and modern in content, look and feel.  Candice Osborne and Brian Platt will be leading UX redesign, engaging the community and civic organizations to create a more resident friendly site.  The implementation will be decided during a dedicated city-sponsored hackathon and the winning team will get to build the new website.

* __Budget Visualization__:  The city is interested in showing budget in a more resident friendly form, similar to opengov.com.  Unfortunately, opengov.com does not work seamlessly with the NJ state system.  In New Jersey, all municipalities use the same state mandated system.  CodeForJC started development of city budget visualization last year.  This is the link to the [CodeForJC Budget Visualization][cjcbudgetvis].

* __Interactive Zoning Map__:  With the current increase of development in the city, the Planning Department is looking to create Interactive Zoning Map similar to [Chicago's 2nd City Zoning][2ndcityzoning] or [Newark's Zoning Map][newarkzonemap] that will replace the current static PDF version of [JC Zoning Map][jczonemap].  The redevelopment plans documents will be included in the interactive map application as well as JCRA's [Downtown Development Map][downtowndevmap] & [Journal Sq Development Map][jsqdevmap].  One of the key requirements is the ability for the planning department to update and maintain the most current version on the public website. 

* __9-1-1 Dashboard__:  To make the currently published raw data relevant to average resident, the city wants to create 9-1-1 dashboard.  Second, the spreadsheet is not compatible with all spreadsheet applications and proposal was made to replace it with CSV file(s), which are smaller, as either one per month or single file per year with additional column indicateing the reporting month.  The Public Safety Alert System project that is being developed by a OpenJC together with the JCPD, will create a real time feed with richer data.  

* __Bike Lane Maps__:  [Bike JC][bikejc] is working with Google to update cycling layer on Google maps ([see article here][article]) for Jersey City.  The [bike lanes map][bikelanesmap] on the city website is couple versions behind.  A workflow to update and maintain the data needs to be established.  The maintenance can be performed by BikeJC and the city portal will include the link to the official Google cycling maps.

* __Data Visualization__:  To make the raw data more relevant to the average resident, the city wants to create a series of visualizations using [Raw Operational Data][rawopsdata] sets published on the city’s data portal.

* __Data wrangling__:  Data wrangling and data publishing practices and tools need to be identified to ensure all data currently posted on the Jersey City website can be automatically updated.  It can include tools like open source project [OpenRefine][openrefine] or customized scripts.

* __Tax Abatement Dashboard File__:  The frequently requested Tax Abatement Dashboard File was one of the recent additions to the portal.  The file contains data like development location, abatement type, abatement duration, affordable housing contribution, project cost, current annual taxes, estimated annual service charge, permanent and temporary jobs created, etc, for  abatements granted in  2014  and 2015.  Upon quick inspection, an improvement was suggested add a link to the actual abatement schedule document.  In addition, all outstanding + historical abatements should be made available in the future.

* __OPRA Requests__:  With expectation of a steep rise of OPRA requests in 2015 as compare to previous years, the city implemented new [on-line OPRA request][opraform] form  using SeamlessDocs.  The new public request form replaced the old process where the request was submitted by printing and filling a PDF form that had to be dropped off at the clerk’s office in person or faxed.  The new on-line form enabled the city to to make improvements to the internal process, adding tracking of all requests.   The current process does not provide feedback with status tracking to the requestor.  Suggestions were made use an open source project, the [FOIA Machine][foiamachine] for internal and external request management.

* __Census Data__:  Each year, Jersey City provides local data to the [American Community Survey (U.S. Census Bureau)][amcommunitysurvey].  The submitted JC data can be found [here][jcsurveydata].  It was suggested to create local survey to collect and submit additional information about quality of live and sustainability. 

* __Potholes Repair__:  In 2015 winter season, the city in partnership with the county increased the number of crews to seven.  Further, the Department of Public Works (DPW) is equipping their crews with Spatial Data Logic (SDL) tablet app with real-time workflow where crews can check off the filled potholes as they fill them out.  In the last week alone, the city filled over 1,000 potholes, as compared with 3,000 potholes between Jan and May filled last year.  The process of collecting information about location of potholes can be improved.   The city relies on several sources, including request filed with the [Resident Response Center][rrc] or [FixIt Mobile App][fixit], phone calls, emails and text messages sent directly to DWP’s director Mark Redfield, and FB posts.  The city does not have an app like [Street Bump][streetbump] to help them automatically identify potholes.
* __Official documents digitization process__:  The city is undergoing an official documents digitization process.  After Sandy, FEMA provided a grant to the city to digitize damaged documents.  Unfortunately many documents were lost during Sandy, but all of those that survived were digitized.  Among many of the lost documents were historical documents.  Clerk's office has all documents in digital form backed up by paper copy.
* __The Bloomberg Innovation Grant__:  The city is very close in hiring a director for the [Bloomberg Innovation Grant][iteam].  There is an overlap with the initiative that will focus on crime and youth recreational programs, removing blight, finding new use for abandoned buildings, quality of life index correlation.  There is also an overlap with open data.


[bikejc]: http://www.bikejc.org/
[officialdataportal]: http://www.jerseycitynj.gov/data.aspx
[cjc]: http://codeforjc.org/
[cfa]: http://www.codeforamerica.org/
[teentechctr]: http://www.codeforamerica.org/
[bgc]: http://bgchc.org/ 
[cjcbudgetvis]: http://codeforjc.org/JerseyCityBudget/jc_2014_overview.html 
[2ndcityzoning]: http://secondcityzoning.org/
[newarkzonemap]: http://planning.ci.newark.nj.us/
[jczonemap]: http://www.cityofjerseycity.com/data.aspx?id=14834 
[downtowndevmap]: http://thejcra.org/jcra_files/File/resources/2014/Downtown%20Development%20Map%20November%2006%202014.pdf
[jsqdevmap]: http://thejcra.org/jcra_files/File/resources/2014/Journal%20Square%20Development%20Map%20October%2030%202014.pdf
[article]: http://googleblog.blogspot.com/2010/03/biking-directions-added-to-google-maps.html
[bikelanesmap]: http://www.jerseycitynj.gov/data.aspx?id=14838
[rawopsdata]: http://www.jerseycitynj.gov/data.aspx?id=14832
[openrefine]: http://openrefine.org/
[opraform]: http://www.jerseycitynj.gov/data.aspx 
[foiamachine]: https://www.foiamachine.org/
[amcommunitysurvey]: http://www.census.gov/acs/www/
[jcsurveydata]: http://www.cityofjerseycity.com/data.aspx?id=14948
[rrc]: http://mygovhelp.com/jerseycitynj/_cs/supporthome.aspx?sSessionID=
[fixit]: https://itunes.apple.com/us/app/jersey-city-rrc-fix-it/id748970109?mt=8
[streetbump]: http://www.streetbump.org/
[iteam]: http://www.cityofjerseycity.com/iteam/ 


