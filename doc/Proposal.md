Flight Explorer: Airline, Route, and Flight Reliability Analysis

Project Summary:

Flight Explorer is a web application that allows users to explore flight information, airports, airlines, and flight routes. Users will be able to search for flights based on departure and arrival airports, airline, date, and other characteristics. The application will combine historical flight performance data with airport and airline information to provide users with more information than a basic flight search. Users will be able to view information such as scheduled and actual departure and arrival times, flight delays, cancellations, routes, and airline performance.

The main goal of the application is to help users understand the reliability of different flights, airlines, airports, and routes. Rather than only displaying whether a flight was scheduled, the application will analyze historical flight data to calculate statistics such as average delays, cancellation rates, and the percentage of flights that arrive on time. Users will also be able to save flights or routes that they are interested in and manage their saved information. By combining multiple datasets, the application will provide both flight information and analytical information about air travel.

Creative Component:

The main creative component of Flight Explorer will be an **interactive flight reliability analysis system**. Instead of simply displaying individual flight records, the application will process historical flight data and calculate statistics for airlines, airports, and routes. For example, when a user searches for a route between two airports, the application could calculate the average departure delay, average arrival delay, cancellation percentage, and on-time percentage for that route. Users could then compare multiple airlines operating on the same route.

The application will also provide interactive visualizations based on these calculations. For example, users could view a chart showing how the average delay for an airline changes throughout the day or compare the reliability of several airlines. Another possible visualization would show the most common routes departing from an airport. These visualizations will require the application to retrieve and aggregate data from multiple database tables rather than simply displaying a static dataset.

A second part of the creative component will be combining flight performance information with airport and potentially weather information. This could allow the application to identify relationships between external conditions and flight delays. For example, users could examine whether flights at a particular airport tend to experience more delays during certain weather conditions. This would make the application more than a simple flight lookup tool and allow users to explore patterns in historical flight performance.

Usefulness:

Flight information websites such as Google Flights, Expedia, and airline websites allow users to search for available flights, but these services primarily focus on helping users find and purchase flights. Flight Explorer will have a different focus. Instead of primarily being a flight-booking website, it will focus on **historical flight performance and reliability**. Users will be able to investigate how frequently flights are delayed or canceled and compare airlines, airports, and routes based on their historical performance.

The basic functionality of the application will allow users to search for airports, airlines, flights, and routes. Users will be able to filter flight records based on departure airport, arrival airport, airline, date, and delay status. The application will also allow users to view aggregate statistics, such as an airline's average delay or an airport's cancellation rate. Users will be able to create accounts and save flights or routes that they are interested in. Saved information can then be updated or deleted by the user.

For example, a user planning a trip from Chicago to New York could search for flights between the two locations and compare the historical performance of different airlines. The user could see that one airline has a lower average delay but another airline has more available routes. This gives users additional information that is not necessarily available from a traditional flight search.

The application will also be useful for users who are interested in analyzing aviation data rather than planning a specific trip. A user could search for a particular airport and investigate which airlines operate there, which destinations are most common, and what the historical delay rate is. Therefore, the application can serve both casual users interested in flight information and users interested in exploring transportation data.

Realness:

The project will use the flights dataset from kaggle [https://www.kaggle.com/datasets/mahoora00135/flights](https://www.kaggle.com/datasets/mahoora00135/flights). The dataset is in .csv format. It contains 336, 775 rows and 21 columns.

