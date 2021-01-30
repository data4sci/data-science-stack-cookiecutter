# Moje poznámky

## CLI 

crate cookiecutter folder structure
```bash
cookiecutter https://github.com/data4sci/data-science-stack-cookiecutter.git
```

run just jupyter
```bash
docker run -d -p 8888:8888 jupyter/scipy-notebook
```

přidat examples do běžícího Superset kontejneru
```bash
docker exec -it superset superset load_examples
```

## TODO

* audit docker kontejnerů (2 roky staré video!)
*

## další microservices

* Streamlit
  * [Streamlit — The fastest way to create data apps](https://www.streamlit.io/)
  * [Deploy a Streamlit NLP WebApp with Docker -](https://maelfabien.github.io/project/Streamlit/#the-application)
  * [Deploy a machine learning application with Streamlit and Docker on AWS | by Kostas Stathoulopoulos | Towards Data Science](https://towardsdatascience.com/how-to-deploy-a-semantic-search-engine-with-streamlit-and-docker-on-aws-elastic-beanstalk-42ddce0422f3)
  * [(124) How To Deploy Streamlit Apps with Docker - YouTube](https://www.youtube.com/watch?v=doCia_CKcko)

* Datasette
  * [Datasette: An open source multi-tool for exploring and publishing data](https://datasette.io/)

* Dash 
  * [Dash Documentation & User Guide | Plotly](https://dash.plotly.com/)
  * [Part 2. Layout | Dash for Python Documentation | Plotly](https://dash.plotly.com/)
  * [Dash Enterprise App Gallery](https://dash-gallery.plotly.host/Portal/)
  * [Dash for Beginners - DataCamp](https://www.datacamp.com/community/tutorials/learn-build-dash-python)
  * [The Sweet Spot of Plotly. Why Plotly is a great exploratory tool… | by Moorissa Tjokro | Towards Data Science](https://towardsdatascience.com/the-sweet-spot-of-plotly-c6e1342e3544) 
  >Platforms like Tableau, Kibana, and Superset offer features such as dropdown that accept only one data table as an input per graph.
  * [Dash Azure Deployment](https://medium.com/swlh/deploy-a-dash-application-in-azure-using-docker-ed46c4b9d2b2)
  * [vioquedu/docker-dash: Docker configuration to develop and deploy a Plotly Dash application](https://github.com/vioquedu/docker-dash)
  * !!! [ploner/coronavirus-py: Simple web app showing Coronavirus case data using Python, Dash and Plotly](https://github.com/ploner/coronavirus-py)

## docker kontejnery

* Streamlit [samdobson/streamlit - Docker Hub](https://hub.docker.com/r/samdobson/streamlit)
* FastAPI [tiangolo/uvicorn-gunicorn-fastapi Dockerfile - Docker Hub](https://hub.docker.com/r/tiangolo/uvicorn-gunicorn-fastapi/dockerfile)
* Neo4j [neo4j - Docker Hub](https://hub.docker.com/_/neo4j/)
* Neo4j Experimental [neo4j/neo4j-experimental - Docker Hub](https://hub.docker.com/r/neo4j/neo4j-experimental)
* MongoDB [mongo - Docker Hub](https://hub.docker.com/_/mongo)
* D-Tale [man-group/dtale: Visualizer for pandas data structures](https://github.com/man-group/dtale#docker-container)




-----------------------------------------------------------------------------------------

# Data Science Stack - Cookiecutter
[![Maintainers Wanted](https://img.shields.io/badge/maintainers-wanted-red.svg)](https://github.com/pickhardt/maintainers-wanted)

Cookiecutter to launch an awesome Data Science toolstack in Docker.

# See it in action
[![asciicast](https://asciinema.org/a/CcZ9duIdP0pBfZWxw5Nt1tFVZ.png)](https://asciinema.org/a/CcZ9duIdP0pBfZWxw5Nt1tFVZ)

# Overall Architecture
![architecture](./architecture.png)

# Used Variables
The following table provides an overview about parameter, that are queried by cookiecutter (and why)

| Name | Description | Injected in Services |
| --- | --- | --- | 
| **project_name** | *Name of your project* | - |
| **jupyter_password** | *Password to protect your Jupyter service* | Jupyter |
| **postgres_db_password** | *Password of standard postgres user* | Postgres |
| **shared_db_password** | *Password for shared database* | Airflow<br>Jupyter<br>Postgres |
| **superset_db_password** | *Password for superset database* | Postgres<br>Superset |
| **superset_admin_password** | *Password for superset admin user* | Superset |
| **minio_access_key** | *Access key for Minio store* | Airflow<br>Apistar<br>Jupyter<br>Minio |
| **minio_secret_key** | *Secret key for Minio store* | Airflow<br>Apistar<br>Jupyter<br>Minio |
