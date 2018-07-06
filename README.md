# cheatsheet-jq-a4
<a href="https://github.com/DennyZhang?tab=followers"><img align="right" width="200" height="183" src="https://raw.githubusercontent.com/USDevOps/mywechat-slack-group/master/images/fork_github.png" /></a>

[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com) [![LinkedIn](https://raw.githubusercontent.com/USDevOps/mywechat-slack-group/master/images/linkedin.png)](https://www.linkedin.com/in/dennyzhang001) <a href="https://www.dennyzhang.com/slack" target="_blank" rel="nofollow"><img src="http://slack.dennyzhang.com/badge.svg" alt="slack"/></a> [![Github](https://raw.githubusercontent.com/USDevOps/mywechat-slack-group/master/images/github.png)](https://github.com/DennyZhang)

File me [tickets](https://github.com/DennyZhang/cheatsheet-jq-a4/issues) or star [the repo](https://github.com/DennyZhang/cheatsheet-jq-a4).

See more CheatSheets from Denny: [here](https://github.com/topics/denny-cheatsheets)

Table of Contents
=================

   * [cheatsheet-jq-a4](#cheatsheet-jq-a4)
   * [jq basic usage](#jq-basic-usage)
   * [jq with watch](#jq-with-watch)
   * [More links](#more-links)

<a href="https://www.dennyzhang.com"><img align="right" width="185" height="37" src="https://raw.githubusercontent.com/USDevOps/mywechat-slack-group/master/images/dns_small.png"></a>

# jq basic usage

```
curl $es_ip:9200/$index_name/_stats?pretty | less

curl $es_ip:9200/$index_name/_stats?pretty | jq '._all.primaries'

curl $es_ip:9200/$index_name/_stats?pretty | jq '._all.primaries | .docs, .merges, .segments'

watch "curl $es_ip:9200/$index_name/_stats?pretty | jq '._all.primaries | .docs, .merges, .segments'"

curl $es_ip:9200/$index_name/_stats?pretty | jq '.[0] | ._all: promaries}'

curl $es_ip:9200/$index_name/_stats?pretty | jq '._all.primaries.docs[]'

curl $es_ip:9200/$index_name/_stats?pretty | jq '._all.primaries.docs[], ._all.primaries.segments[]'

curl $es_ip:9200/$index_name/_stats?pretty | jq '._all.primaries[]' | jq '.docs'
```

# jq with watch

```
watch -n 0.5 "kubectl get configmaps map1 -o json | jq '.data[\"file1.conf\"]'"
```

# More links

- License: Code is licensed under [MIT License](https://www.dennyzhang.com/wp-content/mit_license.txt).

<a href="https://www.dennyzhang.com"><img align="right" width="201" height="268" src="https://raw.githubusercontent.com/USDevOps/mywechat-slack-group/master/images/denny_201706.png"></a>

<a href="https://www.dennyzhang.com"><img align="right" src="https://raw.githubusercontent.com/USDevOps/mywechat-slack-group/master/images/dns_small.png"></a>
