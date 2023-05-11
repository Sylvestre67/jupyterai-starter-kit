# JupyterLab + JupyterAI Docker Environment
This Docker environment provides a pre-configured JupyterLab instance running on Python 3.10. To use this environment, you'll need to have Docker and Docker Compose installed on your system.

## Requirements
- Docker Engine
- Docker Compose

## Usage
Clone this repository to your local machine:

```
$ git clone https://github.com/Sylvestre67/jupyterai-starter-kit.git && cd jupyterai-starter-kit
```

Add your LLM service API key to the docker-compose.yml file. 
For example, to use OPENAI, edit the following line to the environment section of the docker-compose.yml file:

```yaml
services:
  notebook:
    build: .
    ports:
      - "8888:8888"
    volumes:
      - .:/app
    environment:
      - OPENAI_API_KEY=<your_openai_api_key>
```

Start the Docker container using Docker Compose:
```commandline
$ docker-compose up
```

This command will build the Docker image and start a container from that image.

Open your web browser and navigate to http://localhost:8888.

## File Structure
The JupyterLab environment is configured to mount the work directory in the Docker container. This means that any files you want to work with in JupyterLab should be placed in the work directory on your local machine.

## Customizing the Environment
To customize the environment, you can modify the Dockerfile to include any additional packages or dependencies you need. You can also modify the docker-compose.yml file to set environment variables or configure other Docker settings.

## Jupyter AI Assistant
This environment comes with the Jupyter AI assistant, which allows you to use various LLM to assist you with your work in Jupyter Notebook.

To use the Jupyter AI assistant, you need to have an OpenAI API key and add it to the docker-compose.yml file as described in step 3 above.

Please refer to the [Jupyter AI](https://jupyter-ai.readthedocs.io/en/latest/users/index.html#) documentation for more information and configuration options.

## Additional Resources
[Docker documentation](https://docs.docker.com/)
[Docker Compose documentation](https://docs.docker.com/compose/)
[Jupyter documentation](https://jupyter.readthedocs.io/en/latest/index.html)

That's it! You should now be able to start working in the JupyterLab environment. 

If you have any issues or questions, feel free to open an issue on this repository or contact the maintainer.