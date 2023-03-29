# Utilisation de l'image Debian
FROM debian:buster-slim

# Mise à jour des paquets et installer les dépendances nécessaires pour Odoo et wkhtmltopdf
RUN apt-get update && \
    apt-get install -y \
      wget \
      python3 \
      curl \
      sudo \
      python3-dev \
      python3-pip \
    && curl -o wkhtmltox.deb -sSL https://github.com/wkhtmltopdf/wkhtmltopdf/releases/download/0.12.5/wkhtmltox_0.12.5-1.buster_amd64.deb \
    && echo 'ea8277df4297afc507c61122f3c349af142f31e5 wkhtmltox.deb' | sha1sum -c - \
    && apt-get install -y --no-install-recommends ./wkhtmltox.deb

# run as root
RUN sudo -s

# Ajout des clés + répo odoo
RUN wget -O - https://nightly.odoo.com/odoo.key | sudo gpg --dearmor -o /usr/share/keyrings/odoo-archive-keyring.gpg && \
  echo 'deb [signed-by=/usr/share/keyrings/odoo-archive-keyring.gpg] https://nightly.odoo.com/16.0/nightly/deb/ ./' | sudo tee /etc/apt/sources.list.d/odoo.list

# Installation odoo
RUN apt-get update && sudo apt-get install -y odoo

# exit as root
RUN exit

# Copie du fichier de configuration d'Odoo
COPY ./odoo.conf /etc/odoo/odoo.conf

# Exposition du port utilisé par Odoo
EXPOSE 8069

# Lancement odoo avec configuration
CMD ["odoo", "-c", "/etc/odoo/odoo.conf"]
