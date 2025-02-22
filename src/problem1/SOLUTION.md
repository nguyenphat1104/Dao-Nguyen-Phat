Provide your CLI command here:

1. Simple as screening from transaction-log.txt
curl -s "https://example.com/api/12346" >> ./output.txt
curl -s "https://example.com/api/12362" >> ./output.txt

2. Alternative, use with JSON Query:
jq -r 'select(.symbol == "TSLA" and .side == "sell") | .order_id' ./transaction-log.txt | xargs -I {} curl -s "https://example.com/api/{}" >> ./output.txt
