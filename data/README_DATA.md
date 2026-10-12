# Data files (synthetic)

Every file below was produced by the YOROSIX synthetic generator v6.3. Identifiers are generator indices, not real accounts.

## ml_node_features_v6_3.csv (one row per node)
| Column | Meaning |
|---|---|
| member_id | Node id (1–1000) |
| influence | Latent influence parameter of the generator |
| coop_tendency | Latent cooperation propensity of the generator |
| cluster_id | Community the node was generated in |
| bridge | 1 if the node links communities |
| total_replies, total_shares | Simulated activity counts |
| thanks_given, thanks_received | Simulated thanks counts |
| avg_dwell_time, avg_scroll_rate | Simulated browsing behaviour |
| conversion_rate, thanks_ratio, thanks_quality_score | Derived ratios |

Note: `influence` and `coop_tendency` are the generator's own parameters. Using them as model features lets a model recover the generator directly; exclude them when testing whether a method learns from behaviour.

## ml_edge_list_v6_3.csv
`source`, `target`: directed interaction between two nodes.

## ml_node_label_dataset_v6_3.csv
`member_id`, `label_node_expand`: the generator's binary expansion label (1 = the node's activity expanded the simulated cascade).

## bdf_f1pple_score_v0.3.csv
`member_id`, `f1pple_score`: Ripple score in [0, 1].

## gnn_expand_prob_v6_3.csv
`member_id`, `prob_expand`, `rank_desc`: output of a GNN trained on this dataset (see the main README on how to read its score).

## bdc_action_sequence_v6-3.json
List of `{time, actor, target, type}` with `type` in post, reply, share, thanks; timestamps are simulated.
