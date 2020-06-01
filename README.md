
This repository includes a Linked Data representation of the [covid19-ita dataset](https://github.com/pcm-dpc/COVID-19) provided by the Department of the Civil Protection in Italy, following the [RDF Data Cube Vocabulary](https://www.w3.org/TR/vocab-data-cube/).

### Objective

Italy has been one of the countries most affected by the new coronavirus outbreak, both in terms of number of positive cases and economically. Starting from February 24th, 2020 the Department of Civil Protection in Italy has been publishing measurements of various indicators related to COVID19 spread at province, regional and country levels. The open datasets are in CSV format and are updated on a daily basis. 

The Open Data approach allows citizens to co-create and make data available to support the community, enhancing transparency and accountability. Furthermore, making data semantics explicit according to the [Linked Data approach](https://www.w3.org/standards/semanticweb/data.html) helps to better understand them, improve their access through web-scale queries, their reuse and, ultimately, increase their value. 
In this project, we translate the Open Data produced by the Department of Civil Protection into Linked Data, with the purpose to obtain a greater opennes, facilitating data discovery by linking the dataset to other data sources. 

![graph example](/resources/graph.png)

### The data structure
Our dataset relies on the [RDF Data Cube Vocabulary](https://www.w3.org/TR/vocab-data-cube/), which allows to describe statistical multidimensional data as Linked Data on the Web. As such, each data point is represented as an observations of the relevant measures along two dimensions, namely time and geographical area. 
The [`/dataset`](/dataset) folder includes:

* [`covid19-ita_dsd.ttl`](/dataset/covid19-ita_dsd.ttl): the RDF Data Cube Data Structure Definition of the dataset. Here, dataset metadata are provided.
* [`covid19-ita_sd.ttl`](/dataset/covid19-ita_sd.ttl): the schema definition, i.e. the ontology providing definition of dimensions, measures, attributes and other classes and properties. By extending the RDF Data Cube vocabulary, our representation of measures include also their explicit mathematical meaning, namely their calculation formula, according to the [KPIOnto vocabulary](http://w3id.org/kpionto).
* [`covid19-ita-andamento-nazionale.ttl`](/dataset/covid19-ita-andamento-nazionale.ttl): the national dataset. Observations are organized according to the Data Structure Definition. 
* [`covid19-ita-regioni.ttl`](/dataset/covid19-ita-regioni.ttl): the regional dataset. Observations are organized according to the Data Structure Definition. 
* [`covid19-ita-note-en.ttl`](/dataset/covid19-ita-note-en.ttl): the dataset of the notes describing specific exceptions occurred in monitoring.

As an example, the following observation describes the measurements taken in the Marche region on 1 May 2020.

```
cov:obs1417 a qb:Observation ;
    cov:New_Cases 28 ;
    cov:Total_Cases 6275 ;
    cov:Total_Cases_Tested 40123 ;
    cov:Total_Deaths 911 ;
    cov:Total_Home_Confinement 2754 ;
    cov:Total_Hospitalised_Patients_With_Symptoms 413 ;
    cov:Total_Hospitalized_Patients 457 ;
    cov:Total_Intensive_Care 44 ;
    cov:Total_Positive_Cases 3211 ;
    cov:Total_Recovered 2153 ;
    cov:Total_Tests_Performed 61241 ;
    cov:Variation_Total_Positive_Cases 1 ;
    cov:refArea dbr:Marche ;
    cov:refTime "2020-05-01T17:00:00"^^xsd:dateTime ;
    qb:dataSet cov:covid19Italy .
```

RDF serialization is provided in [Turtle syntax](https://www.w3.org/TR/turtle/). 
The full dataset for regions and the dataset for provinces will be uploaded soon.


### Licence
The project is licenced under the [Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/deed.it) [(show the licence)](LICENCE)

 
### Contacts
For information or requests, please contact Emanuele Storti - <e.storti@univpm.it>
