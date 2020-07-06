# Vue Parking Garage

A example app using Vue components to search for parking garages in the Netherlands.

## How to use Vue

In this project Vue cli is installed as dev dependency of npm.
To create a new app run `"npx vue create my-app-name"` with default settings.
Then a new folder will appear with a skeleton Vue app.
Go to the folder `"cd my-app-name"` and run the app with Yarn `"npx yarn serve"`
(Or do `npm start` and it will do the above for you)

## Components

- ParkingGarages: contains the whole feature of filtering parking garages
- SearchPlace: contains input field to search for a parking garage by place
- SearchFilter: contains options to filter for parking garage
- ParkingGarageList: contains a list of parking garages
- ParkingGarageItem: contains parking garage information

## Data

- SearchPlace: dynamic data that changes over time (in this case user input)
- SearchFilter: dynamic data that changes over time (in this case user input)
- ParkingGarageList: static data from external source (json)
- ParkingGarageItem: static data from external source (json)

External source is open data from RDW containing parking garage information: [Open Data Parkeren: PARKEERADRES](https://opendata.rdw.nl/Parkeren/Open-Data-Parkeren-PARKEERADRES/ygq4-hh5q)

## Challenge

The challenge is to build with Vue above components with a correct component communication.
That means data flows down with props or data flows up with events between components.
And having the state / data in the correct components.

### Implementation

```
-ParkingGarages
--SearchPlace
--SearchFilter
--ParkingGarageList
---ParkingGarageItem
```

#### ParkingGarages

This (smart) component contains the data of the search, filter and list of parking garages. It only listens to events received from SearchPlace and SearchFilter and when changed it filters the list of parking garages.

#### SearchPlace and SearchFilter

These (dumb) presentational components receive props like place or filter types to handle the inputs and presentation.
After every input change an event is emitted to the parent ParkingGarages.
You could remove the props and add data() to these components, so the data of the component itself is moved from parent to the child.

#### ParkingGarageList and ParkingGarageItem

These (dumb) presentational components only receive props and display it.