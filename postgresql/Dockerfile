# Utilisation de l'image PostgreSQL 12
FROM postgres:12

# Mise à jour des paquets
RUN apt-get update

ENV POSTGRES_USER odoo
ENV POSTGRES_PASSWORD pwd
ENV POSTGRES_DB odoo

# Exposer le port par défaut de PostgreSQL
EXPOSE 5432
