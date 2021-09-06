# Mathematical_Models

Process Modelling



Problem description and mathematical formulation

The multi-depot multi-trip vehicle routing problem with time windows (MD-MT-VRPTW) that the dissertation examines can be defined as follows. Let  be the network graph of the problem, where  is the set of the vertices which includes a set of depot location  and a set of customer location , and  is the set of arcs between two vertices in set V. Every arc  in set E has travel cost  and travel time .  is the set of all the vehicles, which are distributed at the depot locations they belong to. For each vehicle , multiple trips can be made within daily working hours  and the maximum volume of oil to be collected per vehicle is . Each trip for each vehicle will be coded and recorded in set , representing the trips made by each vehicle. For each customer , each has their own daily opening time  and closing time . Also, each customer has their order quantity for oil  and a vehicle will spend service time  to complete the oil recovery after arriving at the customer's location. When the vehicle returns to the depot, additional time  is required to store the recovered oil from the vehicle at the depot location. When the customer submits an order, a desired lead time , preferred date  and closing date  are given. During a vehicle's trip, the vehicle starts from the depot and ends at the depot. However, if the time that vehicle returns to the depot after servicing a customer exceeds the rest of the day's working hours, the vehicle will end the trip at that customer's location for an overnight stay and start the trip at the customer's location on the next day. The vehicle will incur an overnight cost  for each overnight stay and the overnight situation will only occur on the vehicle's last trip of the day.
The aim of MD-MT-VRPTW is to schedule the daily trips of vehicles within the maximum lead time of all customers  and to minimize the total travel and overnight costs. In addition, the following conditions need to be satisfied:

```
PARAMETERS
```

(1) Each customer should only be served once
(2) Two consecutive trips on the same vehicle cannot overlap
(3) Vehicle  needs to arrive at customer 's location after the opening time  and before the closing time
(4) The total amount of oil recovered from the customer between the time the vehicle leaves the depot and the next time it returns to the depot cannot exceed the total capacity of the vehicle .
(5) Vehicle  needs to complete the customer's order within the defined number of working days .
(6) Vehicle  needs to finish the customer’s order on the preferred date  and to avoid servicing the customer on the closing date .

```
The notations and mathematical formulation of the MD-MT-VRPTW are introduced as follows:
```

Sets and Indices
Set of depots
Set of customers
Set of vehicles
Set of trips for each vehicle
Date that vehicle work
Index of Vertices belong to M∪N
Index of a Vehicle
Index of a Trip
Index of date

Parameters
Opening time at customer i
Closing time at customer i
Lead time of customer i
Preferred date of customer i
Closed date of customer i
Travel cost between Vertices i and Vertices j
Travel time between Vertices i and Vertices j
Order quantity of customer i
Capacity of Vehicle
Service time of customer i
Service time of depot
Working time horizon of vehicle
O	Overnight cost

Decision Variables
Binary variable equal to 1 if vehicle  visit vertices after visiting vertices in trip  at date , otherwise equal to 0
Binary variable equal to 1 if vehicle  visit vertices  in trip  at date , otherwise equal to 0
Binary variable equal to 1 if vehicle  responsible for trip , otherwise equal to 0
Binary variable equal to 1 if the start location of trip serve by vehicle  is not depot location at date , otherwise equal to 0
Binary variable equal to 1 if vehicle  should overnight at the end of trip  at date , otherwise equal to 0
Binary variable equal to 1 if the first customer in trip  by vehicle  is customer at date , otherwise equal to 0
Binary variable equal to 1 if the last customer in trip  by vehicle  is customer  at date , otherwise equal to 0
Binary variable equal to 1 if vehicle  belongs to depot
Time point that vehicle  arrive customer  in trip  at date
Time point that vehicle  start trip  at date
Time point that vehicle  end trip w at date
Time point that vehicle  start to work at date
Time point that vehicle  end the work at date
Date that customer is served

Objective Function

```
(1)
```

Subject to
(2)
(3)
(4)

```
k<

(5)
(6)

(7)
(8)
(9)

(10)
(11)
(12)
(13)

(14)

(15)

(16)

(17)

(18)
(19)

(20)
(21)
(22)
(23)
(24)
(25)
(26)
(27)
(28)
(29)
(30)

The objective function (1) minimize the total travel cost and the overnight cost of all the trips. Constraint (2) ensure that each customer is served only once. Constraint (3) guarantee that only one vehicle is responsible for each journey. Constraint (4) ensure that vehicle  has performed trip  before it will perform trip . Constraint (5) guarantee that trips which do not start and end at the customer's location start from the depot and return to the depot at the end of the trip. Constraint (6) ensure that total volume of oil recovered in trips which do not start and end at the customer's location should not exceed the vehicle capacity . Constraint (7) ensure that the volume of oil recovered in the vehicle  does not exceed the vehicle capacity before vehicle  returning to the depot. Constraint (8)(9) that the first customer of a trip and the last customer of a trip are included in the trip schedule. Constraint (10) explain the relationship between the destination of the overnight trip of vehicle  and the start point of the first trip on the next day. Constraint (11)(12) ensure that vehicle k arrives at customer i within the operating hours of customer i. Constraint (13) address the time relationship between two consecutive trips of vehicle k in the same date. Constraint (14) address the time relationship between two consecutive customer i and j in trip w. Constraint (15)(16) illustrates the conditions to be met by vehicle k to overnight. Constraint (17)-(20) address the time relationship of trip starting time and trip ending time in different scenario. Constraint (21) address the time relationship between the starting time of trip and the starting time of the day in the same vehicle. Constraint (22) address the time relationship between the ending time of trip and the ending time of the day in the same vehicle. Constraint (23) is the daily working time constraint of a vehicle. Constraint (24)-26) is the date constraint of lead time, preferred date and closing date. Constraint (27)-(30) is the binary constraint of decision variables.
```
