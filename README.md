# IBM Watson NLU Project

## About
This project is a Node.js project that allows you to enter some text (must be sufficiently long, around 50 characters or so), or a URL, and the text (or contents of the webpage specified by the URL entered) will be sent to IBM Cloud Watson Natural Language Understanding, and the React webpage with the sentiment or the emotions of the text will be updated with the results. 

## Installation
First, Node.js (and `npm`) is required. Install with `apt`:
```bash
$> sudo apt install nodejs npm
```
or using your distribution's package manager.

Now we can `git clone` the project:
```bash
$> git clone https://github.com/lawruixi/cazgi-IBM-Watson-NLU-Project.git
```
Afterwards, navigate to the directories `/sentimentAnalyzeClient` and `/sentimentAnalyzeServer` and `npm install` the required dependencies.
```bash
$> cd sentimentAnalyzeClient && npm install -s
$> cd ../sentimentAnalyzeServer && npm install -s
```

Next up, we need the API Key and the API URL of the [IBM Natural Language Understanding](https://cloud.ibm.com/catalog/services/natural-language-understanding) service we are using. No, I am not sharing my API Key and API URLs. It's free anyway (for a limited time, at least) so just go ahead and sign up for one. The file should be in the `sentimentAnalyzeFolder` directory.
```bash
$> touch .env
$> printf "API_KEY=<API_KEY>\n" >> .env
$> printf "API_URL=<API_URL" >> .env
```

Finally, we can build and install:
```bash
$> cd ../sentimentAnalyzeClient && npm run-script build
$> cd ../sentimentAnalyzeServer && npm start
```

This should start the Node.js server on the local machine, listening on port `8080` by default. (This can be changed in `sentimentAnalyzeServer/sentimentAnalyzerServer.js`.)

## Usage
Now use a browser (or `curl`, if you're that kind of person) to access the Node.js server. (This should be `localhost:8080'`.) If you are unable to get it working for any number of reasons, you may visit [this website](http://lawruixi-3v3-sentiment-analyzer-excellent-gazelle-xx.mybluemix.net/) (which may not be up for long, given the nature of IBM Lite Account which I was using to host the website).

There is a text field, which you can insert text into. Click URL if you instead want to ask it to read the contents of a webpage. (Personally, I used fanfiction on AO3 for testing. What? It's a perfectly normal thing to do.) 
After inserting text (or specifying a URL), click either "Analyze Sentiment" or "Analyze Emotion" to begin the analysis. You might need to wait for around 10 seconds for the results to show up. **Do note that around 50 characters are required for a successful analysis.** Otherwise, nothing will happen. ~~(TODO: Add error message?)~~

Well, that's about it, really. You can play around with the website. Personally, I think it's pretty cool. That's all from me today!

## Acknowledgements
A great thanks to the Final Project of the [Developing Cloud Apps with Node JS And React](https://www.coursera.org/learn/node-js?specialization=ibm-full-stack-cloud-developer) Course as part of the [IBM Full Stack Cloud Developer Professional Certificate](https://www.coursera.org/professional-certificates/ibm-full-stack-cloud-developer) on [Coursera](https://www.coursera.org/), without which this project would never have been on my GitHub Page. Cheers once more!
