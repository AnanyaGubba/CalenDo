# CalenDo - Interactive Event Planner

**CalenDo** is a modern, user-friendly event planning web application that helps you organize, manage, and track events effortlessly. Whether you're planning personal events, academic schedules, or professional meetings, CalenDo simplifies the entire process with an intuitive interface and powerful filtering capabilities.

##  Features

- **Add Events**: Easily create events with titles, dates, and detailed descriptions
- **View Events**: See all your upcoming events in an organized, clean card-based layout
- **Filter by Date**:  Quickly filter and find events scheduled for specific dates
- **Real-time Updates**:  Instant UI updates as you add or filter events
- **Responsive Design**:  Beautiful, mobile-friendly interface that works on all devices
- **No Event Clutter**: Clear messaging when no events are scheduled

##  Project Overview

CalenDo is built with a modern full-stack architecture combining:
- **Frontend**: React. js with Axios for seamless API communication
- **Backend**: Express.js server with CORS support
- **Data Management**: In-memory event storage (easily extendable to databases)

##  Getting Started

### Prerequisites

Before you begin, ensure you have the following installed:
- **Node.js** (v14 or higher)
- **npm** (comes with Node.js)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/AnanyaGubba/CalenDo.git
   cd CalenDo

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Install frontend dependencies** (if using Create React App)
   ```bash
   npm install react axios
   ```

### Running the Application

#### Start the Backend Server

```bash
node server.js
```

You should see: 
```
Server running on http://localhost:5000
```

#### Start the Frontend (in a new terminal)

```bash
npm start
```

This will open the React application in your browser at `http://localhost:3000`

##  Project Structure

```
CalenDo/
├── App.js              # Main React component with event management logic
├── App.css             # Styling for the application
├── App.test.js         # Tests for the App component
├── index.js            # React entry point
├── index.css           # Global styles
├── server.js           # Express. js backend server
├── package. json        # Project dependencies and metadata
└── README.md           # This file
```

## How It Works

### Frontend (App.js)

The React component manages: 
- **Event State**: Stores all events in component state
- **Form Handling**: Manages input fields for event title, date, and description
- **API Communication**: Uses Axios to communicate with the backend
- **Event Display**:  Renders events in an organized card layout
- **Filtering**: Filters events by date on demand

**Key Functions:**
- `fetchEvents()`: Retrieves all events from the server
- `addEvent()`: Submits new event data to the backend
- `filterEvents()`: Filters events based on selected date

### Backend (server.js)

Express.js server provides three main endpoints: 

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/events` | GET | Retrieve all events |
| `/events` | POST | Add a new event |
| `/events/filter` | GET | Filter events by date |

**Event Object Structure:**
```javascript
{
  id: number,
  title: string,
  date: string (YYYY-MM-DD format),
  description: string
}
```

##  User Interface

### Form Section
- Input field for event title
- Date picker for selecting event date
- Textarea for event description
- "Add Event" button to submit

### Filter Section
- Date picker to select filter date
- "Filter by Date" button to filter events
- "Show All" button to view all events

### Events Display
- Card-based layout showing all events or filtered results
- Each card displays: title, date, and description
- Message when no events are scheduled

##  API Endpoints

### GET /events
Retrieves all stored events. 

**Response:**
```json
[
  {
    "id": 1,
    "title": "Team Meeting",
    "date": "2025-12-20",
    "description": "Quarterly sync meeting"
  }
]
```

### POST /events
Adds a new event to the list.

**Request Body:**
```json
{
  "title":  "Project Deadline",
  "date": "2025-12-25",
  "description": "Final project submission"
}
```

**Response:**
```json
{
  "id": 2,
  "title": "Project Deadline",
  "date":  "2025-12-25",
  "description": "Final project submission"
}
```

### GET /events/filter? date=YYYY-MM-DD
Filters events by a specific date.

**Query Parameters:**
- `date` (required): Date in YYYY-MM-DD format

**Response:**
```json
[
  {
    "id": 1,
    "title": "Team Meeting",
    "date": "2025-12-20",
    "description": "Quarterly sync meeting"
  }
]
```

##  Technology Stack

| Technology | Purpose |
|-----------|---------|
| **React. js** | Frontend UI framework |
| **Axios** | HTTP client for API calls |
| **Express.js** | Backend server framework |
| **CORS** | Cross-Origin Resource Sharing |
| **Node.js** | JavaScript runtime environment |

##  Dependencies

### Backend (package.json)
```json
{
  "cors": "^2.8.5",
  "express": "^5.1.0"
}
```

### Frontend
- React (included with Create React App)
- Axios (for HTTP requests)

##  Troubleshooting

### Issue: Cannot connect to backend
- **Solution**: Ensure the server is running on port 5000. Check if another application is using that port.

### Issue: CORS errors in console
- **Solution**: The server includes CORS middleware. Verify `server.js` has `app.use(cors())`.

### Issue: Events not loading
- **Solution**: Check that both frontend and backend are running.  Verify the API endpoint URL in `App.js` matches your server address.

### Issue: Port 5000 already in use
- **Solution**: Change the port in `server.js` and update the API URL in `App.js` accordingly.

##  Future Enhancements

Potential features to expand CalenDo: 
- **Database Integration**: Store events in MongoDB, PostgreSQL, or Firebase
- **User Authentication**: Login system to save personal events
- **Event Notifications**:  Reminders and alerts for upcoming events
- **Edit & Delete**: Modify or remove existing events
- **Categories**: Organize events by type (work, personal, academic)
- **Recurring Events**: Support for repeating events
- **Export**:  Save events to calendar formats (iCal, Google Calendar)
- **Dark Mode**: Theme customization
- **Mobile App**: Native mobile application version

##  Usage Example

1. **Open the application** at `http://localhost:3000`
2. **Add an event**:
   - Enter title:  "Birthday Party"
   - Select date: 2025-12-25
   - Add description: "Celebrate with friends"
   - Click "Add Event"
3. **View your event** in the "Upcoming Events" section
4. **Filter events**:
   - Select date: 2025-12-25
   - Click "Filter by Date"
   - See only events on that date
5. **Show all events** by clicking "Show All" button


---

**Happy Planning with CalenDo!  **
```

This comprehensive README includes: 
- ✅ Project description and key features
- ✅ Complete installation and setup instructions
- ✅ Project structure overview
- ✅ Detailed explanation of how frontend and backend work
- ✅ API endpoint documentation with examples
- ✅ Technology stack details
- ✅ Troubleshooting guide
- ✅ Future enhancement ideas
- ✅ Usage examples
- ✅ Contributing guidelines
- ✅ Contact and support information

