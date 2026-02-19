# Hotel Booking API - Airbnb-Style Backend

A scalable backend system for hotel booking with dynamic inventory management, pricing engine, and secure payment processing.

**Author:** Tirth Shah | [LinkedIn](https://linkedin.com/in/tirth-shah-a724701b7) | [GitHub](https://github.com/TirthShahh28)

## Tech Stack

- **Backend:** Java 23, Spring Boot 3.4, Spring Security
- **Database:** PostgreSQL with JPA/Hibernate
- **Authentication:** JWT (Access + Refresh Tokens)
- **Payments:** Stripe API with Webhooks
- **Documentation:** Swagger/OpenAPI
- **Deployment:** Docker, Railway

## Key Features

- **Dual-Token JWT Authentication** - Secure access and refresh token system
- **Pessimistic Locking** - Prevents double-booking race conditions
- **Dynamic Pricing Engine** - Strategy pattern for surge, holiday, and occupancy-based pricing
- **Booking State Machine** - RESERVED → CONFIRMED → CANCELLED lifecycle
- **Stripe Integration** - Secure payment processing with webhook verification
- **Scheduled Jobs** - Automated cleanup of abandoned bookings

![Image](https://github.com/user-attachments/assets/585136d9-05b5-4832-ad37-0a47d4678433)

## API Endpoints

### Admin Inventory

- **GET** `/admin/inventory/rooms/{roomId}` - Retrieve inventory of a room
- **PATCH** `/admin/inventory/rooms/{roomId}` - Update inventory for a room
- **PUT** `/admin/hotels/{hotelId}/rooms/{roomId}` - Update a room

### Booking Flow

- **GET** `/bookings/{bookingId}/status` - Check booking status
- **GET** `/admin/hotels/{hotelId}/reports` - Generate hotel booking report
- **GET** `/admin/hotels/{hotelId}/bookings` - Get all bookings
- **POST** `/bookings/{bookingId}/payments` - Initiate payment
- **POST** `/bookings/{bookingId}/cancel` - Cancel a booking
- **POST** `/bookings/{bookingId}/addGuests` - Add guests to a booking
- **POST** `/bookings/init` - Initialize a new booking

### Booking Guests

- **DELETE** `/users/guests/{guestId}` - Remove a guest
- **GET** `/users/guests` - Get my guests
- **POST** `/users/guests` - Add a guest
- **PUT** `/users/guests/{guestId}` - Update a guest

### Hotel Browse

- **GET** `/hotels/{hotelId}/info` - Get hotel details
- **GET** `/hotels/search` - Search for hotels

### Hotel Management

- **DELETE** `/admin/hotels/{hotelId}` - Delete a hotel
- **GET** `/admin/hotels/{hotelId}` - Get hotel by ID
- **GET** `/admin/hotels` - Get all admin hotels
- **PATCH** `/admin/hotels/{hotelId}/activate` - Activate a hotel
- **POST** `/admin/hotels` - Create a hotel
- **PUT** `/admin/hotels/{hotelId}` - Update hotel details

### Room Admin Management

- **DELETE** `/admin/hotels/{hotelId}/rooms/{roomId}` - Delete a room
- **GET** `/admin/hotels/{hotelId}/rooms/{roomId}` - Get room details
- **GET** `/admin/hotels/{hotelId}/rooms` - Retrieve all rooms
- **POST** `/admin/hotels/{hotelId}/rooms` - Create a room
- **PUT** `/admin/hotels/{hotelId}/rooms/{roomId}` - Update a room

### User Authentication

- **POST** `/auth/signup` - User signup
- **POST** `/auth/refresh` - Refresh access token
- **POST** `/auth/login` - User login

### User Profile

- **DELETE** `/users/guests/{guestId}` - Remove a guest
- **GET** `/users/guests` - Get my guests
- **GET** `/users/profile` - Get my profile
- **GET** `/users/myBookings` - Get my bookings
- **PATCH** `/users/profile` - Update my profile
- **POST** `/users/guests` - Add a guest
- **PUT** `/users/guests/{guestId}` - Update a guest

### Webhook

- **POST** `/webhook/payment` - Capture payments

###Schema
![Image](https://github.com/user-attachments/assets/bc209296-e0f2-48f9-a7ae-65d084e4cb6c)
