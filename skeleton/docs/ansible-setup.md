# docs/ansible-setup.md

## installation

### list available versions

```shell
pip install yolk3k
yolk -V ansible
```

Output example

```shell
ansible 2.4.1.0
ansible 2.4.0.0
ansible 2.3.2.0
ansible 2.3.1.0
ansible 2.3.0.0
ansible 2.2.3.0
ansible 2.2.2.0
ansible 2.2.1.0
ansible 2.2.0.0
ansible 2.1.6.0
ansible 2.1.5.0
ansible 2.1.4.0
ansible 2.1.3.0
ansible 2.1.2.0
ansible 2.1.1.0
ansible 2.1.0.0
ansible 2.0.2.0
ansible 2.0.1.0
ansible 2.0.0.2
ansible 2.0.0.1
ansible 1.9.6
ansible 1.9.5
ansible 1.9.4
```

Make a note of the version you want to install

### Ensure for miniconda

### Ensure for a virtual environment

Here we create a virtual environment called **ansible-2.2** that will include python2.x

```shell
conda create -y -n ansible-2.2 python=2
```

### activate the target virtual environment

```shell
source activate ansible-2.2
```

### Confirm active virtual environment

Confirm that the environment is active by verifying that the virtual environment name is prepended to your command prompt as follows:

```shell
(ansible-2.2) cjs@automa:~/projects$ 
```

Alternativly you can use the commend `which python` and confirm that the path returned is located in your target virtual environment:

```shell
/home/cjs/miniconda2/envs/ansible-2.2/bin/python
```

### Install the latest iteration of your target ansible version

If you want ansible 2.2 you probably the latest revision, 2.2.3.0. The following will install ansible as well as any dependancies.

```shell
pip install 'ansible==2.2.3.0' 
```

Installation confirmation

```shell
which ansible
```

Output example

```shell
/home/cjs/miniconda2/envs/ansible-2.2/bin/ansible
```

Version confirmation

```shell
ansible --version
```

Output example

```shell
ansible 2.1.0.0
  config file = 
  configured module search path = Default w/o overrides
```

That's it...
