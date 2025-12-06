# MealBuddy Architecture

## Application Requirements

- Create a web application for logging meals throughout the day, compatible with both desktop and mobile devices.
- Allow users to log their meal entries, view, and collaborate with other users' entries, similar to an accountability partner platform.
- This is a passion project, and I do not expect heavily-optimized code.
- Implement a very simple PostgreSQL setup.
- Develop the web app using C# .NET, all within a single system.
- Use Svelte for the front end, ensuring it is responsive and works well on smaller screens like tablets or mobile phones.
- Containerize the application using Docker and Docker Compose to simplify deployments and testing.

## System Architecture

### Backend (C# .NET)

**Framework**: ASP.NET Core Web API
- RESTful API design
- JSON serialization/deserialization
- Middleware for authentication and logging

**Database**: PostgreSQL
- Relational database for structured data storage
- Simple setup with minimal complexity
- Supports all required relationships

**ORM**: Entity Framework Core
- Object-relational mapping
- Migrations for database schema evolution
- LINQ queries for data access

**Authentication**: JWT tokens with ASP.NET Core Identity
- Secure user authentication
- Password hashing with salt
- Session management

**API Endpoints**:
- User authentication (login/register)
- Topic management (create, read, update, delete)
- Log entry management (create, read, update, delete)
- Sharing management (invite, remove, permissions)
- Feed/overview endpoints for collaborative viewing

### Frontend (Svelte)

**Framework**: Svelte with SvelteKit
- Component-based architecture
- Reactive programming model
- Lightweight compared to React/Vue

**Responsive Design**: Mobile-first approach
- CSS Grid/Flexbox for layout
- Responsive breakpoints for all device sizes
- Touch-friendly interface elements

**State Management**: Svelte stores or Context API
- Efficient state handling
- Component communication
- Global state management

**Components**:
- User dashboard
- Topic list view
- Meal entry form
- Calendar/date-based grouping
- Collaboration sharing interface
- Mobile-friendly navigation

### Containerization (Docker)

**Docker Compose** for multi-container setup
- Local development environment
- Consistent deployment across environments
- Easy testing and scaling

**Services**:
- Web API (ASP.NET Core)
- Database (PostgreSQL)
- Frontend (Svelte build)

**Networking**: Internal Docker networks
- Secure communication between containers
- Port mapping for external access

**Persistence**: Volume mounts for database data
- Data persistence across container restarts
- Backup and recovery capabilities

## MVP Requirements

### Core Features
1. User authentication (login/register)
2. Topic creation and management
3. Meal entry logging with title, content, calories, sentiment
4. Date-based grouping of entries
5. Collaborative sharing of topics
6. Responsive web interface for mobile and desktop

### Technical Requirements
1. PostgreSQL database setup
2. C# .NET Web API backend
3. Svelte frontend with responsive design
4. Docker containerization with docker-compose
5. Basic CRUD operations for all entities

## Enhancement Roadmap

### Phase 1: Basic Functionality
- User authentication and account management
- Topic creation and organization
- Meal entry logging with all required fields
- Basic search and filtering capabilities

### Phase 2: Collaboration Features
- Topic sharing with permission levels
- Real-time collaboration indicators
- Commenting system on entries
- Activity feed for shared topics

### Phase 3: Advanced Features
- Analytics and statistics dashboard
- Goal setting and progress tracking
- Integration with fitness APIs
- Notification system
- Data export capabilities

### Phase 4: Polish and Performance
- Improved UI/UX with animations
- Performance optimization
- Mobile app capabilities (PWA)
- Advanced search and filtering
- Data backup and restore features

