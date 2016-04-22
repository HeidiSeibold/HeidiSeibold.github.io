# docker run --rm -p 8787:8787 -v /home/heidi/Documents/git/HeidiSeibold.github.io/:/home/rstudio blog

# servr::jekyll(command = '/usr/local/bin/jekyll build')

# most of the Dockerfile is taken from image: cboettig/labnotebook

FROM rocker/hadleyverse 

## So that things like `top` and `less` work correctly
ENV TERM xterm

## Install basic ruby, javascript, and linux utils we need for the site ##
RUN apt-get update \
  && apt-get install -y -t unstable \
    bundler \
    curl \
    nodejs \
    rake \
    rsync \
    libgmp3-dev \
  && apt-get clean \ 
  && rm -rf /var/lib/apt/lists/ \
  && gem install nokogiri -v '1.6.3.1' \ 
  && installGithub.r yihui/servr \
	&& install2.r -r http://cran.rstudio.com git2r \
  && rm -rf /tmp/downloaded_packages 


### Install additional Ruby gems given in the Gemfile ###  
### (bundler likes to be a non-root user in sudoers.) 
### (Docker won't cache layers depending on external files, so this goes last)
ADD Gemfile /data/Gemfile 
#ADD Gemfile.lock /data/Gemfile.lock
RUN adduser rstudio sudo \
  && echo '%sudo ALL=(ALL) NOPASSWD:ALL' >> /etc/sudoers \
  && chown -R rstudio:rstudio /data
USER rstudio
WORKDIR /data
RUN bundle update \
  && bundle config build.nokogiri --use-system-libraries \ 
  && bundle install \
  && bundle update
RUN export PATH=$PATH:/usr/local/bin/
RUN gem list

## My git name, must be done for user pid 1000, and root
RUN git config --global user.name 'HeidiSeibold' \
  && git config --global user.email 'heidi.seibold@uzh.ch' \
  && git config --global credential.helper 'cache --timeout=3600' \
  && git config --global push.default simple


## Reset and tidy up
USER root
WORKDIR /
RUN rm -rf /data && gem cleanup

## My git name, must be done for user pid 1000, and root
RUN git config --global user.name 'HeidiSeibold' \
  && git config --global user.email 'heidi.seibold@uzh.ch' \
  && git config --global credential.helper 'cache --timeout=3600' \
  && git config --global push.default simple


### Expose port for jekyll serve ###
EXPOSE 4000

# CMD sudo supervisord
