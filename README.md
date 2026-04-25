# Travlr Getaways Full Stack Reflection

## Architecture

### Frontend Development: Express HTML vs. Angular SPA

The customer-facing side of the Travlr Getaways app uses Express, Handlebars, HTML, CSS, and JavaScript to build pages on the server. This works well for the public site because users mainly need to view travel information and browse trips.

The admin side uses Angular as a single-page application, which fits better for tasks like adding, editing, and managing trips. Angular organizes the frontend into components, services, models, and routes, while Express is set up with routes, controllers, views, and server-side rendering.

### Backend Database: MongoDB and NoSQL

MongoDB was a good fit for this project because the trip data works well as document-style records. Each trip has fields like `code`, `name`, `length`, `start`, `resort`, `perPerson`, `image`, and `description`, which fit naturally into JSON-like documents.

Mongoose adds structure to the NoSQL database by using schemas and models. This helps keep the data organized while still allowing the flexibility of MongoDB.

## Functionality

### JSON and Full Stack Data Flow

JSON is a data format, while JavaScript is a programming language. In this project, JSON connects the frontend and backend by carrying trip and user data between Angular, Express, and MongoDB.

The API sends back JSON from the database, and Angular uses it to show trips, fill out forms, and send updates. This makes JSON the main communication format across the full stack application.

### Refactoring and Reusable Components

One example of refactoring was switching from static HTML trip content to dynamic templates and API-based data. The project also refactored repeated Angular code by turning it into reusable components like `trip-card`.

Reusable UI components made the admin side easier to manage because the same component could show trip information in different places without rewriting code. Services like `TripDataService` also helped by keeping API calls in one place instead of spreading them across multiple components.

## Testing

### API and Endpoint Testing

I tested the backend API with Postman before depending on the Angular frontend. I checked `GET` requests for retrieving trips, `POST` requests for adding trips and logging in, and `PUT` requests for updating trips.

Testing the API on its own helped confirm that the Express routes, controllers, Mongoose models, and MongoDB database were all working correctly. I also used MongoDB Compass to make sure that changes were actually saved in the database.

### Security Testing

Security made testing more complex because protected endpoints needed a valid JSON Web Token. Instead of just sending a request in Postman, I had to log in first, copy the token, and include it as an `Authorization: Bearer <token>` header.

In Angular, the authentication service and JWT interceptor helped manage this automatically. This showed how authentication affects everything from the backend API to the frontend user interface.

## Reflection

This course helped me understand how a full stack application works as a connected system. I learned how a browser action can move through an Angular component, API service, Express route, Mongoose model, and MongoDB, and then return data back to the user interface.

That kind of understanding helps me move toward entry-level software engineering or application development roles because I can better explain how frontend, backend, database, API, and authentication layers work together.

The main skills I developed in this course include Node.js, Express, Angular, TypeScript, MongoDB, Mongoose, REST API design, JSON data handling, Postman testing, GitHub version control, and JWT authentication. I also gained more practice debugging issues across multiple layers of an application instead of only looking at one file or one error message.

The biggest professional takeaway is that maintainable structure matters just as much as working code. Separating responsibilities into routes, controllers, models, components, services, and authentication utilities made the project easier to understand, test, and improve.
