#pre-reqs
```
go get github.com/Sirupsen/logrus
go get github.com/clbanning/mxj
go get github.com/mattn/go-colorable
go get github.com/mitchellh/mapstructure
go get github.com/parnurzeal/gorequest
go get gopkg.in/olivere/elastic.v5
```

#build
```
go build
```

#test

```
./promec-indexer -pepxml Unknown-sample_t1.raw.intensity0.charge0comet-human.pep.xml

ESC[36mINFOESC[0m[0000] Promec Indexer started to index file Unknown-sample_t1.raw.intensity0.charge0comet-human.pep.xml 
ESC[36mINFOESC[0m[0001] Indexing Unknown-sample_t1.raw.intensity0.charge0comet-human.pep.xml to elasticserch: http://localhost:9200 index: promec 
[map[num_matched_ions:17 num_tol_term:2 modification_info:map[modified_peptide:GYM[147]VLAIGVALGRLIR mod_aminoacid_mass:map[mass:147.035385 variab
...
...
...
0.000", "spscore_hit_10":"387.1", "sprank_hit_10":"23", "expect_hit_10":"7.53E+01"}
INFO[0008] Successfully indexed data from Unknown-sample_t1.raw.intensity0.charge0comet-human.pep.xml 
```

# promec-indexer

`Promec-Indexer` flattens the Pep XML data format from [Comet](http://comet-ms.sourceforge.net/) and ingest data with correct mapping as applied from `template.go`

You can test it using Docker as

```
docker run -ti -v /path/to/test.pep.xml:/test.pep.xml gurvin/promec-indexer promec-indexer -pepxml /test.pep-xml -host http://elasisearch-host.com:9200
```
