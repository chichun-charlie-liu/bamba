# Bamba -- Reducing Inference Latencies
Standard `transformer` models are being adopted and deployed in production settings, where memory bandwidth bottleneck has emerged as a key challenge. The bottleneck is due to the per token decoding step which is very light on compute, but bottlenecked for short sequences by moving weights between memory and compute and for longer sequences moving KV-cache between memory and compute. As longer sequence models (e.g., Meta Llama3.1 is 128K, IBM Granite code v2 is 128K, Mistral large is 32k) are becoming popular due to the demands of applications, KV-cache bottleneck dominates. The key reason for KV-cache growth is the full attention layer and Several approaches such as model weight quntization and KV-cache optimization have Many approaches have been explored that reduce the kv-cache 