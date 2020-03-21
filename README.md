# Real-Time-Melbourne-Climate-Data-Streaming-and-Analysis

<hr />

## Background

With the explosion of data driven applications and the need to get the real time data which determine the functioning of several critical systems around the world, the need for streaming applications is inevitable. Python, being the leading scripting langauge to provide solutions,particulary the data drivem applications by harnessing the wide and varies Python community around the world that produces open source libraries to reach the intended solution more quickly. 

This application is divided into 2 stages:

	- Querying data from the MongoDb Database
	- Simulating the streaming of data, processing incoming streams of data and providing real time insights to the end user.

<hr />

## Querying data from the MongoDb Database

For this stage, we make use of a very popular NoSQL database MongoDB. A NoSql database is more suited for streaming applications as there are no schema constraints as opposed to the relational databases. This makes the task of storing and retrieving the data much easier and all types of data objects can be easily stored which eliminates the need of required fields when it comes to inserting into the database. Additionally the data is stored as <b>JSON Documents</b> which is a standard data format used by all the conventional applications to transfer data between the front end and the back end components of the application. This eliminates the need for a DTO layer in the application whose sole responsibilty is to transfer the structure of the data into a JSON object. The `PyMongo_Querying_Operations.ipynb` talks about all about MongoDb in detail and shows how <i>PyMongo</i> can interact with the database and perform operations.  
