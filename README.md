# Ollama Docker Compose

This project is a docker compose file for [ollama](https://github.com/ollama/ollama)

## Usage

```bash
cd {your_workpace}
git clone {this_package}
```

### Ollama and Open Web UI with NVIDIA GPU

```bash
docker compose up -d
```

#### Customize Options

Edit environments for Ollama and Open WebUI.

```bash
cp .env.example .env
vi .env
```
Restart docker containers.

```bash
docker compose stop
docker compose up -d
```


### Docker Compose Settings

|Item|Value|
|:-|:-|
|Ollama port|11434 (configurable via `OLLAMA_PORT`)|
|Model storage|.ollama in this project directory|

### Environment Variables

The following environment variables can be set in your `.env` file:

| Variable                   | Description                                         | Example Value                  |
|----------------------------|-----------------------------------------------------|-------------------------------|
| `OLLAMA_DOCKER_TAG`        | Ollama Docker image tag                             | `latest`                      |
| `WEBUI_DOCKER_TAG`         | Open WebUI Docker image tag                         | `main`                        |
| `OPEN_WEBUI_PORT`          | Port for Open WebUI                                 | `3000`                        |
| `OLLAMA_PORT`              | Host port for Ollama API                            | `11434`                       |
| `OLLAMA_MAX_LOADED_MODELS` | Maximum number of loaded models                     | `1`                           |
| `OLLAMA_NUM_PARALLEL`      | Number of parallel requests                         | `1`                           |
| `OLLAMA_SCHED_SPREAD`      | Scheduler spread setting (0: off, 1: on)            | `0`                           |
| `OLLAMA_FLASH_ATTENTION`   | Enable flash attention (1: enabled, 0: disabled)    | `1`                           |
| `OLLAMA_KV_CACHE_TYPE`     | Key-value cache type                                | `q8_0`                        |
