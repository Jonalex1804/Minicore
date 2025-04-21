# MVCgit 

Es una aplicación web desarrollada con Flask que sigue el patrón de arquitectura MVC (Modelo-Vista-Controlador). Su propósito principal es gestionar empleados, tareas y proyectos de forma eficiente. Entre sus funciones destacadas se encuentra la posibilidad de ver trabajos o tareas atrasadas dentro de un rango de fechas específico, además de filtrar tareas por estado y fecha, y realizar un seguimiento del progreso de los proyectos.
## Features

- View all employees, tasks, and projects.
- Filter overdue tasks within a specified date range.
- Highlight the total number of overdue tasks.
- Simple, user-friendly interface.

## Prerequisites

- Python 3.11
- SQLite
- Flask
- SQLAlchemy
- Jinja2

## Installation

1. Clone the repository:

    ```bash
    git clone https://github.com/yourusername/minicore.git
    cd minicore
    ```

2. Create a virtual environment and activate it:

    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    ```

3. Install the required packages:

    ```bash
    pip install -r requirements.txt
    ```

4. Set up the database:

    ```bash
    flask db init
    flask db migrate -m "Initial migration"
    flask db upgrade
    ```

5. Populate the database with initial data:

    ```bash
    sqlite3 instance/minicore.sqlite < data.sql
    ```

## Usage

1. Run the Flask application:

    ```bash
    flask run
    ```

2. Open your web browser and go to `http://127.0.0.1:5000`.

## File Structure


## Models

### Employee

- `id`: Integer, primary key
- `first_name`: String, employee's first name
- `last_name`: String, employee's last name
- `username`: String, unique, employee's username
- `tasks`: Relationship to `Task`

### Project

- `id`: Integer, primary key
- `name`: String, project's name
- `tasks`: Relationship to `Task`

### Task

- `id`: Integer, primary key
- `description`: String, task description
- `start_date`: DateTime, task start date
- `estimated_days`: Integer, estimated number of days to complete the task
- `status`: String, task status (e.g., 'In progress', 'Done')
- `employee_id`: Integer, foreign key to `Employee`
- `project_id`: Integer, foreign key to `Project`
- `employee`: Relationship to `Employee`
- `project`: Relationship to `Project`

## Routes

### `/`

Displays the homepage with a list of employees, tasks, and projects.

### `/overdue-tasks`

Displays a list of overdue tasks within a specified date range. Users can filter tasks by start and end dates.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Repositorio GITHUB
https://github.com/Jonalex1804/Minicore.git

## Documentacion

https://www.youtube.com/watch?v=xlxNzOqT16g
https://www.youtube.com/watch?v=PmnIvR066WA

## Video explicativo 
https://udlaec.sharepoint.com/:v:/s/ubicua852/EW-n20vRK05Bl9CpXUsG3KQBDB5Ijdct-xZgPTG4JzZ5YQ?email=juan.leon%40udla.edu.ec&e=VEh6Ah&nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJTdHJlYW1XZWJBcHAiLCJyZWZlcnJhbFZpZXciOiJTaGFyZURpYWxvZy1MaW5rIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXcifX0%3D


## Link del deploy 
https://minicore-pnmf.onrender.com
