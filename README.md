# codi2021_scripts
Scripts to convert the [Universal Anaphora](https://github.com/UniversalAnaphora/UniversalAnaphora/blob/main/UA_CONLL_U_Plus_proposal_v1.0.md) format to jsonlines

1. `helper.py` contains scripts to convert UA to jsonlines format

2. `preprocess.py` contains scripts to parse annotation structure from UA documents

3. `conllua_dir` and `json_dir_*` contain UA and jsonlines files (respectively) for AMI, Persuasion, and Light datasets.

## Commands for conversion

```import helper```

#### Identity Anaphora

1. UA to jsonlines 
```helper.convert_coref_ua_to_json(UA_PATH, JSON_PATH, MODEL="coref-hoi", SEGMENT_SIZE=512, TOKENIZER_NAME="bert-base-cased")```

2. jsonlines to UA 
```helper.convert_coref_json_to_ua(JSON_PATH, UA_PATH, MODEL="coref-hoi")```

> **NOTE:** Currently, these scripts only support conversion to and from the format used by models that use bert/spanbert embeddings. E.g. [coref-hoi](https://github.com/lxucs/coref-hoi/).


#### Bridging

1. UA to jsonlines 
```helper.convert_bridg_ua_to_json(UA_PATH, JSON_PATH, MODEL="dali_bridging")```

2. jsonlines to UA 
```helper.convert_bridg_json_to_ua(JSON_PATH, UA_PATH, MODEL="dali-bridging")```

> **NOTE:** Currently, these scripts only support conversion to and from the format used by [dali-bridging](https://github.com/juntaoy/dali-bridging).


#### Discourse Deixis

1. Previous Utterance Baseline (for "this", "that")
```helper.discourse_deixis_baseline(IN_UA_PATH, PRED_UA_PATH, MODEL="previous-utterance")```
