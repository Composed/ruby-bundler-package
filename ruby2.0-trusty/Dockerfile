FROM ubuntu:trusty

RUN apt-get install -qy software-properties-common && \
    add-apt-repository -y 'ppa:brightbox/ruby-ng' && \
    apt-get update -qq && \
    apt-get install -qy ruby2.0 checkinstall
RUN mkdir -p /tmp/ruby-bundler-package

WORKDIR /tmp/ruby-bundler-package

### XXX: NOTE there are two places where you must bump the version number here
ENTRYPOINT ["checkinstall", "-D", "--pkgname", "ruby2.0-bundler", "--pkgversion", "1.10.6", "--maintainer", "'Dan Brown <dan@madebymany.co.uk>'", "--requires", "'ruby2.0 (>= 2.0.0.647-1bbox1~trusty1)'", "--default", "--exclude", "/var/lib/gems/2.0.0/cache,/root/.gem", "gem2.0", "install", "--no-document", "-v", "1.10.6", "bundler"]
