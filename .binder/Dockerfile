FROM rocker/binder:4.2.2
LABEL maintainer='Joey Trampush <j.trampush@gmail.com>'
USER root
COPY . ${HOME}
RUN chown -R ${NB_USER} ${HOME}
USER ${NB_USER}

RUN wget https://github.com/brainworkup/srt/raw/main/DESCRIPTION && R --vanilla -s -e "options(repos = list(CRAN = 'http://cran.rstudio.com'));  install.packages('pak'); pak::lockfile_install(lockfile = 'pkg.lock')"

RUN rm DESCRIPTION.1; exit 0
