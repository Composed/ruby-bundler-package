FROM ubuntu:trusty

RUN apt-get install -qy software-properties-common && \
    add-apt-repository -y 'ppa:brightbox/ruby-ng' && \
    apt-get update -qq && \
    apt-get install -qy ruby2.3 checkinstall
RUN mkdir -p /tmp/ruby-bundler-package

WORKDIR /tmp/ruby-bundler-package

### XXX: NOTE there are two places where you must bump the version number here
ENTRYPOINT ["checkinstall", "-D", "--pkgname", "ruby2.3-bundler", "--pkgversion", "1.10.6", "--maintainer", "'Jerry Steele <jerry@composed.com>'", "--requires", "'ruby2.3 (>= 2.3.0-1bbox2~trusty1)'", "--default", "--exclude", "/var/lib/gems/2.3.0/cache,/root/.gem", "gem2.3", "install", "--no-document", "-v", "1.10.6", "bundler"]
