# Vue Jobs

This project is a job listing application built with Vue 3 and Vite. It allows users to view job postings, including details about the job, company information, and contact details.

## Features

- View job listings with detailed descriptions
- Company information and contact details
- Manage job postings (Edit and Delete functionality)
- Responsive design for mobile and desktop views

## Technologies Used

- **Vue 3**: A progressive JavaScript framework for building user interfaces.
- **Vite**: A fast build tool that provides a modern development experience.
- **Axios**: A promise-based HTTP client for making requests to the backend.
- **PrimeVue**: A rich set of UI components for Vue.js.

## Recommended IDE Setup

- [VSCode](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur).

## Project Setup

To get started with the project, follow these steps:

1. Clone the repository:

   ```sh
   git clone <repository-url>
   cd <project-directory>
   ```

2. Install the dependencies:
   ```sh
   npm install
   ```

### Compile and Hot-Reload for Development

To run the development server, use the following command:

```sh
npm run dev
```

### Run the API

To run the backend using json-server, execute:

```sh
npm run server
```

### Compile and Minify for Production

To build the project for production, run:

```sh
npm run build
```

## API Integration

The application fetches job data from a backend API. Ensure that the API is running and accessible at `http://localhost:5000/jobs/`.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Thanks to the Vue community for their support and resources.
- Special thanks to the contributors and developers who made this project possible.
