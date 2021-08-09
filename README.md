
<!-- [![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![MIT License][license-shield]][license-url]
[![LinkedIn][linkedin-shield]][linkedin-url] -->



<!-- PROJECT LOGO -->
<br />
<p align="center">
  <a href="https://github.com/amoldalwai/Movie-Spider/">
    <img src="https://github.com/amoldalwai/Movie-Spider/blob/main/WatchAnyMovieLogo.png" alt="Logo" width="80" height="80">
  </a>

  <h3 align="center">Movie Spider API</h3>

  <p align="center">
    An awesome API uses web scrapping and searches for latest Bollywood, Tollywood and Hollywood movies from various sites and provides video streaming links directly!
    <br />
    <a href="https://rapidapi.com/amol.dalwai/api/movie-spider"><strong>Explore the docs »</strong></a>
    <br />
    <br />
    <a href="https://rapidapi.com/amol.dalwai/api/movie-spider">View Demo</a>
    ·
    <a href="https://github.com/amoldalwai/Movie-Spider/issues">Report Bug</a>
    ·
    <a href="https://github.com/amoldalwai/Movie-Spider/issues">Request Feature</a>
  </p>
</p>



<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#how-to-use">How to Use</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#roadmap">Roadmap</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#acknowledgements">Acknowledgements</a></li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## About The Project


Movie spider uses web scrapping and searches for latest Hollywood, Bollywood, Tollywood and  movies from various sites and provides video streaming links directly.
Movie links are provided from video hosting platforms such as vidcloud, doodstram, streamtape, mixdrop .The web crawler searches these sites for following title of imdb id provided and then returns the video url.

Why to choose it :
* It is a free service created for educational purposes , that provides direct links to movie hosting services.
* It uses IMDb Id or title of the movie to search from torrente sites that you can play on your browser.
* Has collection of 10000+ movies.


### Built With

The Api is built using Python Flask and uses Webscraping throught Beautiful Soup .
* [Flask](https://flask.palletsprojects.com/en/2.0.x/)
* [BeautifulSoup](https://www.crummy.com/software/BeautifulSoup/bs4/doc/)


<!-- GETTING STARTED -->
## Getting Started

Movie Spiders is a Simple REST API ,that you can integrate with other languages like Python,JavaScript any many more.

### Prerequisites

Following Instructions are for how to integrate it with  Node.js using axios

### How to use

1. Get a free API Key at [https://rapidapi.com/amol.dalwai/api/movie-spider](https://rapidapi.com/amol.dalwai/api/movie-spider)

3. Install NPM packages
   ```sh
   npm install axios
   ```
4. Enter your API in `config.js`
   ```JS
   const API_KEY = 'ENTER YOUR API KEY';
   ```


<!-- USAGE EXAMPLES -->
## Usage
1. `GET\imdb`
To search movies by imdb id do the following .
 ```JS
   var axios = require("axios").default;

var options = {
  method: 'GET',
  url: 'https://movie-spider.p.rapidapi.com/imdb',
  params: {id: 'YOUR IMDB ID eg. tt0816692'},
  headers: {
    'x-rapidapi-key': 'YOUR API KEY from config.js',
    'x-rapidapi-host': 'movie-spider.p.rapidapi.com'
  }
};

axios.request(options).then(function (response) {
	console.log(response.data);
}).catch(function (error) {
	console.error(error);
});
 ```
 Example Response
 ```
 {
imdb_id: {
id: "tt0816692"
},
movie_links: {
vidcloud: "/play?server=vidcloud&id=9Q55Xpd",
multiserver: "/play?server=multiserver&id=y277MIV",
doodstream: "/play?server=doodstream&id=upccOZJ",
123movies: "/play?server=123movies&id=dBlljAc",
Fembed: "/play?&id=OQXXGby&server=fembed",
MultiSource: "/play?server=multisource&id=GKSS8bv",
Dbgo: "/play?&id=C2hhf1V&server=dbgo",
1movie: "/play?&id=V3SSe91&server=1movie",
HLS: "/play?&id=KbssBuA&server=hls",
Gdrive-VIP: "/play?server=gdrivevip&id=eL33dai",
Streamtape: "/play?&id=ZqMMCBl&server=streamtape"
},
message: {
status_code: "200_OK"
}
}
 ```
 Now copy any  link from video_url list from the response and save the server and unique id 

 
 2. `GET\play`
The id and server name received from above request ,pass them in the PLAY endpoint like  .
 ```JS
 var axios = require("axios").default;

var options = {
  method: 'GET',
  url: 'https://movie-spider.p.rapidapi.com/play',
  params: {server: 'Server name from above imdb response eg.vidcloud', id: ' Unique id from above imdb response eg.RXQXuRdX'},
  headers: {
    'x-rapidapi-key': 'API KEY ',
    'x-rapidapi-host': 'movie-spider.p.rapidapi.com'
  }
};

axios.request(options).then(function (response) {
	console.log(response.data);
}).catch(function (error) {
	console.error(error);
});
  ```
  
  Response from above is html page that plays the movie .You can use it as a iframe in your application.
 
  Example Response <br/>
  <img src="https://github.com/amoldalwai/Movie-Spider/blob/main/play_example_response.PNG" align="center" alt="example response play" width="500" height="270">
  
  
3. `GET\title`
To search movies by title it requires a server id and title of movie. 
* Valid values of server id is 1 to 7 eg. server=3
* Title of the movie should conatin space if there is space in movies name eg.title=fast and furious 9 or if there is no space in movie name eg. title=interstellar
* Not all server have all the movie links ,hence it is better to try in all servers.
 ```JS
  var axios = require("axios").default;

var options = {
  method: 'GET',
  url: 'https://movie-spider.p.rapidapi.com/search',
  params: {server: 'SERVER ID eg. 3', title: 'TITLE OF MOVIE TO SEARCH eg. fast and furious 9'},
  headers: {
    'x-rapidapi-key': 'API KEY ',
    'x-rapidapi-host': 'movie-spider.p.rapidapi.com'
  }
};

axios.request(options).then(function (response) {
	console.log(response.data);
}).catch(function (error) {
	console.error(error);
});
```
Example response 
```
{
title_query: {
title: "fast+and+furious+9"
},
video_url: [
"https://pkspeed.net/s48xrnxkjpd6.html",
"https://dood.so/e/uuyhbbjbilqc",
"//mixdrop.sx/f/rw3ql6jxs7z0gj",
"https://www.moviesmanha.com/fast-and-furious-9-2021-english-full-movie-watch-online-hd-print-free-download/"
],
message: {
status_code: "200",
status_message: "Movie found"
},
```

Copy any of the links in video url as the srouce of the iframe in your application 



_For more examples, please refer to the [Documentation](https://rapidapi.com/amol.dalwai/api/movie-spider)_


<!-- LICENSE -->
## License

Created for educational purposes



<!-- CONTACT -->
## Contact

Project Link: [https://github.com/amoldalwai/Movie-Spider/](https://github.com/amoldalwai/Movie-Spider/)






