# Vagrant / Ansible / Docker swarm / K8s

## Was brauchen wir:

python 3, pip3, ansible

alles wird in der wsl gemacht:

    $python -m -venv --prompt ansible -start venv

    $. venv/bin/activate

    $pip install ansible

    $pip freeze >requirements.txt

    $pip install -r requirements.txt

venv ist das virtual environment und hilft uns mit dem requirements.txt
diese bestimmten versionen mit python zu installieren.

## Situation:

Vagrant funktioniert, jedoch keine möglichkeit die VMs mit ansible zu
steuern weil ich in der WSL nicht mit ssh zugriff haben kann. Habe einige Tage getroubleshooted und nicht wirklich eine Lösung gefunden.

![ssh problem](images/img1.PNG)

Fahre mit den ansible files trotzdem fort...

## Problemlösung endlich gefunden:

in der wsl im .ssh ordner die private.keys adden indem man eine config file erstellt und das rein schreibt:

![ssh problem](images/img3.PNG)

Ergebnis:
![ssh problem](images/img2.PNG)
