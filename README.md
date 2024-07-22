# How to install Python on Shared/Cloud plan in Hostinger

This guide will show how it's possible to install and use Python (up to 3.10) on a Hostinger Shared/Cloud hosting plans **without root access**. This method will be based on [Miniconda](https://docs.anaconda.com/miniconda/ "Miniconda") usage (lightweight version of [Anaconda](https://www.anaconda.com/download "Anaconda")) and the utilization of virtual enviroments that can be created using this platform.

## Preparation

Before starting, you need to make sure that:
- You have access to your [hosting plan via SSH](https://support.hostinger.com/en/articles/1583245-how-to-connect-to-a-hosting-plan-via-ssh "hosting plan via SSH")
- Have [a basic knowledge](https://www.hostinger.com/tutorials/linux-commands "a basic knowledge") of using Linux terminal
- Are willing to use [Conda](https://docs.conda.io/en/latest/ "Conda") for Python virtual environments management
- The version of Python up to 3.10 (3.11 and 3.12 versions are not supported with our used Miniconda3-4.5.12 release) is fine for you

## Installation of Miniconda
First, you need to be connected to your hosting plan via SSH and make sure that you are in your home folder (~) by executing this command:
```bash
cd ~
```
Then, you can download Miniconda3-4.5.12 release by executing this command:
```bash
wget repo.anaconda.com/miniconda/Miniconda3-4.5.12-Linux-x86_64.sh
```
After downloading the Miniconda3 platform on your hosting plan, you need to give the script **execution** permissions by running this command:
```bash
chmod +x Miniconda3-4.5.12-Linux-x86_64.sh
```
Now run the script:
```bash
./Miniconda3-4.5.12-Linux-x86_64.sh
```
Press **Enter**, and with arrows on the keyboard, read the license and lastly type:
```bash
yes
```
Once again, hit **Enter** to confirm the default installation path.

When the installation is finished, type:
```bash
no
```
Now you need to make sure that your SSH terminal will start with the Conda environment activated each time you launch it. To do that, we will need to modify the `.bash_profile` file by executing this command (make sure that you're in your home `~` folder):
```bash
echo "source ~/miniconda3/bin/activate" >> .bash_profile
```

For the changes to take effect, please try to relaunch your terminal.

## Creating a virtual environment for your project and activating it

At this point, you should have Miniconda installed and the Conda environment activated at your terminal, so the next step would be to create a virtual environment with a specified Python version by following this command:
```bash
conda create -n myenv python=3.10
```
**The name "myenv" can be changed to your preferred environment name and "3.10" to your specific Python version (up to 3.10)*

Confirm default packages to be installed in your environment by executing the following letter:
```bash
y
```
Finally, you can activate your newly created virtual environment by running this command:
```bash
conda activate myenv
```
Currently, you should be able to use Python with your specified version. To check that, you can run this command:
```bash
python --version
```
In this case, you should see the following output:
```bash
Python 3.10.4
```
After doing some work on it, you can deactivate the virtual environment:
```bash
conda deactivate
```

## Final thoughts

Since Python is crucial for everyone and can open quite different operation levels, this guide provides a reliable solution to run it without administrative access to the server. It depends on when you're reading this, but some older Shared/Cloud hosting servers had Python 3.6 pre-installed. However, with newer OS releases, Python was disabled from the Shared/Cloud servers, so this guide is a way to go if you want to utilize this powerful language.
