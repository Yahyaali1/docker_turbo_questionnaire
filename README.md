# docker_turbo_questionnaire


## Project Approach 
- Starts docker containner for [questionnaire backend](https://github.com/Yahyaali1/django_questionnaire_wizard) and [frontend](https://github.com/Yahyaali1/react_stunning_questionnaire_app)
- Exposes backend and frontend using ports 

### Directory Structure to follow on your machine
```bash
├── interviewTask
│   ├── DockerFile
│   └── ...
├── interviewTaskFrontEnd
│   ├── user-app
│       ├── DockerFile
│       └── ...
├── docker-compose.yml
└── README.md
```
### How to instructions:
#### Project Setup
Setting up both projects using docker-compose.
- Using Terminal 
   - Clone/extract project files in your local drive with the mentioned project structure above. 
   - ``` docker-compose build ``` to build both projects.
   - ``` docker-compose up ``` to start both projects.
   - For running backend ``` http://127.0.0.1:8000/questionnaire/fetch ``` port ``` 8000 ``` will be used.
   - For running frontend ``` http://127.0.0.1:3000 ``` port ``` 3000 ``` will be used.
- Note : Case where console shows warning for running migrations, you need to run ``` python manage.py migrate ``` under src/interviewTask 

#### Changing ports:
Ports mapping can be managed by changing docker-compose.yml
- In this file ``` "4000:3000" ``` refer to ```YourMachinePort:PortExposedFromContainner```.
- Furthermore you would need to update ``` CORS_ORIGIN_WHITELIST = (
    'http://localhost:3000', 'http://127.0.0.1:3000') ``` to allow new host to access backend. This variable can be changed under src/interviewTask/interviewTask/settings.py
- For changing port exposed by each project changed DockerFile under each project directory.


### Questionnaire-backend-containner Structure
```bash
├── backend
    ├── interviewTask
        ├── DockerFile
```
### Questionnaire-frontend-containner Structure
```bash
├── frontend
    ├── interviewTaskFrontEnd
        ├── user-app
            ├── DockerFile
            └── ...
```

#### Assumptions 
- Docker Installed

