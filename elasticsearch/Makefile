add:
	curl -XPOST 'localhost:9200/pokemons/pictorial-book?pretty' -d '@pokemon.json'

# bulkのデータは\nで1行ごとに分けているので-dや--dataは改行を削除してしまうので
# 必ず--data-binaryを指定する必要がある
# 1行ごとのjsonなのでフォーマットかけたりするのも駄目
bulk:
	curl -XPOST 'localhost:9200/_bulk?pretty' --data-binary '@pokemons_bulk'

#全部を検索
match-all:
	curl -s -XGET 'localhost:9200/_search?pretty' -d @match-all.json | jq

search:
	curl -s -XGET 'localhost:9200/_search?pretty' -d @search.json | jq


#index一覧を表示
indices:
	curl 'localhost:9200/_cat/indices?v'

delete:
	curl -XDELETE 'localhost:9200/pokemons?pretty
