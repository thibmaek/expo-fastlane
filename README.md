<div align="center">
  <h1>expo-fastlane</h1>
  <p>Lightweight Docker image for deploying Expo React Native apps through Fastlane</p>
</div>
<hr />

## Quick setup

Integrate this in your local/CI/CD env by pulling the remote image from Docker Hub:

```console
docker pull thibmaek/expo-fastlane
```

```yaml
image: thibmaek/expo-fastlane:latest
```

## Building locally

```console
git clone https://github.com/thibmaek/expo-fastlane
docker build . -t expo-fastlane
docker run -d --name="expo-fastlane" expo-fastlane
docker exec -it expo-fastlane …
```

### Why?

[We](github.com/inthepocket) needed a way to deploy our Expo RN app using Bitbucket Pipelines.
Bitbucket pipelines has very limited support for RN projects, so i created this image to run a bash script in which publishes & builds the app through `exp` and then downloads the binary .ipa file to use the fastlane delivery api to send it to iTunes Connect.
