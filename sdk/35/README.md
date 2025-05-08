```
echo <GITHUB_PAT> | docker login ghcr.io -u <GITHUB_USERNAME> --password-stdin
docker build -t ghcr.io/<GITHUB_USERNAME>/android-sdk:35 .
docker push ghcr.io/<GITHUB_USERNAME>/android-sdk:35
```