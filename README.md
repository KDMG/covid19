
This repository includes a Linked Data representation of the [covid19-ita dataset](https://github.com/pcm-dpc/COVID-19) provided by the Department of the Civil Protection in Italy, following the [RDF Data Cube Vocabulary](https://www.w3.org/TR/vocab-data-cube/).

### Objective

Italy has been one of the countries most affected by the new coronavirus outbreak, both in terms of number of positive cases and economically. Starting from February 24th, 2020 the Department of Civil Protection in Italy has been publishing measurements of various indicators related to COVID19 spread at province, regional and country levels. The datasets are in CSV format and are updated on a daily basis. 

Giving data explicit semantic helps to better understand them, improve their access through web-scale queries, their reuse and, ultimately, increase their value. 
In this project, we translate the dataset produced by the Department of Civil Protection into Linked Data, with the purpose  to obtain a greater opennes, facilitating data discovery and by linking the dataset to other data sources. 

![graph example](/resources/graph.png)

### The data structure
Our dataset relies on the [RDF Data Cube Vocabulary](https://www.w3.org/TR/vocab-data-cube/), which allows to describe statistical multidimensional data as Linked Data on the Web. As such, each data point is represented as an observations of the relevant measures along two dimensions, namely time and geographical area. 
The [`/dataset`](/dataset) folder includes:

* [`covid19-ita_dsd.ttl`](/dataset/covid19-ita_dsd.ttl): the Data Structure Definition of the dataset. Here, dataset metadata are provided together with definition of dimensions, measures and attributes. By extending the RDF Data Cube vocabulary, our representation of measures include also their explicit mathematical meaning, namely their calculation formula, according to the [http://w3id.org/kpionto](KPIOnto vocabulary).
* [`covid19-ita-regioni_sample.ttl`](/dataset/covid19-ita-regioni_sample.ttl): a sample of the regional dataset. Observations are organized according to the Data Structure Definition. 

As an example, the following observation describes the measurement taken in the Marche region on 1 May 2020.

```
  cov:obs1417 a qb:Observation ;
    cov:New_Cases 28 ;
    cov:Total_Active_Cases 3211 ;
    cov:Total_Cases 6275 ;
    cov:Total_Cases_Tested 40123 ;
    cov:Total_Deaths 911 ;
    cov:Total_Home_Isolation 2754 ;
    cov:Total_Hospitalized 457 ;
    cov:Total_Hospitalized_With_Sympthoms 413 ;
    cov:Total_Intensive_Care 44 ;
    cov:Total_Recovered 2153 ;
    cov:Total_Tests 61241 ;
    cov:Variation_Total_Active_Cases 1 ;
    cov:refArea dbr:Marche ;
    cov:refTime "2020-05-01T17:00:00"^^xsd:dateTime ;
    qb:dataSet cov:covid19Italy .
```

RDF serialization is provided in [Turtle syntax](https://www.w3.org/TR/turtle/). 
The full dataset for regions and the dataset for provinces will be uploaded soon.


### Licence
The project is licenced under the [Creative Commons Attribution 4.0 International
](https://creativecommons.org/licenses/by/4.0/deed.it) [(show the licence)](LICENCE)

### Changelog
* 2020-05-17: publication of the Data Structure Definition and a sample of the regional dataset

### Contacts
For information or requests, please contact Emanuele Storti - <e.storti@univpm.it>
