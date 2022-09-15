# Action-d

### workflow
* [action-d](.github/workflow/action-d.yaml) workflow for test github runner.
* To specify a self-hosted runner for your job, configure [runs-on](.github/workflows/action-d.yml#runs-on) in your workflow with self-hosted **runner labels**.


### Setting up self-hosted runner [^1]
[^1]: [Adding self-hosted runners](https://docs.github.com/en/actions/hosting-your-own-runners/adding-self-hosted-runners) is installation document.
* Go to [setttings/action/runners](../../settings/actions/runners) and click **New self-hosted runner**.
* Select the operating system image and architecture
* Shell to self-hosted runner machine. **Download** and **Configure** follow the message that appears.
* Config service follow [link](https://docs.github.com/en/actions/hosting-your-own-runners/configuring-the-self-hosted-runner-application-as-a-service#installing-the-service)
* Install docker on self-hosted runner machine. config group to docker service
  - Add docker group
  ```bash
  sudo groupadd docker
  ```
  - Add your current user to docker group
  ```bash
  sudo usermod -aG docker $USER
  ```
  - Change group and permission to docker.socket
  ```bash
  sudo chgrp docker /lib/systemd/system/docker.socket
  sudo chmod g+w /lib/systemd/system/docker.socket
  ```
