---
layout: post
title: Vision Language Navigation Using Hierarchical Chunk Memory Attention and Reinforcement Learning with Human Feedback
image: 
  path: /assets/img/model.jpeg
description: >
  Vision Language Navigation Using Hierarchical Chunk Memory Attention and Reinforcement Learning with Human Feedback
sitemap: false
---
---

## Results go to github and run the below command(for UI)
> streamlit run app.py

## Problem and summary of the project

Vision language navigation is a task in Embodied AI research where an agent has to navigate to a location mentioned given language instruction and visual inputs. However, the vision language navigation task poses some challenges, like Visual Complexity, Language Ambiguity, Multimodal Integration, Generalization to Unseen Environments, Dealing with Uncertainty, Zero-shot Learning, Real-time Decision-making, Evaluation Metrics, Human- Agent Interaction, and Long-Term Dependencies. In this project, we concentrate on Human- Agent Interaction and Long-Term Dependencies Challenges for which we introduce HCAM and RLHF mechanisms to our model and training, which enable the agent to think like a human while navigating and storing to infer to make future informed decisions in the same episode as cross episode memory is not tested in this project. We use the Mattersim simulator for an environment with 1.2 TB of data. The dataset comprises 194,400 RGB-D images of 90 building-scale scenes with 21,567 navigation instructions. Our model will be trained using contrastive supervised learning with ground actions, and RLHF techniques will be used as mentioned below. We observe its success in Human-Agent Interaction and Long-Term dependencies and failure in Generalization to Unseen Environments. The metrics used are success rate 42%, Trajectory length - x, and Navigation error - Y.  

## Intution 

![The layout of the whole network](/assets/img/arvl.jpeg)

### why HCAM

Regarding Long-Term Dependencies, VLN tasks often require agents to remember and refer to previous states, actions, or instructions to make informed navigation choices. Capturing and utilizing long-term dependencies effectively is a challenge, particularly when memory and context span over extended periods. HCAM introduced by can be experimented upon in this case. The original paper presents a novel approach called "hierarchical memory" HCAM to enhance the decision-making capabilities of RL agents. To evaluate the effectiveness of hierarchical memory, the authors conduct experiments, including Remembering the Ballet, which involves the agent recalling its previous observations and going to that particular dancer after seeing a 12-32 dance episode. Memory and recall were tested in all of these experiments. The results demonstrate that agents equipped with hierarchical memory outperform those without memory or with a single-level memory.
Furthermore, the hierarchical memory allows the agents to generalize their knowledge across different tasks and adapt their decision-making strategies to unseen situations. Overall, the paper presents the concept of hierarchical memory as a valuable mechanism for RL agents to improve their decision-making abilities. By enabling agents to perform mental time travel and leverage past experiences, the hierarchical memory enhances the agents' ability to generalize, adapt, and make informed decisions in dynamic environments. We will be using this mechanism in this paper.

![HCAM](/assets/img/Hcam.png)

### why RLHF

The next part of this paper uses RLHF. The concept of Reinforcement Learning with Human Feedback (RLHF) has been explored in various studies, but pinpointing the exact first paper on RLHF can be challenging due to the vast literature in the field. However, one influential early article on RLHF is "Apprenticeship Learning via Inverse Reinforcement Learning" by Pieter Abbeel and Andrew Y. Ng. In this paper, the authors introduce the concept of apprenticeship learning, which combines ideas from inverse reinforcement learning (IRL) and RLHF. The focus is on learning from demonstrations provided by an expert rather than relying solely on trial-and-error exploration. By incorporating human demonstrations, the RL agent can learn from an expert's behavior and acquire skills more efficiently. The paper proposes a mathematical framework for apprenticeship learning, which involves estimating the underlying reward function from expert demonstrations and then using this estimated reward function to train the RL agent.
RLHF was initially introduced as an approach to address the challenges of sparse reward signals and accelerate the learning progress in RL. Traditional RL methods rely on trial-and- error exploration to learn optimal policies, which can be time-consuming and inefficient. RLHF leverages human expertise to provide additional guidance and feedback to the RL agent, helping it learn faster and perform better. In RLHF, human feedback can take various forms, such as demonstrations, preferences, or direct evaluations. Demonstrations involve a human expert showcasing desired behaviors or providing example trajectories for the RL agent to learn from. Preferences involve the comparison of different actions or trajectories to indicate preferred choices. Direct evaluations provide explicit feedback or reward signals to guide the learning process. For example, we generate multiple trajectories, manually compare them in two pairs, and select the most successful one.

![Step-2](/assets/img/Blank diagram (4).png)  

An additional step-2 was to run with contrastive learning on the whole network with simulated game plays with langauge and image pairs as shown above.


## successful navigation sample:
https://github.com/shivacharan22/shivacharan22.github.io/assets/54499416/5c2073a6-a176-4f40-8d33-e9abcbf1e5f2


## For detailed information please check out this [!Report!](https://github.com/shivacharan22/shivacharan22.github.io/files/12554322/Capstone_report_upload_.pdf)


## Appendix:

### Setup I used to run:

I used GCP VM with 104 gb RAM with A100 GPU and 32 CPUs with Ubantu18.05 OS.

Below are the commands if you wanna fasten your process:
```
sudo wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu1804/x86_64/cuda-keyring_1.0-1_all.deb:

#This command uses wget to download a Debian package (cuda-keyring) from an NVIDIA repository. The package is used to authenticate CUDA-related software.
sudo dpkg -i cuda-keyring_1.0-1_all.deb:

#This command installs the previously downloaded Debian package (cuda-keyring) using dpkg. This package likely contains GPG keys and other authentication-related data for NVIDIA's CUDA repository.
sudo apt-get update:

#This command updates the package lists for the APT package manager, ensuring that you have the latest information about available packages and their versions.
sudo apt-get -y install cuda:

#This command installs CUDA, which is a parallel computing platform and application programming interface (API) developed by NVIDIA. CUDA is commonly used for GPU-accelerated computations.
sudo apt update:

#This command updates the package lists again.
sudo apt install apt-transport-https ca-certificates curl software-properties-common:

#This command installs various utilities and libraries necessary for handling HTTPS, certificates, and adding software repositories.
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -:

#This command fetches the Docker GPG key and adds it to the list of trusted keys on your system. It's used to verify the authenticity of Docker packages.
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable":

#This command adds the official Docker repository to your system's list of software sources.
sudo apt update:

#This command updates the package lists again to include the Docker repository.
sudo apt-cache policy docker-ce:

#This command checks the available versions of Docker in the newly added repository.
sudo apt install docker-ce:

#This command installs Docker Community Edition (CE), a containerization platform.
sudo systemctl status docker:

#This command checks the status of the Docker service, confirming that it is running.
sudo usermod -aG docker ${USER}:

#This command adds your user account to the "docker" group, allowing you to run Docker commands without using "sudo."
curl -s -L https://nvidia.github.io/nvidia-docker/gpgkey | sudo apt-key add -:

#This command fetches the NVIDIA Docker GPG key and adds it to your system's trusted keys.
curl -s -L https://nvidia.github.io/nvidia-docker/$distribution/nvidia-docker.list | sudo tee /etc/apt/sources.list.d/nvidia-docker.list:

#This command adds the NVIDIA Docker repository to your system's list of software sources.
sudo apt-get update:

#This command updates the package lists once more to include the NVIDIA Docker repository.
sudo apt-get install -y nvidia-docker2:

#This command installs NVIDIA Docker 2, which enables you to use NVIDIA GPUs with Docker containers.
sudo pkill -SIGHUP dockerd:

#This command sends a signal to the Docker daemon (dockerd) to reload its configuration. This is often necessary after installing Docker-related software.
xhost +:

#This command allows any user to connect to your X server (GUI) temporarily.
nvidia-docker run -it -e DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix --mount type=bind,source=$MATTERPORT_DATA_DIR,target=/root/mount/Matterport3DSimulator/data/v1/scans,readonly --volume pwd:/root/mount/Matterport3DSimulator mattersim:9.2-devel-ubuntu18.04:

#This is a complex command that appears to run a Docker container named "mattersim:9.2-devel-ubuntu18.04." The container is configured to use NVIDIA Docker, share the X server display, and mount specific directories as volumes.
cd /root/mount/Matterport3DSimulator:

#This command changes the current directory to "/root/mount/Matterport3DSimulator."
git clone --recursive https://github.com/peteanderson80/Matterport3DSimulator.git:

#This command clones a Git repository named "Matterport3DSimulator" and its submodules from the specified URL.
```