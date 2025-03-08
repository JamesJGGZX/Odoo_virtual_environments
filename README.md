# Odoo_virtual_environments
Configuraciones de Virtualización para Odoo en diferentes versiones

Each environment is preconfigured with the appropriate versions of **Python, PostgreSQL and dependencies**, ensuring stability and compatibility.

## ⚠ **Prerequisites**.
Before you begin, make sure your system has the following libraries installed:

sudo apt update && sudo apt install -y build-essential libssl-dev libffi-dev python3-dev libpq-dev \
    libxml2-dev libxslt1-dev libsasl2-dev libldap2-dev libjpeg-dev zlib1g-dev

After the miniconda virtualizer has been installed this is the path where the virtualizations should be placed:

/miniconda3/envs

After performing the docker installation this is the command to create the postgre image configured for Odoo:

docker run -d \
  -e POSTGRES_USER=odoo \
  -e POSTGRES_PASSWORD=odoo \
  -e POSTGRES_DB=postgres \
  -p 5432:5432 \
  --name db postgres:<VERSIÓN>

After you have configured everything use the following command to run Odoo with virtualization enabled:

python odoo-bin -c /route_odoo_conf/ -d data_base_example
