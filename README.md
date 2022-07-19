# cuckoo-sandbox-installation-step-by-step



## Installing Cuckoo Sandbox


Useful websites:
- [Reuirements](https://cuckoo.readthedocs.io/en/latest/installation/host/requirements/)
- [Installing Cuckoo Sandbox](https://cuckoo.readthedocs.io/en/latest/installation/host/installation/)


### Before started...
Install `Anaconda` from [HERE](https://linuxhint.com/install-anaconda-ubuntu-22-04/)



### Requirements:
---
### Step 1 : 
Start by updating the server packages to the latest available.

```
$ sudo apt-get update
$ sudo apt-get upgrade -y
```

### Step 2 :
The Cuckoo host components is completely written in Python, therefore it is required to have an appropriate version of Python installed. At this point we only fully support Python 2.7.

The following software packages from the apt repositories are required to get Cuckoo to install and run properly:

```
$ sudo apt-get install libpq-dev python-dev libxml2-dev libxslt1-dev libldap2-dev libsasl2-dev libffi-dev
```


### Step 3 :
In order to use the Django-based Web Interface, MongoDB is required:

Install MongoDB from [HERE](https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-ubuntu/)

### Step 4 :
In order to use PostgreSQL as database (our recommendation), PostgreSQL will have to be installed as well:

```
$ sudo apt-get install postgresql libpq-dev -y
```

### Step 5 :
Create new envirement with name `cuckoo` and `python=3.6`:

```
$ conda create --name cuckoo python=3.6
```

### Step 6 : 
Activate conda envirement `cuckoo`:

```
$ conda activate cuckoo
```
### Install Cuckoo
---
### Step 7 : 
Installing the latest version of Cuckoo is as simple as follows. Note that it is recommended to first upgrade the `pip` and `setuptools `libraries as they’re often outdated, leading to issues when trying to install Cuckoo [(see also DistributionNotFound / No distribution matching the version..)](https://cuckoo.readthedocs.io/en/latest/faq/#pip-install-issue).

```
$ sudo pip install -U pip setuptools
```

### Step 8:
We need pip2 to install cuckoo:
```
$ sudo apt install python-pip
```

### Step 9 :
Install cuckoo using pip2:

```
$ pip2 install -U cuckoo
```

### Step 10 :
Run Cuckoo:
```
$ cuckoo
```


### Step 11 :
If Cuckoo cummond not found, try to update all packages:
```
$ conda update --all -y
```

### Step 12 :
If have Error like this `error: command 'x86_64-linux-gnu-gcc' failed with exit status 1`, do following commond:
```
$ sudo apt-get install python2.7-dev
```

### Step 13 :
Enabling mongodb in reporting.conf before run cuckoo webserver
```
$ sudo nano ~/.cuckoo/conf/reporting.conf
```

find `[mongodb]`, and change `enabled = no` to `enabled = yes`

### Run Cuckoo Webserver:
---
### Step 14 :
Run Cuckoo webserver:
```
$ cuckoo web
```

### Step 15 :
Congratulation :)

Cuckoo now running on [http://localhost:8000/](http://localhost:8000/)
