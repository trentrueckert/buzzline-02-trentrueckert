# buzzline-02-trentrueckert

Streaming data is often too big for any one machine. 
A streaming platform helps organize our pipelines.

A common pattern for managing streaming pipelines is publish-subscribe, similar to how Twitter operates:

- Producers publish streaming information.
- Consumers subscribe to specific "topics" to process, analyze, and generate alerts based on detected conditions.

In this project, we use Apache Kafka, a popular, open-source streaming platform.
We write producers that send data to topics and consumers that read from topics.

> Kafka needs space - it's big. We'll use the Windows Subsystem for Linux on Windows machines. 

## Install and Start Kafka (using WSL if Windows)

In this task, we will download, install, configure, and start a local Kafka service. 

1. Install Windows Subsystem for Linux (Windows machines only)
2. Install Kafka Streaming Platform
3. Start the Zookeeper service (leave the terminal open).
4. Start the Kafka service (leave the terminal open).

For detailed instructions, see:

- [SETUP-KAFKA](docs/SETUP-KAFKA.md) (all machines)


## Copy This Example Project & Rename

Copy/fork this project into your GitHub account
and create your own version of this project to run and experiment with. 
Name it `buzzline-02-yourname` where yourname is something unique to you.
Follow the instructions in [FORK-THIS-REPO.md](https://github.com/denisecase/buzzline-01-case/blob/main/docs/FORK-THIS-REPO.md)).
    

## Manage Local Project Virtual Environment

Follow the instructions in [MANAGE-VENV.md](https://github.com/denisecase/buzzline-01-case/blob/main/docs/MANAGE-VENV.md) to:
1. Create your .venv
2. Activate .venv
3. Install the required dependencies using requirements.txt.

## Start Kafka and Zookeeper

Start Apache Kafka and Zookeeper in seperate terminals to begin. First navigate to the folder before the following steps.

Windows:
```shell
.venv\Scripts\activate
wsl
cd ~/kafka
bin/zookeeper-server-start.sh config/zookeeper.properties
```

```shell
.venv\Scripts\activate
wsl
cd ~/kafka
bin/kafka-server-start.sh config/server.properties
```

## Start a Kafka Producer

Producers generate streaming data for our topics.

In VS Code, open a terminal.
Use the commands below to activate .venv, and start the producer. 

Windows:
```shell
.venv\Scripts\activate
py -m producers.kafka_producer_rueckert
```

## Start a Kafka Consumer

Consumers process data from topics or logs in real time.

In VS Code, open a NEW terminal in your root project folder. 
Use the commands below to activate .venv, and start the consumer. 

Windows:
```shell
.venv\Scripts\activate
py -m consumers.kafka_consumer_rueckert
```

## Later Work Sessions
When resuming work on this project:
1. Open the folder in VS Code. 
2. Start the Zookeeper service.
3. Start the Kafka service.
4. Activate your local project virtual environment (.env).

## Save Space
To save disk space, you can delete the .venv folder when not actively working on this project.
You can always recreate it, activate it, and reinstall the necessary packages later. 
Managing Python virtual environments is a valuable skill. 

## License
This project is licensed under the MIT License as an example project. 
You are encouraged to fork, copy, explore, and modify the code as you like. 
See the [LICENSE](LICENSE.txt) file for more.