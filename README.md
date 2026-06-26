# Smart Animal Rescue & Adoption Platform 🐾

**Description:** Report injured animals with GPS, connect with nearby volunteers, adopt pets, donate, and access emergency contacts. Full-stack app with Spring Boot + React + MySQL.

## Features

- **Report Injured Animals**: Report injured or stray animals with location tracking
- **Volunteer Network**: Nearby volunteers receive notifications when animals are reported
- **Animal Adoption**: Browse and adopt animals from partner shelters
- **Donation System**: Support the cause through donations
- **Emergency Contacts**: Quick access to animal rescue organizations

## Technologies

### Backend
- Java 17
- Spring Boot 3.2.0
- Spring Data JPA
- MySQL 8.0

### Frontend
- React 18
- React Router
- Axios
- CSS3

## Project Structure

```
Animal adopted/
├── backend/
│   ├── src/
│   │   └── main/
│   │       ├── java/com/animalrescue/
│   │       │   ├── AnimalRescueApplication.java
│   │       │   ├── config/
│   │       │   ├── controller/
│   │       │   ├── entity/
│   │       │   ├── repository/
│   │       │   └── service/
│   │       └── resources/
│   │           └── application.properties
│   └── pom.xml
└── frontend/
    ├── public/
    │   └── index.html
    ├── src/
    │   ├── components/
    │   │   ├── Adoption.js
    │   │   ├── Donate.js
    │   │   ├── EmergencyContacts.js
    │   │   ├── Home.js
    │   │   ├── ReportAnimal.js
    │   │   └── Volunteer.js
    │   ├── App.js
    │   ├── App.css
    │   ├── index.js
    │   └── index.css
    └── package.json
```

## Setup Instructions

### Prerequisites

- Java 17 or higher
- Maven 3.6+
- Node.js 16+
- MySQL 8.0+
- npm or yarn

### Backend Setup

1. **Navigate to backend directory**
   ```bash
   cd backend
   ```

2. **Configure MySQL Database**
   - Install MySQL 8.0+
   - Create a database named `animal_rescue` (or update the URL in `application.properties`)
   - Update database credentials in `src/main/resources/application.properties`:
     ```properties
     spring.datasource.url=jdbc:mysql://localhost:3306/animal_rescue?createDatabaseIfNotExist=true
     spring.datasource.username=your_username
     spring.datasource.password=your_password
     ```

3. **Build the project**
   ```bash
   mvn clean install
   ```

4. **Run the application**
   ```bash
   mvn spring-boot:run
   ```
   
   The backend will start on `http://localhost:8080`

### Frontend Setup

1. **Navigate to frontend directory**
   ```bash
   cd frontend
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Start the development server**
   ```bash
   npm start
   ```
   
   The frontend will start on `http://localhost:3000`

## API Endpoints

### Animal Reports
- `GET /api/reports` - Get all reports
- `GET /api/reports/{id}` - Get report by ID
- `POST /api/reports` - Create new report
- `PUT /api/reports/{id}` - Update report
- `DELETE /api/reports/{id}` - Delete report
- `GET /api/reports/pending` - Get pending reports
- `GET /api/reports/type/{animalType}` - Get reports by animal type

### Animal Adoptions
- `GET /api/adoptions` - Get all animals
- `GET /api/adoptions/{id}` - Get animal by ID
- `POST /api/adoptions` - Add new animal
- `PUT /api/adoptions/{id}` - Update animal
- `DELETE /api/adoptions/{id}` - Delete animal
- `GET /api/adoptions/available` - Get available animals
- `GET /api/adoptions/type/{animalType}` - Get animals by type
- `POST /api/adoptions/{id}/adopt` - Adopt an animal

### Volunteers
- `GET /api/volunteers` - Get all volunteers
- `GET /api/volunteers/{id}` - Get volunteer by ID
- `POST /api/volunteers` - Register new volunteer
- `PUT /api/volunteers/{id}` - Update volunteer
- `DELETE /api/volunteers/{id}` - Delete volunteer
- `GET /api/volunteers/available` - Get available volunteers
- `GET /api/volunteers/location/{location}` - Get volunteers by location
- `GET /api/volunteers/nearby?latitude=&longitude=&radiusKm=` - Find nearby volunteers

### Donations
- `GET /api/donations` - Get all donations
- `GET /api/donations/{id}` - Get donation by ID
- `POST /api/donations` - Create new donation
- `DELETE /api/donations/{id}` - Delete donation

### Emergency Contacts
- `GET /api/emergency-contacts` - Get all contacts
- `GET /api/emergency-contacts/{id}` - Get contact by ID
- `POST /api/emergency-contacts` - Add new contact
- `PUT /api/emergency-contacts/{id}` - Update contact
- `DELETE /api/emergency-contacts/{id}` - Delete contact

## Database Schema

### Tables

1. **animal_reports** - Stores reported animal incidents
2. **animal_adoptions** - Stores animals available for adoption
3. **volunteers** - Stores volunteer information
4. **donations** - Stores donation records
5. **emergency_contacts** - Stores emergency contact information

## Usage

### Reporting an Animal
1. Navigate to "Report Animal" page
2. Fill in the animal details (type, condition, description)
3. Provide location (use GPS or enter manually)
4. Add your contact information
5. Submit the report
6. Nearby volunteers will be notified

### Adopting an Animal
1. Navigate to "Adopt" page
2. Browse available animals by type
3. Click "Adopt Me" on an animal
4. Fill in your contact information
5. Submit the adoption request
6. The shelter will contact you

### Becoming a Volunteer
1. Navigate to "Volunteer" page
2. Fill in your personal information
3. Set your location and notification radius
4. Register as a volunteer
5. Receive notifications for nearby animal reports

### Making a Donation
1. Navigate to "Donate" page
2. Select or enter donation amount
3. Choose to remain anonymous or provide details
4. Add a personal message (optional)
5. Submit your donation

### Emergency Contacts
1. Navigate to "Emergency" page
2. Browse available emergency contacts
3. Click "Call Now" to contact immediately
4. Follow the emergency tips provided

## Development

### Backend Development
- Use Spring Boot DevTools for hot reloading
- Database schema auto-updates on application start
- CORS enabled for frontend on localhost:3000

### Frontend Development
- React DevTools for debugging
- Hot module replacement enabled
- API calls to localhost:8080

## Troubleshooting

### Backend Issues
- Ensure MySQL is running
- Check database credentials in application.properties
- Verify port 8080 is not in use
- Check Maven dependencies are installed

### Frontend Issues
- Ensure Node.js and npm are installed
- Check that backend is running on port 8080
- Verify port 3000 is not in use
- Clear node_modules and reinstall if needed

## Future Enhancements

- Real-time notifications using WebSockets
- Image upload for animal reports
- Payment gateway integration for donations
- User authentication and authorization
- Mobile app development
- Advanced search and filtering
- Animal tracking system
- Volunteer rating system

## License

This project is created for educational purposes.

## Contact

For questions or support, please contact the development team.
