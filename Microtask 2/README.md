# Chaoss-microtasks-2019

## Requirements
1. Docker
2. Grimoirelab docker image [Image](https://hub.docker.com/r/grimoirelab/full)

## Steps to create Dashboard
1. Run the following command
```docker run -p 127.0.0.1:9200:9200 -p 127.0.0.1:5601:5601 \
    -v $(pwd)/credentials.cfg:/override.cfg \
    -v $(pwd)/projects.json:/projects.json \
    -t grimoirelab/full
```
This will start ElasticSearch on port 9200 and Kibiter on port 5601.
credentials.cfg will contain Github Personal access token, which is required to use Github API to retrieve information
projects.json contains information about the Data Sources (like Github repository link) from which data is to be retrieved and stored in ElasticSearch Indexes.

2. There are some pre-loaded visualizations which are very useful to build quick dashboards, the git_aoc vizualizations are generated when the enriched index is loaded.
3. Using different generated visualizations, build the dashboard.
4. Dashboard can be exported in the settings tab of kibiter, to a .json file.
