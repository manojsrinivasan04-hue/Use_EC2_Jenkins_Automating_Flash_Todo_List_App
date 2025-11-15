Flask To-Do List App
This is a simple Flask-based To-Do List application that allows users to add, complete, and delete tasks. The tasks are stored in AWS DynamoDB, and flash messages are displayed for task actions.

Features
Add new tasks
Mark tasks as completed
Delete tasks
Flash messages for task actions
Prerequisites
AWS Account: You’ll need an AWS account to set up DynamoDB and configure the AWS CLI.
Python 3.10+: This project uses Python for its backend logic.
Flask: A lightweight web framework to create the app.
Boto3: AWS SDK for Python to interact with DynamoDB.
AWS CLI: Command line tool for configuring AWS services.
Table of Contents
Installation
Setting up DynamoDB
Configuring AWS CLI
Running the Application
File Structure
Contributing
Installation
Clone the repository:

git clone https://github.com/Sangamesh080/Python-projects/flask-todo-app.git
cd flask-todo-app
Create a Python virtual environment:

python3 -m venv flask-env
Activate the virtual environment:

On Windows:
flask-env\Scripts\activate
On MacOS/Linux:
source flask-env/bin/activate
Install dependencies:

pip install -r requirements.txt
Setting up DynamoDB
Create a DynamoDB table named todo_tasks:

To create the DynamoDB table, follow these steps:

Open the AWS DynamoDB Console.
Click on Create Table.
In the Table name field, enter todo_tasks.
Set Partition key as task_id with type String.
Leave the default settings for the rest of the options and click on Create.
DynamoDB Table Schema:

The table schema should have at least the following attributes:

task_id (String) - Partition Key
task_name (String)
completed (Boolean)
Configuring AWS CLI
Install AWS CLI (if not already installed):

Follow the instructions from the AWS CLI Documentation.

Configure AWS CLI:

Run the following command to configure your AWS CLI:

aws configure
You'll need to provide your:

AWS Access Key ID
AWS Secret Access Key
Default region name (e.g., us-east-1)
Default output format (e.g., json)
Ensure that DynamoDB permissions are enabled for the IAM user whose credentials you are using.

Configuring the Application
Update config.py:

In the config.py file, update the following values:

class Config:
    # AWS DynamoDB Configuration
    AWS_REGION = 'us-east-1'  # Set to your AWS region
    DYNAMODB_TABLE = 'todo_tasks'  # Name of your DynamoDB table
Running the Application
Run the Flask app:

Start the Flask development server:

flask run
The application will run on http://127.0.0.1:5000/.

Access the To-Do List App:

Open your browser and navigate to http://127.0.0.1:5000/. You should be able to see the app's user interface, where you can add, complete, and delete tasks.

File Structure
flask-todo-app/
│
├── app.py               # Flask app entry point
├── db.py                # DynamoDB connection setup
├── routes.py            # Main routes for task management
├── static/
│   └── style.css        # CSS for styling the UI
├── templates/
│   ├── dashboard.html   # Dashboard (Task Management) page
├── config.py            # Configuration for AWS and app settings
├── requirements.txt     # Python dependencies
└── README.md            # Project documentation (this file)
Contributing
Fork the repository.
Create a feature branch (git checkout -b feature-name).
Make changes and commit them (git commit -am 'Add new feature').
Push to the branch (git push origin feature-name).
Open a pull request to the main repository.
By following this README, you should be able to set up the application, configure DynamoDB, run the Flask app, and use the To-Do List application with the DynamoDB backend.