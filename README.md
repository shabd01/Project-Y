# Project-Y
This project consists of two components -

### Component 1 - Web Scraping module
You are required to scrape two weeks ( Feb 1 , 2021 to Feb 14 , 2021) of web news files from The Hindu archive site : https://www.thehindu.com/archive/web/2021/02/ . As per the Robots.txt at Hindu website(https://www.thehindu.com/robots.txt) , the archives section is NOT in disallow , thus it implies it is within legal norms to scrape the archive section.

You will need to find URL patterns with which you can go to each day of the two weeks period of February month , find web links and then recursively hit all the web news pages that have occured on that given day page. From each of the page , you need to scrape out the web content and create an independent JSON file that will capture all the text details as values and store them in a key named "text" within that file.

For each of the file to be identifiable independently , create a sequence pattern which will be used for nameing the file. For e.g :

thehindu_feb_02_file_23.json, thehindu_feb_02_file_24.json etc .

You will also need to store all these file names with their respective URLs from which the content is scraped in another lookup file , say URLs_to_file_mapping.csv . Content of this will look like -

file_scraped | Corresponding_URL

thehindu_feb_02_file_1.json | https://www.thehindu.com/sport/other-sports/radjabov-closer-to-beating-dubov/article33475129.ece

thehindu_feb_02_file_2.json | https://www.thehindu.com/sport/other-sports/nba-wall-makes-rockets-debut-in-win-over-kings/article33475123.ece

The intent of look up file is to eventually tag the Topics identified for each URL back to them via the *topics -> scraped file -> URLs linkage

The web scraper that you create might be required to run on your own system / or may work on colab . Depends on the time taken for response from these sites , file storage capacity on a google drive (tied to a colab) or eventually saving scraped files on your local systems. Not all web page link will work via scraping , so try to identify metrics around :

* No of web page hits
* Sucess Hit Ratio
### Component 2 - Topic Model
Once you've scraped the two weeks worth of data , the idea is to perform Topic Model on this scraped data set. You can keep 90% of the web scraped data in training of the model and 10% as a hold out set on which you can assign topics based on the trained model.

Find out the optimal topics number based on Topic Coherence score along with manual review of Topic - words quality.Iterate until you can get the diverse and best topics with words that closely define a theme/topic

For each of the Topic that have been identified - give the Topic Name based on IAB Taxonomy attached. IAB Taxonomy is a standard followed across web to provide web page content a consistent Topic naming convention. Highlighted in the attached XLS are two Tiers - I & II. Tier I is a broad category , whereas Tier II is sub category under Tier I. First ensure you assign Tier I based Topics mapping based on the content and Topic words as they show up. If you feel two topics fall under the same Tier I category then look at assigning further sub-category of Tier II.

Based on the above Topic names assignment , save the model and then assign the topics to 10% test set. Try doing manual review for few set of links i.e whether the assigned topics make sense to the what URL web page is about ? Come up with metrics around Accuracy or any other that you feel relevant to measure the quality of Topic Model

* Use the common repo Project Y for checking in your code periodically , collaborating with other team members and any files that you need to store
* A high level design document towards approach for both components need to be created. This should have flow diagram , any details/ assumptions or hacks that are used while   progressing towarsds tasks.
* Project summary PPT/Report needs to be created which briefly talks about your project work details and results obtained along with illustrative visualizations
