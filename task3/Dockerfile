# Utiliser l'image Ubuntu comme base
FROM ubuntu:latest

# Mettre à jour et installer les dépendances nécessaires
RUN apt-get update && apt-get upgrade -y && \
    apt-get install -y python3 python3-pip python3-venv

# Créer un environnement virtuel et activer cet environnement
RUN python3 -m venv /app/venv
ENV PATH="/app/venv/bin:$PATH"

# Installer Flask et flask-cors dans l'environnement virtuel
RUN pip install flask flask-cors

# Définir le répertoire de travail
WORKDIR /app

# Copier le fichier Python
COPY ./api.py /app/api.py

# Exposer le port
EXPOSE 5252

# Exécuter l'application
CMD ["python", "api.py"]
