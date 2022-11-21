# pulsar-transit-pinot
Apache Pinot - Apache Pulsar - Transit Data


````

{companyname=transcom, advisoryAlert=NULL, link=https://www.511nj.org/home, description=NYSDOT - Region 3: Construction , bridge work on NY 5 eastbound between I-481 SB Ramp (De Witt) and I-481 NB Ramp (De Witt) 1 Right lane of 2 lanes closed until 3:00 PM, guid=43.034178,-76.062942, servicename=transcom, title=NY 5 eastbound:Construction, pubDate=2022-10-20T09:00:06, uuid=b778a1de-519a-4f60-bd34-c1b212784971, ts=1666291837244}

{companyname=newjersey, advisoryAlert=NULL, link=https://www.njtransit.com/node/1523434, description=Bus Route Nos. 313, 315, 316*, 317, 408 & 409: Bus Service Changes in Philadelphia – Saturday, June 25, 2022, guid=Philadelphia, servicename=bus, title=BUS 408 - Jun 20, 2022 11:01:56 AM, pubDate=Jun 20, 2022 11:01:56 AM, uuid=309f32c7-e5e5-41d0-b6c6-37ba00aac8d3, ts=1667572441233}


````

#### Convert

````

bin/pinot-admin.sh JsonToPinotSchema \
  -timeColumnName ts \
  -metrics "number_of_episodes,popularity"\
  -dimensions "" \
  -pinotSchemaName=transit \
  -jsonFile=/data/transit.json \
  -outputDir=/config

````


#### References

* https://dev.startree.ai/docs/pinot/recipes/infer-schema-json-data
* https://github.com/startreedata/pinot-recipes/blob/main/recipes/json-nested/README.md
