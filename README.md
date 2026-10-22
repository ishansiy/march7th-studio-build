# march7th-studio-build

Sync, build and deploy pipeline for ModelScope Studio `hansiy/March7thAssistant`.

This repository exists because GitHub disabled Actions for `ishansiy/March7thAssistant`
(`HTTP 422: Actions has been disabled for this repository`), so the original fork can no
longer run its own workflows. Everything the fork pipeline did now happens here:

1. Clone `ishansiy/March7thAssistant` and merge `moesnow/March7thAssistant@main` into it.
2. Build the web UI and the Docker image.
3. Verify container startup, WEBUI_TOKEN authentication, persistence and bundled version.
4. Publish to `ghcr.io/ishansiy/march7th-studio-build`.
5. Update the Studio Dockerfile and redeploy, refusing to interrupt a running task.

Required secrets: `MODELSCOPE_API_KEY`, `STUDIO_WEBUI_TOKEN`.
