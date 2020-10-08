# webscraping640
Web scraping, web harvesting, or web data extraction is data scraping used for extracting data from websites. Web scraping software may access the World Wide Web directly using the Hypertext Transfer Protocol, or through a web browser. While web scraping can be done manually by a software user, the term typically refers to automated processes implemented using a bot or web crawler. It is a form of copying, in which specific data is gathered and copied from the web, typically into a central local database or spreadsheet, for later retrieval or analysis.  Web scraping a web page involves fetching it and extracting from it. Fetching is the downloading of a page (which a browser does when a user views a page). Therefore, web crawling is a main component of web scraping, to fetch pages for later processing. Once fetched, then extraction can take place. The content of a page may be parsed, searched, reformatted, its data copied into a spreadsheet, and so on. Web scrapers typically take something out of a page, to make use of it for another purpose somewhere else. An example would be to find and copy names and phone numbers, or companies and their URLs, to a list (contact scraping).  Web scraping is used for contact scraping, and as a component of applications used for web indexing, web mining and data mining, online price change monitoring and price comparison, product review scraping (to watch the competition), gathering real estate listings, weather data monitoring, website change detection, research, tracking online presence and reputation, web mashup and, web data integration.  Web pages are built using text-based mark-up languages (HTML and XHTML), and frequently contain a wealth of useful data in text form. However, most web pages are designed for human end-users and not for ease of automated use. As a result, specialized tools and software have been developed to facilitate the scraping of web pages.  Newer forms of web scraping involve listening to data feeds from web servers. For example, JSON is commonly used as a transport storage mechanism between the client and the web server.  There are methods that some websites use to prevent web scraping, such as detecting and disallowing bots from crawling (viewing) their pages. In response, there are web scraping systems that rely on using techniques in DOM parsing, computer vision and natural language processing to simulate human browsing to enable gathering web page content for offline parsing.

## Real-Time Video Recognition AI with auto-webscraping trainer + alerts, YoloV3
### By: Nasrudin Salim

#### Real-time object detection and classification with YoloV3


#### Test:
![ ](nas-demo.gif  "Algorithm Real-Time Demo")

### What is this:

- Automatically trains a model via webscraping image search results on a video recognition classifier with transfer learning.
- Enter a label, then enter a list of search queries to google for. It will then google for those search terms and fine-tunes a pretrained classifier.
- Detect objects as well as output alerts/colors differently if an object in your "alert list" is found.
- Can be performed on a video stream in real-time.
- Can be performed on a live-camera stream in real-time.


### Prerequisities
0. Anaconda 3
1.  Python 3
2. CUDNN and CUDA ToolKit Installed
3. GPU with CUDA 9.0 and above support

## Installation Instructions:
- A conda environment file has been provided, please make use of environment file to install the necessary requirement packages.
		conda create -n "YourEnvironmentName" -f environment.yml
- Project uses Cython, so build that too.
		python3 setup.py build_ext --inplace

Remember to download pretrained weights if you need to
See training section

# Usage
#### Getting Data
On the webscraper, indicate the labels in labels.txt, and change the parameters in config.py if needed then in terminal, type


		python3 downloadimages.py

#### Training
Once images are downloaded. You can download pretrained weights here: 
[darknet](https://pjreddie.com/darknet/yolo/) 
Or you can continue training your weights if you've done this before
Edit the parameters in train.py and then in batch type:

		python3 train.py -g

	-g : Whether to use GPU
	-e #: Epochs (optional)
	-s #: Save Rate (optional)
	-e #: Epochs (optional)
	-lr #: Learning Rate (optional)
	-b #: Batch (optional)


#### Testing/Using
Usage:

	python3 run.py "path_to_video_file" -g -s "test.avi"
	
#### Explanation

	Whether to use a video file, supply path
	If not video file, assume to use camera feed.
	-g /--gpu : Optional, whether to use GPU ( Defaults to config)
	-s /--save: Optional, whether to save results to a video file and where (Defaults to config)

### Configs

There is a config.py provided which helps to set the defaults for the following:
1. 	Edit the path to weight file
2. 	USE GPU? Bool
3. 	SAVE Result video file? Bool


You will be asked for the path of the video file. You can adjust the parameters as well as the paths of the weights by opening up the py files.

#### Setting Alerts
You can set alerts by editing the text file "alerts.txt" when a label found in this text file appears, it will generate an alert by drawing the box red and displaying "Alert x found in footage" when testing.

#### HELP AND CONTRIBUTION

	This project needs your help and contribution
	The Training Script needs work.
	The Alerts and Pinging requires work to finish.
	Downloading of images from google and seamless Training


