# Python3 Virtual Environments Using "virtualenv" Package

Using the pip3 package "virtualenv", it is easy to manage python projects that
have varying dependencies.

To create a virtual environment:
```bash
cd ~/virtualenvironments
virtualenv your_venv_name
```

To activate a virtual environment:
```bash
source ~/virtualenvironments/your_venv_name/bin/activate
```

Once here, you can install packages to the virtual environment using pip3.
Packages installed in one virtual environment do not affect other virtual 
environments.
```bash
pip3 install your_package_name
```

Environment dependencies can be added to a "requirements.txt" file to make 
working from different machines easier.
```bash
pip3 freeze --local > ~virtualenvironments/your_venv_name/requirements.txt"
```

To deactivate a virtual environment:
```bash
deactivate
```

## Tags
#python #virtualenvironment
