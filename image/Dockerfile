FROM eddelbuettel/r2u:22.04
RUN apt-get update 
RUN apt-get install -y --no-install-recommends pandoc pandoc-citeproc curl gdebi-core python3 python3-pip
RUN rm -rf /var/lib/apt/lists/*
RUN install.r shiny jsonlite ggplot2 htmltools remotes renv knitr rmarkdown quarto
RUN curl -LO https://github.com/quarto-dev/quarto-cli/releases/download/v1.4.549/quarto-1.4.549-linux-amd64.deb
RUN gdebi --non-interactive quarto-1.4.549-linux-amd64.deb
COPY requirements.txt .
RUN pip install -r requirements.txt
RUN quarto install tinytex
WORKDIR /data
