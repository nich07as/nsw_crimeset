# NSW Crimeset Visualisation
Ingesting Public Crimeset Data into Elasticsearch

## Credits / References:
The data set is taken from from [DATA.GOV.AU](http://data.gov.au/storage/f/2013-09-12T23%3A32%3A36.918Z/rci-offencebymonth.csv)

## Modifications
The sample data set contains "," within some string values thus needs translation; and also the the field names had been transformed by replacing whitespaces ' ' with underscore '_'.

## Sample Kibana Dashboard
![image](https://cloud.githubusercontent.com/assets/8389292/24992531/37ef993a-2065-11e7-90e3-9f1a6961f8c6.png)

## Setup and Assumptions
### Assumptions
1. Elasticsearch is already installed and running;
2. You know how to actually download, run bin/elasticsearch to bring it up at least locally in your machine
3. Know where to find and download kibana and run bin/kibana

### Setup
1. Download logstash [here](https://www.elastic.co/downloads/logstash)
2. Clone this repository;
3. Modify the following properties in the logstash config file named `nsw_crimeset_logstash.conf`
```
path => "/<path_to_your_cloned_repo>/nsw_offence.csv  
template => "/<path_to_your_cloned_repo>/nsw_crimeset_template.json"  
hosts => ["localhost:9200"]
```
4. In Kibana, configure your index pattern to read `nsw*`
5. Then upload the kibana objects where all the goodies like the Dashboard, filename `nsw_crimeset.json`
6. Navigate to your kibana dashboard and enjoy.
7. If you have X-PACK installed, enjoy Graphing on the relationships :)
