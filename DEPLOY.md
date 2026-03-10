# FAI-LiveKit-Agent

## Build the Docker image

```bash
# For the first build, use `uv lock` to create the uv.lock file
uv lock

docker build -t livekit-agent:1.0 .
```

## Run the Docker container

```bash
docker run -d \
    --name livekit-agent \
    --network host \
    -e LIVEKIT_URL=ws://localhost:7880 \
    -e LIVEKIT_API_KEY=devkey \
    -e LIVEKIT_API_SECRET=secret \
    livekit-agent:1.0 \
    uv run src/agent.py start
```