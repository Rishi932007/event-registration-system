# UniEvents – Event Registration System

A basic event registration web app built using Flask and Google Cloud services.

---

## Features

* Register for events through a form
* Store data in Firestore
* Publish registration data to Pub/Sub
* Simple admin panel to view registrations

---

## Tech Stack

* Python (Flask)
* Google Cloud Run
* Firestore
* Cloud Pub/Sub

---

## Project Structure

```
.
├── app_cloud.py
├── templates/
├── static/
├── Dockerfile
├── requirements.txt
```

---

## Setup

### 1. Set environment variables

```
GCP_PROJECT_ID=your-project-id
PUBSUB_TOPIC=event-registrations
SECRET_KEY=your-secret-key
```

---

### 2. Enable required services

* Firestore
* Cloud Run
* Pub/Sub

---

### 3. Create Pub/Sub topic

```
event-registrations
```

---

### 4. IAM Permissions

Give your service account:

* Pub/Sub Publisher
* Firestore access (Datastore User or similar)

---

## Run locally

```
docker build -t unievents .
docker run -p 8080:8080 unievents
```

---

## Deploy

```
gcloud builds submit --tag gcr.io/PROJECT_ID/unievents
gcloud run deploy unievents \
  --image gcr.io/PROJECT_ID/unievents \
  --platform managed \
  --allow-unauthenticated
```

---

## Admin

* Route: `/admin`
* Password: `1234`

---

## Notes

* Change the admin password before production
* Make sure Pub/Sub topic name matches your code

---

## Author

Rishi Shah
