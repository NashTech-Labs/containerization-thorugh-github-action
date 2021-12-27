# docker-in-github-action

Using this template you will be able to containerize following type of application
1. Maven 
2. Scala

The benifit of this template is You don't need to execute any cmd. YOu just have to trigger this workflow and you image get created and will be push to your dockerhub accout.

**Note:**
You just need to change your dockerhub username in the following line.

```tags: sakshigawande12/maven-app:${{ github.sha }}```

You can change the image name you want in place of "maven-app"

This note is same for the scala app .

**Rather than using the inbuild docker build and push action you use the following code as well**


```
- name: Build Docker image
  run: docker build --file Dockerfile --tag sakshigawande12/maven-app:$GITHUB_RUN_NUMBER .

- name: push Docker image
  run: docker push  sakshigawande12/maven-app:$GITHUB_RUN_NUMBER
```

**The above workflow will execute whenever you are going to push or create a Pull Request to master branch.**