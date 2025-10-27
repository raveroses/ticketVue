🎟️ VueTicket: Streamlined Ticket Management

## Overview
VueTicket is a modern and intuitive web application designed to simplify ticket management. Built with Vue.js 3 and Vite, it offers a seamless experience for user authentication, creating, tracking, and resolving various types of tickets directly within the browser using local storage for data persistence.

## Features
*   ✨ **User Authentication**: Secure user registration and login functionality (client-side via local storage).
*   📊 **Dashboard Overview**: A clear dashboard displaying key metrics like total, open, and resolved tickets.
*   ➕ **Ticket Creation**: Easily create new tickets with a title, detailed description, and initial status.
*   📝 **Ticket Management**: Comprehensive listing of all tickets, with capabilities for editing and deleting existing entries.
*   🔄 **Dynamic Status Updates**: Tickets can be assigned statuses such as "Open," "Closed," or "In Progress."
*   📱 **Responsive Design**: Optimized for a smooth experience across various devices and screen sizes.

## Getting Started

Follow these steps to set up and run VueTicket locally on your machine.

### Prerequisites
Ensure you have Node.js (version 18 or higher) and npm installed.

### Installation
1.  **Clone the repository**:
    ```bash
    git clone https://github.com/raveroses/ticketVue.git
    ```
2.  **Navigate into the project directory**:
    ```bash
    cd ticket
    ```
3.  **Install dependencies**:
    ```bash
    npm install
    ```

### Running the Application
To start the development server:
```bash
npm run dev
```
The application will typically be accessible at `http://localhost:5173`.

### Environment Variables
This project currently uses client-side local storage for all data persistence and does not require server-side environment variables.

## Usage

Once the application is running, you can interact with it through your web browser.

1.  **Access the Application**: Open your browser and navigate to the address provided by Vite (e.g., `http://localhost:5173`).
2.  **Sign Up**: If you are a new user, click "Get Started" or navigate to `/signup` to register a new account by providing your full name, email, and password. Your credentials will be stored locally.
3.  **Login**: After signing up, or if you already have an account, navigate to `/login` to log in using your registered email and password.
4.  **Dashboard**: Upon successful login, you will be redirected to the dashboard. Here you can:
    *   View a summary of your tickets (Total, Open, Resolved).
    *   Use the sidebar to switch between "Create Ticket" and "Ticket List".
5.  **Create a Ticket**: Select "Create Ticket" from the sidebar. Fill in the title, description, and choose a status (Open, Close, In progress) for your new ticket, then click "Create."
6.  **Manage Tickets**: Select "Ticket List" from the sidebar to view all your created tickets. From here, you can:
    *   **Edit**: Click the "Edit" button next to a ticket to modify its details.
    *   **Delete**: Click the "Delete" button to remove a ticket permanently.

The hero section prominently features an image (`ticket.jpg`) that visually represents the ticket management concept, providing an engaging first impression of the application's purpose.

## Technologies Used

| Technology    | Description                                                     |
| :------------ | :-------------------------------------------------------------- |
| **Vue.js 3**  | A progressive framework for building user interfaces.           |
| **Vite**      | A fast, opinionated build tool and development server.          |
| **Vue Router 4** | The official routing library for Vue.js.                       |
| **Heroicons** | A set of beautiful, free SVG icons for UI.                      |
| **Local Storage** | Browser-based client-side storage for user and ticket data persistence. |
| **Node.js**   | JavaScript runtime used for development dependencies and build tools. |

## Contributing

We welcome contributions to enhance VueTicket! If you're interested in improving the project, please follow these guidelines:

*   🍴 **Fork the repository**: Start by creating your own fork of the project.
*   ✨ **Create your feature branch**: Make a new branch for your feature or bug fix (e.g., `git checkout -b feature/new-dashboard-widget`).
*   🚀 **Commit your changes**: Write clear, concise commit messages that explain your changes (e.g., `git commit -m 'feat: Add responsive sidebar'`).
*   ⬆️ **Push to the branch**: Push your local branch to your forked repository (`git push origin feature/new-dashboard-widget`).
*   🗣️ **Open a Pull Request**: Submit a pull request detailing your changes and the problem they solve or the feature they add.

## License

This project is currently unlicensed. It is intended for personal use and portfolio demonstration. For formal distribution or open-source contribution, consider adding an appropriate license file (e.g., MIT).

## Author Info

Connect with me and see more of my work:

*   LinkedIn: [Your LinkedIn Profile]
*   Twitter: [Your Twitter Handle]
*   Portfolio: [Your Portfolio Website]

---

[![Vue.js](https://img.shields.io/badge/Vue.js-35495E?style=for-the-badge&logo=vue.js&logoColor=4FC08D)](https://vuejs.org/)
[![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white)](https://vitejs.dev/)
[![NPM](https://img.shields.io/badge/npm-CB3837?style=for-the-badge&logo=npm&logoColor=white)](https://www.npmjs.com/)
[![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)](https://nodejs.org/)

[![Readme was generated by Dokugen](https://img.shields.io/badge/Readme%20was%20generated%20by-Dokugen-brightgreen)](https://www.npmjs.com/package/dokugen)