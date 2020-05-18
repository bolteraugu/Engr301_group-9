### 3.4 Performance requirements

How often the position of the rocket is updated on the map<br>
This can be a tick-based update where each tick can be a specified 
number of milliseconds say 500ms for example. Every 500ms, the positional data
of the rocket can be retrieved and then be processed at mission control to
be then displayed on the map. At a tick rate of 500ms, the rockets position will be
updated 120 times over the course of 1 minute. 
The latency between the rocket and mission control will need to be considered. As the rocket
travels further away, the connection is likely to get weaker, so a variable tick-rate may be considered. 

No 'go' given on failure probabilities of greater than X%
As part of our go no go functionality, we will be calculating a probability of failure based on current conditions. 
These conditions can range from the current weather (i.e. wind speed or temperature) to the strength of the connection between 
the rocket and mission control. Each condition could be given weights (that are calibrated beforehand) which signify their 
overall impact as a cause of failure during the rocket launch. 
We will set a probability threshold at a value that will be decided in the future. If the probability of failure is greater than or equal
to our predefined threshold, then the rocket will be given the "no go", signifying that the chance of failure is too high.  

Number of Simultaneous users
Each program will support one user. However our system will support multiple instances running simultaneously. 

Amount and Type of Information to be handled 
*What type of data will be sent/recieved from the rocket to mission control while its in flight? I.e. JSON?*

See 9.5.13. for most systems this will be around one page. Hardware projects also see section 9.4.6.

> **9.5.13 Performance requirements** <br>
> Specify both the static and the dynamic numerical requirements placed on the software or on human interaction with the software as a whole. 
> 
> Static numerical requirements may include the following:
> 
> a) The number of terminals to be supported;  
> b) The number of simultaneous users to be supported;  
> c) Amount and type of information to be handled.
> 
> Static numerical requirements are sometimes identified under a separate section entitled Capacity.
> 
> Dynamic numerical requirements may include, for example, the numbers of transactions and tasks and the amount of data to be processed within certain time periods for both normal and peak workload conditions. The performance requirements should be stated in measurable terms.
> 
>  For example, "_95 % of the transactions shall be processed in less than 1 second._" rather than, "An operator shall not have to wait for the transaction to complete."
> 
> NOTE Numerical limits applied to one specific function are normally specified as part of the processing subparagraph description of that function.