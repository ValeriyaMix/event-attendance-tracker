# event-attendance-tracker
This project is an Event Attendance Tracker for the WCC community.

The requirements for the functionality of the project are provided here: https://github.com/Women-Coding-Community/java-bootcamp/blob/main/docs/PROJECT_IDEAS.md#2-event-attendance-tracker

The project will be implemented as a RESTful API using the Spring Boot framework (Java 17).
Data persistence will be handled using a PostgreSQL database.

# APIs end-points


## POST /events

This end-point will record event details (name, date, location, description)

Request payload:
{
  "name": "Community Meetup",
  "date": "2026-03-01",
  "location": "Online",
  "description": "Spring Boot Workshop"
}


## POST /events/{id}/registrations

This end-point will track attendee check-ins

Request payload:
{
  "email": "john@email.com",
  "firstName": "John",
  "lastName": "Doe"
}


## POST /events/{id}/attendance

This end-point will track attendee attendance

Request payload:
{
  "email": "john@email.com"
}


## GET /events/{id}/statistics

This end-point will calculate attendance statistics

Response payload: TBD

## GET /events/{id}/report

This end-point will generate attendance reports

Response payload: TBD


# Database tables

## EVENTS

- id
- name
- date
- location
- description

## ATTENDEES 

- id
- email
- firstName
- lastName

## EVENT_REGISTRATIONS

- id
- eventId
- attendeeId
- status [Registered, Waitlisted, Cancelled]
- attended [true, false]
- timestamps
