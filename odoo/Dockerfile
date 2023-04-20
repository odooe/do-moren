ARG ODOO_VERSION
FROM ghcr.io/tecnativa/doodba:${ODOO_VERSION}-onbuild

USER root

# RUN sed -i 's/DEFAULT@SECLEVEL=2/DEFAULT@SECLEVEL=1/g' /etc/ssl/openssl.cnf

RUN echo 'deb http://http.us.debian.org/debian/ buster main contrib non-free' >> /etc/apt/source.list

RUN echo 'deb-src http://http.us.debian.org/debian/ buster main contrib non-free' >> /etc/apt/source.list

RUN apt-get update

RUN apt-get install -y --no-install-recommends python3-libxml2 libxml2-dev libxslt1-dev libldap2-dev libsasl2-dev libcups2-dev libssl-dev libssl1.1 swig gcc

RUN pip install M2Crypto==0.38.0

RUN pip install Pillow==9.0.1

RUN mkdir -p /usr/local/lib/python3.8/site-packages/pyafipws/cache

RUN chown -R odoo:odoo /usr/local/lib/python3.8/site-packages/pyafipws/cache

RUN chown odoo:odoo /etc/ssl/openssl.cnf

USER odoo
