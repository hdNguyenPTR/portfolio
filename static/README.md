<div id="top"></div>

<!-- PROJECT LOGO -->
<br />
<div align="center">

<h3 align="center">Movie GRPC</h3>

  <p align="center">
    Simple GRPC service
    <br />
  </p>
</div>



<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#installation">Installation</a></li>
        <li><a href="#usage">Usage</a></li>
      </ul>
    </li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## About The Project

A simple grpc service that consume Event's cinema JSON data and communicate it between 2 services.

<p align="right">(<a href="#top">back to top</a>)</p>

<!-- GETTING STARTED -->
## Getting Started

Unzip to a working folder

### Installation

1. Simply run the run.sh in the top level directory file to start the server and client.

<p align="right">(<a href="#top">back to top</a>)</p>

<!-- USAGE EXAMPLES -->
## Usage
There are 2 endpoints added to the moviepresenter http://localhost:8081/ service, /moviesGrpc and /moviesHttp

1. This endpoint uses grpc client stub to recieve and display the movie JSON from the moviedatasource service
   ```
   http://localhost:8081/moviesGrpc
   ```

2. This endpoint uses basic http to recieve and display the movie JSON from the moviedatasource service
   ```
   http://localhost:8081/moviesHttp
   ```

<p align="right">(<a href="#top">back to top</a>)</p>
