# Data Science Docker Base

This repository provides Docker Compose configurations and pre-built Docker images tailored for data science projects. The images come with essential libraries and tools for various domains, including visualization, data processing, NLP, computer vision, time series, and geospatial analysis. Additionally, the project includes Doccano for annotation, making it a complete toolkit for different data science tasks.

## Features

- **Pre-configured Docker Compose** setup for easy environment management.
- **Comprehensive toolset**: Packages for:
  - Visualization 
  - Data processing
  - Natural Language Processing
  - Computer Vision 
  - Time series 
  - Geospatial
- **Doccano integration** for easy annotation of text, images, and more.
- Ready-to-use Docker images for Jupyter Notebook and other data science tools.

## Getting Started

### Prerequisites

Before you begin, ensure you have the following installed on your local machine:

- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)


### Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/jomaminoza/data-science-docker-base.git
   cd data-science-docker-base
   ```

2.  Build the Docker containers using docker-compose:

    ```bash

    docker-compose build
    ```

3. Start the containers:

    ```bash

    docker-compose up
    ```

4.  After starting the containers, you can access Jupyter Notebook by visiting the following URL in your browser:

    ```bash
    http://localhost:5000
    ```

    (The default port and URL may vary depending on your configuration.)

### Accessing the Jupyter Notebook

Once the containers are running, Jupyter Notebook will be available in your browser. Simply open the URL provided in the console output.

### Stopping the Containers

To stop the running containers, press CTRL+C in the terminal where the containers are running or use:

  ```bash
  docker-compose down
  ```
