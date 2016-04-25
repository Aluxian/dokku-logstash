# dokku-logstash

## Deploy

Install ElasticSearch and create the app and its db:

```
dokku apps:create kibana
dokku plugin:install https://github.com/dokku/dokku-elasticsearch.git elasticsearch
dokku elasticsearch:create kibana
dokku elasticsearch:link kibana kibana
```

Now push your app:

```
git clone git@github.com:Aluxian/dokku-kibana.git
cd dokku-kibana
git remote add dokku dokku@yourserver.me:kibana
git push dokku master
```

## Env vars

- CONFIG_TYPE: Can be `simple` or `syslog`
- ELASTICSEARCH_URL
- DOWNLOAD_URL (for the buildpack)
