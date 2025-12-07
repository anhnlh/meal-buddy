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
