# Development Guide

## Initial Setup

This project is best developed using GitHub Codespaces, which provides a consistent development environment with all the necessary tools pre-configured.

### Setting up your development environment

1. Open the repository in a codespace
2. Wait for the container to finish building and installing dependencies
3. Install Python dependencies by running:

   ```bash
   pip install -r src/requirements.txt
   ```

### Dependencies

The project requires the following Python packages:

- FastAPI - Modern web framework for building APIs
- Uvicorn - ASGI server implementation for running the FastAPI application

These dependencies will be installed when you run `pip install -r src/requirements.txt`

## Debugging

### Running the website locally

1. From VS Code's Run and Debug view (Ctrl+Shift+D), select "Launch Mergington WebApp" from the launch configuration dropdown
2. Press F5 or click the green play button to start debugging
3. The website will be available at `http://localhost:8000`
4. The API documentation will be available at `http://localhost:8000/docs`

### Debugging tips

- FastAPI's auto-reload feature will automatically restart the server when you make code changes
- Use the interactive API documentation at `/docs` to test your endpoints

## Features

### Dark Mode

The website includes a dark mode toggle button located in the top right corner of the header. Users can:

- Click the moon icon (🌙) to switch to dark mode
- Click the sun icon (☀️) to switch back to light mode
- The selected theme preference is automatically saved in the browser's local storage
- The saved preference is restored when the user returns to the website

This feature is especially popular with students who prefer darker interfaces!

## Usage

### Running the application

1. Install the dependencies:

   ```bash
   pip install -r src/requirements.txt
   ```

2. Run the application:

   ```bash
   python -m uvicorn src.app:app --host 0.0.0.0 --port 8000
   ```

3. Open your browser and go to:
   - API documentation: http://localhost:8000/docs
   - Alternative documentation: http://localhost:8000/redoc

### API Endpoints

| Method | Endpoint                                                          | Description                                                         |
| ------ | ----------------------------------------------------------------- | ------------------------------------------------------------------- |
| GET    | `/activities`                                                     | Get all activities with their details and current participant count |
| POST   | `/activities/{activity_name}/signup?email=student@mergington.edu` | Sign up for an activity                                             |

> [!IMPORTANT]
> All data is stored in memory, which means data will be reset when the server restarts.
