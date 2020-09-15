
## Encoding and Evolution

Json 

* cannot distinguish integer and floating-point numbers and there is no precision
* doesn't support binary strings - sequence of bytes without any encoding

 Binary encodings of Json - MessagePack, BSON, BJSON, UBJSON, BISON, and Smile, to name a few

 What is the space saved for ProtoBuf compared to Json


Document databases 
* Doesn't nicely handle one-to-many information because you cannot do joins in db but have to do in application layer
* Schema flexibility due to storage locality

Network model - one record could have multiple parents - to represent both one-to-many and many-to-many relationships


Schema-on-read vs schema-on-write
	* 1 is advantageous when the schema is changing



Locality in Spanner, Oracle (Multi table  index cluster tables), Bigtable data model

Document reference in MongoDB
Mongodb offers MapReduce
Triple stores


