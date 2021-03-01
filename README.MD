# Webportal
Webportal is a web application, that contains next parts:

1. [flask_backend](https://github.com/BorodaUA/flask_backend) an api build with [flask](https://github.com/pallets/flask), and [flask-restful](https://github.com/flask-restful/flask-restful).
2. [flask_frontend](https://github.com/BorodaUA/flask_frontend) regular flask app, that serve data from [flask_backend](https://github.com/BorodaUA/flask_backend).
3. [postgres_sever](https://github.com/BorodaUA/postgres_server) An postgresql server that store and serve data to [flask_backend](https://github.com/BorodaUA/flask_backend) and [hacker_news_parser](https://github.com/BorodaUA/hacker_news_parser).
4. [hacker_news_parser](https://github.com/BorodaUA/hacker_news_parser) A [Scrapy](https://github.com/scrapy/scrapy) project, that parsing https://news.ycombinator.com/ , also contains [ScrapydWeb](https://github.com/my8100/scrapydweb) web app to schedule and manage spiders run.
5. [pgadmin4](https://github.com/BorodaUA/pgadmin4) Web application, for [postgres_server](https://github.com/BorodaUA/postgres_server) to manage postgresql.

## How to use:
### Local development mode:
1. Clone the repo
2. For each repository use `readme.md` to create and manage necessary data (creating .env files), preparations and settings, 
3. Use command `docker-compose -p dev_webportal -f ${PWD}/docker-compose.yml up --build` to build and run docker compose, inside the repo
4. Create the [postgres_server](https://github.com/BorodaUA/postgres_server) databases, can be done via [pgadmin4](https://github.com/BorodaUA/pgadmin4)
5. Make [flask_backend](https://github.com/BorodaUA/flask_backend) migrations
6. Set up [hacker_news_parser](https://github.com/BorodaUA/hacker_news_parser) scheduled parsing, can be done via local web interface [Scrapydweb](http://localhost:6900/) address 
7. Run [flask_backend](https://github.com/BorodaUA/flask_backend) via command `python run.py` inside the container
8. Run [flask_frontend](https://github.com/BorodaUA/flask_frontend) via command `python run.py` inside the container
9. Use command `docker-compose -p dev_webportal -f ${PWD}/docker-compose.yml stop` to stop the webportal's docker-compose