# Kustomize CI Helper

This image is used to validate deployments within a continuous integration pipeline. The following code snippet is an example teamcity build step.

```bash
docker run -v $(pwd)/base:/app/base:ro -v $(pwd)/overlays:/app/overlays:ro deenerin0/kustomize-ci overlays/production > /dev/null

if [ "${'$'}?" = "1" ]; then
  exit 1
fi

exit 0
```
