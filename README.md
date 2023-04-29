# 🐳 Whisper API with Flask + Docker Compose 🐳

![whisperApiFlask](https://user-images.githubusercontent.com/57062736/235303377-e24c66f5-261d-4786-83e3-224a819fbdbd.png)

If you find this useful, remember about giving a start ⭐ to this repo or share it 🔁

Forked from [Lablab-ai/whisper-api-flask](https://github.com/lablab-ai/whisper-api-flask)

## Description 📋

![docker_facebook_share](https://user-images.githubusercontent.com/57062736/139103227-36f3cb32-c3c1-4158-b99e-25a31e955f44.png)

With this repo, you will deploy, using Docker Compose, an API of Whisper, an automatic State-of-the-Art speech recognition system from OpenAI that has been trained on 680,000 hours of multilingual and multitask supervised data collected from the web, running on a Flask server.

It is composed by a single container:

- `whisper-api`, Whisper API running on a Flash server.

## Installation ⌨

![Docker Installation Illustration](https://user-images.githubusercontent.com/57062736/139102730-d6f51d53-ffb3-44bb-be5e-2bdf48d91295.png)

0. You need **Docker** and **Docker-compose** where you are going to launch this so, if you do not have it... click [HERE](https://github.com/Inushin/dockerOdooSymfonySSL#installing-docker-docker-compose-and-composer) or go to the end of this `.md` ^^

1. Clone this rep.

2. Check the app.py in order to understand the logic, change the model of any other configuration.

3. Run `docker-compose up -d` or `docker-compose up` if you want to check the logs directly.

4. Check that the container is correctly deployed and running.

5. If everything lookd good. Lets have some fun with it:

   - Test the API by sending a POST request to the route [http://localhost:5000/whisper](http://localhost:5000/whisper), or the endpoint you have defined inside the `app.py` file, with a file in it. **Body should be form-data**.
   - For terminal lovers, you can test it with this curl command:

   ```bash
   curl -F "file=@/path/to/file" http://localhost:5000/whisper
   ```

   - The result should out put a JSON object with the transcription in it :beers:

## Docker's useful commands 📑

![Docker Commands Illustration](https://user-images.githubusercontent.com/57062736/139102966-25f28be1-f768-49bd-a8a1-915a8465de9e.png)

- Run Docker Compose: `docker compose up -d` / `docker compose up`

- Check Docker Compose's volumens status: `docker compose ps -a` / `docker compose ps`

- Check Docker's images: `docker images -a`

- Remove Docker's images: `docker rmi -f imageID1 imageID2 ...` (-f = force)

- Enter to a Docker's volumen: `docker compose exec VolumenID sh` / `docker compose exec VolumenID bash`

- Copy a file to the docker we want to: `docker cp file docker_id:/dir`

- Remove all dangling (not tagged or associated with a container) containers, volumes, networks and images: `docker system prune`

- Remove all unused containers and images with at least one container associated to them: `docker system prune -a`

- Shows all unused local images: `docker images ls -f dangling=true`

- Shows all unused local volumes: `docker volume ls -f dangling=true`

- Remove all local volumes not used by at least one container: `docker volume prune`

## Installing Docker, Docker-compose and Composer 🛠

![Docker-composer](https://user-images.githubusercontent.com/57062736/141182130-b8ed2d7a-9a68-4387-b838-ba0d44bb4e0e.png)

### Docker installation

1. Download and install Docker: `apt install docker`

2. Gives permisions so you can run it everywhere: `sudo usermod -aG docker $USER`

3. Starts Docker's service: `service docker start`

4. Starts Docker's service each time you run the SO: `chkconfig docker on`

### Docker Compose V2 installation

For this repo, DockerComposeV2 was used, so that is why we use `docker compose` instead of `docker-compose`. If you are using DockerComposeV1, have this in mind.

1. Run `sudo apt-get install docker-compose-plugin`

2. Check which versions are availables with `apt-cache madison docker-compose-plugin`

3. Intall the version you are looking for with `sudo apt-get install docker-compose-plugin=<VERSION_STRING>`, for this repo `sudo apt install docker-compose-plugin=2.6.0~ubuntu-focal` was used.

4. Check the version and the installation: `docker compose version`

## ⭐ Feedback and bugs 🐞

If you find any bug or just want to give your feedback (remember the ⭐ ^^), **Feel free to do it**. I am, like you, constantly learning and things change so quickly that... no one knows ^^

## Version control 📝

- [v1.0 - Current](https://github.com/Inushin/dockerPiholeWireguard/tree/v1.0) - Creation of the rep with the config finished - 29/04/2023
