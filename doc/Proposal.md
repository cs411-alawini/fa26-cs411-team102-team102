# Flight Explorer: Airline, Route, and Flight Reliability Analysis

## Project Summary

Flight Explorer is a web application that allows users to explore flight information, airports, airlines, and flight routes. Users will be able to search for flights based on departure and arrival airports, airline, date, and other characteristics. The application will combine historical flight performance data with airport and airline information to provide users with more information than a basic flight search. Users will be able to view information such as scheduled and actual departure and arrival times, flight delays, cancellations, routes, and airline performance.

The main goal of the application is to help users understand the reliability of different flights, airlines, airports, and routes. Rather than only displaying whether a flight was scheduled, the application will analyze historical flight data to calculate statistics such as average delays, cancellation rates, and the percentage of flights that arrive on time. 
In addition to analyzing individual flights and routes, the application will allow users to analyze the reliability of connecting flights. For example, a user considering a flight with a 55-minute layover could examine how frequently historical delays on the first flight would reduce the available connection time to less than 45, 30, or 15 minutes. This allows users to better understand the potential risk associated with different connecting flights.

Users will also be able to save flights or routes that they are interested in and manage their saved information. By combining multiple datasets, the application will provide both flight information and analytical information about air travel.

## Creative Component

The main creative component of Flight Explorer will be an **interactive flight reliability analysis system**. Instead of simply displaying individual flight records, the application will process historical flight data and calculate statistics for airlines, airports, and routes. For example, when a user searches for a route between two airports, the application could calculate the average departure delay, average arrival delay, cancellation percentage, and on-time percentage for that route. Users could then compare multiple airlines operating on the same route.

The reliability analysis system will also support connecting flights. Users will be able to specify two flight segments and a planned layover time. Using historical arrival delays from the first segment, the application will calculate how frequently those delays would significantly reduce the amount of time available for the connection. For example, the system could determine how frequently a 60-minute scheduled layover would historically have been reduced to less than 45, 30, or 15 minutes, allowing users to be able to determine if this flight layover time will affect them in any way.

The application will also provide interactive visualizations based on these calculations. For example, users could view a chart showing how the average delay for an airline changes throughout the day or compare the reliability of several airlines. Another possible visualization would show the most common routes departing from an airport. These visualizations will require the application to retrieve and aggregate data from multiple database tables rather than simply displaying a static dataset.

A second part of the creative component will be combining flight performance information with airport and potentially weather information. This could allow the application to identify relationships between external conditions and flight delays. For example, users could examine whether flights at a particular airport tend to experience more delays during certain weather conditions. This would make the application more than a simple flight lookup tool and allow users to explore patterns in historical flight performance.

## Usefulness

Flight information websites such as Google Flights, Expedia, and airline websites allow users to search for available flights, but these services primarily focus on helping users find and purchase flights. Flight Explorer will have a different focus. Instead of primarily being a flight-booking website, it will focus on **historical flight performance and reliability**. Users will be able to investigate how frequently flights are delayed or canceled and compare airlines, airports, and routes based on their historical performance. Historical reliability can also be useful when evaluating connecting flights. A connection that appears reasonable based on scheduled arrival and departure times may provide significantly less connection time if the first flight is frequently delayed. Flight Explorer will allow users to evaluate how historical delays could affect the amount of time available to make a planned connection.

The basic functionality of the application will allow users to search for airports, airlines, flights, and routes. Users will be able to filter flight records based on departure airport, arrival airport, airline, date, and delay status. The application will also allow users to view aggregate statistics, such as an airline's average delay or an airport's cancellation rate. Users will be able to create accounts and save flights or routes that they are interested in. Saved information can then be updated or deleted by the user.

For example, a user planning a trip from Chicago to New York could search for flights between the two locations and compare the historical performance of different airlines. The user could see that one airline has a lower average delay but another airline has more available routes. This gives users additional information that is not necessarily available from a traditional flight search. Similarly, a user considering a connecting flight could provide the planned layover time and examine how delays on the first flight have historically affected the amount of time remaining before the second flight's scheduled departure.

The application will also be useful for users who are interested in analyzing aviation data rather than planning a specific trip. A user could search for a particular airport and investigate which airlines operate there, which destinations are most common, and what the historical delay rate is. Therefore, the application can serve both casual users interested in flight information and users interested in exploring transportation data.

## Realness

The project will use datasets from the U.S. Department of Transportation's Bureau of Transportation Statistics (BTS).

### Dataset 1

The first dataset (BTS) will use flight records from Janurary 2025 (month is subjected to change). This dataset will take the flight records and information such as flight dates, airlines, flight numbers, origin and destination airports, scheduled and actual departure and arrival times, delays, cancellations, diversions, flight distances, and reported causes of delays. The dataset is provided as a CSV.

#### Dataset 1 Information

- Source: U.S. Department of Transportation, Bureau of Transportation Statistics
- Format: CSV
- Cardinality: 599014
- Degree: 120
- Time Period: January 2025

### Dataset 2

This dataset (DCB1) will have information describing individual segments of sampled passenger itineraries, including segment origins and destinations, airlines, and identifiers connecting segments to passenger flights. This information can help the application identify realistic multi-segment travel patterns and airport connections.

#### Dataset 2 Information

- Source: U.S. Department of Transportation, Bureau of Transportation Statistics
- Format: CSV
- Cardinality: 126458 
- Degree: 39
- Time Period: July 2025


## Functionality 

Users will be able to search historical flights based on the departered and arrival airports, airline, date/time period, and characteristics that made the delay. The application will take information and calculate aggregated statisitics. 

Users will also be able to analyze connecting flights by providing multiple flight segments and will use it to analyze possible delays so users can use it to see how much time they may actually have on a connecting flight to make it to another gate.

Users will be able to do the following:

- **Insert/Create:** Save a flight, route, or connecting flights.
- **Read:** View saved flights, routes, connecting flights, and reliability information.
- **Update:** Modify information associated with a saved route or connecting flight, such as the planned layover time.
- **Delete:** Remove a saved flight, route, or connecting flight.
- **Search:** Search and filter historical flight information by airport, airline, route, date, and delay characteristics.

## Low-Fidelity UI Mockup

My markdown UI mockup from my sketchs.

### Flight / Route Search

```text
+------------------------------------------------------------------+
|                         FLIGHT EXPLORER                          |
+------------------------------------------------------------------+
|                                                                  |
|  From:              To:                Airline:                  |
|  [ ORD        ]     [ LAX        ]     [ Any Airline      v ]    |
|                                                                  |
|  Date / Period:                                                  |
|  [ January 2025 ]                         [ Search Flights ]     |
|                                                                  |
+------------------------------------------------------------------+
|                    ROUTE RELIABILITY                             |
+------------------------------------------------------------------+
|                                                                  |
|  ORD -> LAX                                                      |
|                                                                  |
|  Average Delay:        __ min                                    |
|  On-Time Percentage:   __%                                       |
|  Cancellation Rate:    __%                                       |
|  30+ Minute Delays:    __%                                       |
|                                                                  |
|  Airline Comparison                                              |
|                                                                  |
|  United       [===============     ] __% On Time                 |
|  American     [==============      ] __% On Time                 |
|  Southwest    [================    ] __% On Time                 |
|                                                                  |
|                         [ Save Route ]                           |
+------------------------------------------------------------------+
```

### Connection Analysis

```text
+------------------------------------------------------------------+
|                     CONNECTION ANALYSIS                          |
+------------------------------------------------------------------+
|                                                                  |
|  Origin          Connection Airport          Destination         |
|  [ CMI ]    ->        [ ORD ]          ->       [ LAX ]          |
|                                                                  |
|  Planned Layover: [ INSERT ] minutes                             |
|                                                                  |
|                      [ Analyze Connection ]                      |
|                                                                  |
+------------------------------------------------------------------+
|                 HISTORICAL CONNECTION ANALYSIS                   |
+------------------------------------------------------------------+
|                                                                  |
|  CMI -> ORD -> LAX                                               |
|  Planned Layover: __ minutes                                     |
|                                                                  |
|  Historical first-leg delays would leave:                        |
|                                                                  |
|  More than __ min       [====================]  65%              |
|  __ - __ min            [========            ]  20%              |
|  __ - __ min            [====                ]  10%              |
|  Less than __ min       [==                  ]   5%              |
|                                                                  |
|  Avg. First-Leg Delay: __ min                                    |
|  Cancellation Rate:    __%                                       |
|                                                                  |
|                      [ Save Itinerary ]                          |
+------------------------------------------------------------------+
```

### Saved Routes / Itineraries

```text
+------------------------------------------------------------------+
|                       MY SAVED TRIPS                             |
+------------------------------------------------------------------+
|                                                                  |
|  ORD -> LAX                                                      |
|  Saved Route                                                     |
|  [ View Analysis ]    [ Edit ]    [ Delete ]                     |
|                                                                  |
|  CMI -> ORD -> LAX                                               |
|  __-minute connection                                            |
|  [ View Analysis ]    [ Edit ]    [ Delete ]                     |
|                                                                  |
+------------------------------------------------------------------+
```

## Project Distribution

### Ravi
- BTS On-Time Performance data preprocessing and import
- Flight, airline, airport, and route database tables
- Flight and route search queries
- Reliability calculations such as average delays, cancellation rates, and on-time percentages
- Backend endpoints for flight and route searches

### Adrian
- DB1C Segment data preprocessing and import
- Itinerary and connection-related database tables
- Connection analysis queries and calculations
- Backend endpoints for connection analysis
- Connection analysis visualizations

### Davi
- User/account and saved itinerary database tables
- Insert, update, delete, and retrieval functionality for saved information
- User-related backend endpoints
- Frontend interface and search forms
- Frontend/backend integration and reliability visualizations

All team members will collaborate on database schema design, testing, documentation, integration, and deployment.
