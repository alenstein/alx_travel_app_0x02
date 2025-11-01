# alx_travel_app_0x00

This project is a travel application built with Django. It provides a database schema for managing property listings, bookings, and reviews.

## Features

*   **Database Models**: `Listing`, `Booking`, and `Review` models to store application data.
*   **API Serializers**: `ListingSerializer` and `BookingSerializer` for data representation in the API.
*   **Database Seeder**: A management command to populate the database with sample listings.

## Setup

1.  **Clone the repository:**
    ```bash
    git clone <repository-url>
    ```
2.  **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```
3.  **Apply migrations:**
    ```bash
    python manage.py migrate
    ```

## Database Seeding

To populate the database with sample data, run the following command:

```bash
python manage.py seed
```

This will create a few sample listings in the database.

## Models

### Listing

*   `title`: `CharField`
*   `description`: `TextField`
*   `price`: `DecimalField`
*   `address`: `CharField`
*   `country`: `CharField`
*   `city`: `CharField`

### Booking

*   `listing`: `ForeignKey` to `Listing`
*   `guest`: `ForeignKey` to `User`
*   `check_in_date`: `DateField`
*   `check_out_date`: `DateField`
*   `num_guests`: `PositiveIntegerField`

### Review

*   `listing`: `ForeignKey` to `Listing`
*   `guest`: `ForeignKey` to `User`
*   `rating`: `PositiveIntegerField`
*   `comment`: `TextField`

## Serializers

### ListingSerializer

Serializes all fields of the `Listing` model.

### BookingSerializer

Serializes all fields of the `Booking` model.
