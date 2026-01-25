# Robin OSINT DarkWeb Tool : Commands

## quickstart guide

first make sure these programs are running

- start `proton vpn` and quick connect
- start `docker desktop`
- start `ollama`

to start and stop execute these commands in powershell

- run `docker start robin` to start
- run `docker stop robin` to stop

finally to access the GUI open this in your browser
```
http://127.0.0.1:8501/
```

## other usefull commands

these must be executed in a ubuntu wsl terminal

- create the docker and show the log
```
cd robin
sudo docker run -d --name robin -p 8501:8501 -v $(pwd):/app --env-file .env robin ui --ui-host 0.0.0.0 --ui-port 8501
sudo docker logs -f robin
```
- delete the docker
```
sudo docker rm -f robin
```
