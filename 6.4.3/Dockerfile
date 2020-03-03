FROM elasticsearch:6.4.3 as with-plugin
RUN ./bin/elasticsearch-plugin install https://github.com/NLPchina/elasticsearch-sql/releases/download/6.4.3.0/elasticsearch-sql-6.4.3.0.zip
RUN ./bin/elasticsearch-plugin install --batch https://github.com/medcl/elasticsearch-analysis-ik/releases/download/v6.4.3/elasticsearch-analysis-ik-6.4.3.zip
RUN ./bin/elasticsearch-plugin install https://github.com/medcl/elasticsearch-analysis-pinyin/releases/download/v6.4.3/elasticsearch-analysis-pinyin-6.4.3.zip


FROM with-plugin
RUN curl -sL https://rpm.nodesource.com/setup_10.x | bash -
RUN yum install -y nodejs
RUN yum install epel-release -y
RUN yum install jq -y && \
    jq --version
RUN yum install -y vim
