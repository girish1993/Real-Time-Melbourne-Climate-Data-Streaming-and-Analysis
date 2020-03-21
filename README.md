# Real Time Melbourne Climate Data Streaming & Analysis

<hr />

## Background

With the explosion of data driven applications and the need to get the real time data which determine the functioning of several critical systems around the world, the need for streaming applications is inevitable. Python, being the leading scripting langauge to provide solutions,particulary the data drivem applications by harnessing the wide and varies Python community around the world that produces open source libraries to reach the intended solution more quickly. 

This application is divided into 2 stages:

	- Querying data from the MongoDb Database
	- Simulating the streaming of data, processing incoming streams of data and providing real time insights to the end user.

<hr />

## Querying data from the MongoDb Database

For this stage, we make use of a very popular NoSQL database MongoDB. A NoSql database is more suited for streaming applications as there are no schema constraints as opposed to the relational databases. This makes the task of storing and retrieving the data much easier and all types of data objects can be easily stored which eliminates the need of required fields when it comes to inserting into the database. Additionally the data is stored as <b>JSON Documents</b> which is a standard data format used by all the conventional applications to transfer data between the front end and the back end components of the application. This eliminates the need for a DTO layer in the application whose sole responsibilty is to transfer the structure of the data into a JSON object. The `PyMongo_Querying_Operations.ipynb` talks about all about MongoDb in detail and shows how <i>PyMongo</i> can interact with the database and perform operations.  

<hr />

## Data Streaming & Graphical Analysis

This part of the application deals with streaming data and providing real time analysis of the streamed data. Here is a brief description about the working:

<ul>
	 <li>The streaming part of the application is implemented by <b>Kafka</b> - one of the most popular streaming tool used across several popular platforms and online streaming services like Netflix and the likes. Since we are not dealing with actual data sources, we have simulated these data sources called <b>Kafka Producer</b>. This application employs 3 such producers which stream chunks of data on a particular channel called <i><b>Topics</b></i>.</li> 
	 <li>Components in the application that listen to these topics are called <b>Consumers</b> in this case we call it a Kafka Consumer. This Consumer accepts the incoming data packets. It performs processing in accordance to the business rules. For instance, one of the Business rules in this case is to insert those locations that are in close vicinity to a Fire hotspot. We make use of GIS packages available in Python to perform these checks. Also most of the operations on the incoming data chucks is performed by a python stream processing tool called <b>PySpark</b>. The consumer also maintains an active connection with the MongoDb database and inserts when the business rule is satisfied. </li>
	 <li>Once the data is inserted in the database. These data objects are then fetched using PyMongo operations and real time grahical analysis in terms of <b>Line charts</b> and <b>Geo Spatial charts</b> is produced by a file under the name <i>Real_Time_Data_visualiser.ipynb</i>. This notebook provides real time insights in terms of outlier detection, min and max tagging and several other markings using Matplotlib for a particular time frame. <li>
 </ul>

This constitutes the working of this streaming application. Dockerization of the application would be carried in Version 2 of this application.