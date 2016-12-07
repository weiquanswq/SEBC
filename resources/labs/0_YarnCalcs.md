#adjustments in YARNCalcs

##work load factor
Work load factor is estimated based on the component required for the use case scenario. 
Eg. Impala is most intensive among Hbase and Solr, work load factor graded as "4"
    Hbase will be "2",and follow by Solr be "1"
    
    
## Reducing OS parameters
Initially, the parameters for OS memory is ```0.1```, I reduced it to ```0.05``` as 6GB should be sufficent.

#Allocationg of Memory to DataNode and Node Manager
Node manager and DataNode shuld be allocated more memory and vcores for more job request and processing power

## Adjusting memory per Container (map/reduce)
Memory per container can be adjusted according to the nature of the use case . If majority of the job is intensive, modify the parameters 
and increase the memory allocation per container and reduce the number of max container

##Reducer and Mapper ratio
Reduce the number of reducers and increase the number of mapper.

(I think) Majority of the jobs will require mapper job but not necessary reducer job.

Eg. teragen / terasort examples
