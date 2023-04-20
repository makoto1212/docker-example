#---起動---
up:
	docker compose up -d
#---終了---
down:
	docker compose down
#---マッピング設定---
mapping-add:
	curl -XPUT 'localhost:9200/pokemons' -d @mapping.json
#---マッピング確認---
#"dynamic": falseを設定することで指定したマッピング以外の型を制限する
mapping:
	curl -XGET 'localhost:9200/pokemons/_mapping?pretty'
#---データ1行投入---
add:
	curl -XPOST 'localhost:9200/pokemons/pictorial-book' -d '@pokemon.json'
#---データ複数投入---
#bulkのデータは\nで1行ごとに分けているので-dや--dataは改行を削除してしまうので
#必ず--data-binaryを指定する必要がある
# 行ごとのjsonなのでフォーマットかけたりするのも駄目
bulk:
	curl -XPOST 'localhost:9200/_bulk' --data-binary '@pokemons_bulk'
#---全件を表示---
search-all:
	curl -s -XGET 'localhost:9200/_search'
#---index一覧を表示---
indices:
	curl 'localhost:9200/_cat/indices?v'
#---削除---
delete:
	curl -XDELETE 'localhost:9200/pokemons'
