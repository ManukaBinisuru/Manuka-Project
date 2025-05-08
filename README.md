# 🪑 Furniture Store Web Application

A seamless online shopping and interior design platform built using *React, Vite, .NET 8, Azure Functions, and **@react-three/fiber*, empowering users to visualize and personalize room layouts in 2D and 3D.

---

## 🌐 Live Demo

🔗 [Link to Live Application](#) (Add deployment URL here if available)

---

## 📸 Screenshots

(Include some screenshots of homepage, design page in 2D and 3D modes, and saved designs if possible)

---

## 🚀 Features

### 👤 User Roles
- *Customer*: Design rooms remotely, save and revisit layouts, shop furniture.
- *Admin*: Create personalized room setups in-store using the design tool.

### 🏠 Homepage
- Hero section with call-to-action
- Featured furniture products (sofas, chairs, tables)
- Company services: Custom furniture, design consultation, fast delivery

### 🔒 Authentication
- JWT-based login for both Admin and Customer
- Role-based navigation and feature access

### 🛋 Room Designer
- Drag & drop furniture from sidebar (beds, chairs, tables, etc.)
- Customize room size, wall/floor textures or colors, and toggle 2D/3D view
- Style furniture: color, dimensions, shade, shadow
- Save designs with name and reuse/edit later

---

## 🛠 Tech Stack

### Frontend
- *React 19*  ![Image Alt](image_url)
- *Vite* – Build tool for faster development
- *React Router DOM* – Client-side routing
- *Bootstrap 5* – Responsive layout and UI
- *@react-three/fiber* & *drei* – 3D rendering engine
- *Axios* – API requests
- *Leva* – UI sliders and controls
- *React Icons* – Vector icons

### Backend
- *Azure Functions v4* – Serverless APIs
- *.NET 8*
- *Entity Framework Core 9* – Database ORM
- *SQL Server* – User and design data storage
- *Newtonsoft.Json* – JSON parsing
- *PasswordHasher<T>* – Secure password hashing

---





## 🔐 Security

### JWT Authentication
- Tokens generated at login contain user ID, role, and expiration
- Attached to every secure API request (Authorization header)

### Password Protection
- Passwords stored as secure hashes using ASP.NET Core's PasswordHasher<T>
- Hashed password compared during login (no plaintext storage)

---




## 📁 Project Structure
/frontend - React + Vite frontend
/backend - Azure Functions (.NET 8) backend
/public - Assets like textures, models





## 🧪 Setup Instructions

### 1. Clone Repository
```bash
git clone https://github.com/Mathushanan/Furniture-Store.git
cd furniture-store


2. Frontend Setup

cd frontend
npm install
npm run dev

3. Backend Setup

cd backend
dotnet restore
func start

Ensure a local SQL Server instance is running and configured in appsettings.json





💾 Database Schema (Overview)
The database consists of three main entities: User, RoomDesign, and Furniture. These entities are related to each other to store user information, room design details, and associated furniture for each user.

User Table
Stores user information, including their role and personal details.
UserId (int): Primary key, unique identifier for the user.
UserType (string): The type of user (e.g., Admin, Customer).
FirstName (string): User's first name.
LastName (string): User's last name.
Gender (string): User's gender.
Address (string): User's address.
Email (string): User's email address (unique).
ContactNumber (string): User's phone number.
PasswordHash (string): Hashed password for authentication.

Relationships:
A User can have multiple RoomDesigns (one-to-many relationship).

RoomDesign Table
Stores the design details of the room, including the room's size, wall attributes, and associated furniture.
RoomId (int): Primary key, unique identifier for the room design.
UserId (int): Foreign key referencing the User table, indicating which user owns the design.
RoomSize (float): The size of the room.
WallHeight (float): Height of the room's walls.
WallThickness (float): Thickness of the room's walls.
WallColor (string): Color of the room's walls.
WallTexture (string): Texture applied to the walls.
FloorTexture (string): Texture applied to the floor.
ViewMode (string): The mode in which the room is viewed (either 2D or 3D).
DesignName (string): The name of the room design.
CreatedAt (DateTime): Timestamp of when the design was created.

Relationships:
A RoomDesign belongs to one User (many-to-one relationship).
A RoomDesign can have multiple Furnitures (one-to-many relationship).

Furniture Table
Stores the furniture items placed in a room, along with their position, size, and styling.
FurnitureId (int): Primary key, unique identifier for the furniture item.
RoomId (int): Foreign key referencing the RoomDesign table, indicating which room the furniture belongs to.
Type (string): The type of furniture (e.g., sofa, chair, table).
PositionX (float): X coordinate of the furniture in the room.
PositionY (float): Y coordinate of the furniture in the room.
PositionZ (float): Z coordinate of the furniture in the room.
Color (string): Color of the furniture.
SizeWidth (float): Width of the furniture.
SizeHeight (float): Height of the furniture.
SizeLength (float): Length of the furniture.
Shade (string): Shade of the furniture.
Shadow (bool): Whether the furniture casts a shadow.

Relationships:
A Furniture item belongs to one RoomDesign (many-to-one relationship).

This schema outlines the structure of the database and the relationships between users, their room designs, and the furniture placed within those designs, ensuring a seamless interior design and furniture shopping experience.




🎨 Resources & Credits
Art / Textures / 3D Models
3D Furniture Models:
All 3D models used in the application were downloaded from Free3D.com. These models are free to use under their respective free licenses.

Wall & Floor Textures:
Texture images were sourced directly from Google search (free-to-use images). Used solely for demonstration purposes.

Model Conversion:
3D models were converted to .glb format using anyconv.com – a free and easy-to-use model conversion tool.

Icons:
React Icons – MIT licensed icon packs including FontAwesome, Material Icons, and others.
