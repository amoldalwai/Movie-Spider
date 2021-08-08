
<!-- [![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![MIT License][license-shield]][license-url]
[![LinkedIn][linkedin-shield]][linkedin-url] -->



<!-- PROJECT LOGO -->
<br />
<p align="center">
  <a href="https://github.com/othneildrew/Best-README-Template">
    <img src="https://github.com/amoldalwai/Movie-Spider/blob/main/WatchAnyMovieLogo.png" alt="Logo" width="80" height="80">
  </a>

  <h3 align="center">Movie Spider API</h3>

  <p align="center">
    An awesome API uses web scrapping and searches for latest Bollywood, Tollywood and Hollywood movies from various sites and provides video streaming links directly!
    <br />
    <a href="https://github.com/othneildrew/Best-README-Template"><strong>Explore the docs »</strong></a>
    <br />
    <br />
    <a href="https://github.com/othneildrew/Best-README-Template">View Demo</a>
    ·
    <a href="https://github.com/othneildrew/Best-README-Template/issues">Report Bug</a>
    ·
    <a href="https://github.com/othneildrew/Best-README-Template/issues">Request Feature</a>
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
        <li><a href="#installation">How to Use</a></li>
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

[![Product Name Screen Shot][product-screenshot]](https://example.com)

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


_For more examples, please refer to the [Documentation](https://example.com)_



<!-- ROADMAP -->
## Roadmap




<!-- CONTRIBUTING -->
## Contributing

Contributions are what make the open source community such an amazing place to be learn, inspire, and create. Any contributions you make are **greatly appreciated**.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request



<!-- LICENSE -->
## License

Distributed under the MIT License. See `LICENSE` for more information.



<!-- CONTACT -->
## Contact

Your Name - [@your_twitter](https://twitter.com/your_username) - email@example.com

Project Link: [https://github.com/your_username/repo_name](https://github.com/your_username/repo_name)



<!-- ACKNOWLEDGEMENTS -->
## Acknowledgements
* [GitHub Emoji Cheat Sheet](https://www.webpagefx.com/tools/emoji-cheat-sheet)
* [Img Shields](https://shields.io)
* [Choose an Open Source License](https://choosealicense.com)
* [GitHub Pages](https://pages.github.com)
* [Animate.css](https://daneden.github.io/animate.css)
* [Loaders.css](https://connoratherton.com/loaders)
* [Slick Carousel](https://kenwheeler.github.io/slick)
* [Smooth Scroll](https://github.com/cferdinandi/smooth-scroll)
* [Sticky Kit](http://leafo.net/sticky-kit)
* [JVectorMap](http://jvectormap.com)
* [Font Awesome](https://fontawesome.com)





<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/othneildrew/Best-README-Template.svg?style=for-the-badge
[contributors-url]: https://github.com/othneildrew/Best-README-Template/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/othneildrew/Best-README-Template.svg?style=for-the-badge
[forks-url]: https://github.com/othneildrew/Best-README-Template/network/members
[stars-shield]: https://img.shields.io/github/stars/othneildrew/Best-README-Template.svg?style=for-the-badge
[stars-url]: https://github.com/othneildrew/Best-README-Template/stargazers
[issues-shield]: https://img.shields.io/github/issues/othneildrew/Best-README-Template.svg?style=for-the-badge
[issues-url]: https://github.com/othneildrew/Best-README-Template/issues
[license-shield]: https://img.shields.io/github/license/othneildrew/Best-README-Template.svg?style=for-the-badge
[license-url]: https://github.com/othneildrew/Best-README-Template/blob/master/LICENSE.txt
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://linkedin.com/in/othneildrew
[product-screenshot]: images/screenshot.png
