# Information Retrieval System Course @ UGM Class MMI 2023-I

> Sistem Temu Balik Informasi 

This to compare the Llama3 model when given query to produce Pandas Dataframe.

## Running Ollama

```shell
docker run --platform linux/amd64 --volume $(pwd)/ollama-models:/root/.ollama -p 11434:11434 --name ollama -d docker.io/ollama/ollama:0.1.39
```

Then download the model, we use `llama3.1:8b`

```shell
docker exec -it ollama ollama run llama3.1:8b
```

Test it using cURL:

```shell
curl -L 'http://localhost:11434/api/generate' -H 'Content-Type: application/json' -d '{
  "model": "llama3.1:8b",
  "prompt": "Why is the sky blue?",
  "stream": false
}'
```

## Reproduce the Jupyter Notebook

Use [Poetry](https://python-poetry.org/).

1. Create Poetry env by `poetry shell`
2. Download packages `poetry install`
3. Activate shell `source $(poetry env info --path)/bin/activate`

Then run each cell in the [20240824-stbi-final.ipynb](/20240824-stbi-final.ipynb)
